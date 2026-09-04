## 2026-09-03 17:15:26 UTC [target] (model bigpickle)
## 2026-09-03 20:00:59 UTC [target] (model bigpickle)
[NEW] cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
[CHANGED] applicationdesigner.de/www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
[CHANGED] live-manager.de/www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
[CHANGED] dev.applicationdesigner.de live but 403 internal-only page; dev/staging/test/portal/account.live-manager.de do not serve HTTP.
[PRIO] cbs-proxy.api.live-manager.de,8.4,gate_ease=10(unauth WS)+cloud_surface+bd_fresh
[PRIO] www.live-manager.de,6.0,business_value(customer portal)+auth flow
[PRIO] www.applicationdesigner.de,5.2,tech_exposure(ExtJS+WS+AI/upload)
[HYP] Unauthenticated / unauth-token CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}
confidence: 65
reasoning: help.js builds the WS URL with client-side placeholders (cid=a.context.customerId, service=service_number) and passes origin=LiveDemo/LiveDebugger. Anonymous WS upgrade succeeded with zero credentials, emitting proxy CONNECT frames to CBS100/CBS190/CBS200 then READY. No token/Authorization was required or validated in the observed handshake, so whether cid scoping is enforced server-side is unverified.
evidence_needed: confirm proxy enforces an authenticated session token tied to the claimed cid, and that requesting a foreign cid is denied; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: (passive-first) WS upgrade to wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid=1&service=<test> and observe CONNECT/READY frame set; compare a probe with a clearly foreign/unowned cid and note whether READY/data is still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debugging (PII/voice data) — High if unauthenticated actor can enumerate cid.
testability: PASSIVE (handshake reachable anonymously; auth-scoping confirmation requires valid session = AUTH_HELPED/HUMAN)
[HYP] LiveManager rs (base64 return-url) post-login open-redirect -> OAuth/session chain
class: AUTH
asset: https://www.live-manager.de/?rs=<base64>& (Login.aspx flow)
confidence: 40
reasoning: every unauthenticated subpath 302 -> /?rs=<base64-of-requested-path>; the decoded target is carried to a return-URL parameter. GET does not reflect the value, so a direct anonymous open redirect is not present. Post-login redirect target validation is unverified.
evidence_needed: log in and observe whether the decoded rs target is honored verbatim for the post-auth redirect; a schema-less/external value reaching a Location header or JS redirect = open redirect.
verify_steps: (passive-first, AUTH needed) after obtaining a session, GET /?rs=<base64 of an attacker-controlled external URL> and follow the login; inspect the resulting redirect Location / JS navigation for reflection.
impact: open redirect enabling OAuth code/credential theft and ATO — Medium/High if redirects to attacker domain.
testability: AUTH_HELPED (needs a valid customer session + Human to confirm)
[HYP] AppDesigner playground/docs ExtJS help app proxies to internal CBS endpoints; exposed auth-less backend discovery
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (ExtJS help.js) and help.json/resources.help
confidence: 42
reasoning: the ExtJS help app (Sencha Cmd, app uuid 3342eca3-...) ships help.js containing live backend host wss://cbs-proxy.api.live-manager.de and an internal Proxy/Endpoint model. The documented help manifest (help.json) and resources (resources.help/) are publicly served, which can enumerate internal host/proxy names beyond the already-confirmed one.
evidence_needed: whether further unauth endpoints/hosts are listed in the served ExtJS app and whether any expose data or allow on-behalf-of calls.
verify_steps: GET /help.json, /resources.help/*, and the app JS to list proxy/endpoint URLs (read-only); cross-reference found hostnames against scope before any further probe.
impact: surface/asset discovery and potential unauthorized internal call relay — Medium.
testability: PASSIVE (read-only asset enumeration)
[FINAL] cbs-proxy IDOR (65) — strongest: confirmed anonymous WS handshake to in-scope host reaching backend CBS servers; highest value class.
[FINAL] LiveManager rs open-redirect (40) — plausible but needs session; parked above threshold but AUTH-gated.
[PARKED] AppDesigner ExtJS endpoint enumeration (42): valid but lower impact; kept only as supporting for cbs-proxy chain.
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=<observable-test> with explicit Upgrade/Sec-WebSocket headers (no auth) to confirm the READY frame set and whether cid/service are validated pre-connect or merely forward-connected; ~1 req, read-only handshake, no data subscription.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); 6 confirms the surface is far smaller than the 22-host inventory suggested, limiting breadth.
## 2026-09-03 22:30:38 UTC [target] (model bigpickle)
[PRIO] cbs-proxy.api.live-manager.de,7.85,a=8,b=9,t=6,g=10,c=2,f=10
[PRIO] api.live-manager.de,7.15,a=9,b=8,t=9,g=5,c=2,f=6
[PRIO] www.applicationdesigner.de,6.0,a=6,b=6,t=8,g=6,c=2,f=7
[PRIO] www.live-manager.de,5.8,a=5,b=8,t=5,g=6,c=2,f=7
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}
confidence: 65
reasoning: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
evidence_needed: confirm proxy enforces an authenticated session token tied to the claimed cid, and that requesting a foreign cid is denied; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: (passive-first) WS upgrade to wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid=1&service=<test> and observe CONNECT/READY frame set; compare a probe with a clearly foreign/unowned cid and note whether READY/data is still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debugging (PII/voice data) — High if unauthenticated actor can enumerate cid.
testability: PASSIVE (handshake reachable anonymously; auth-scoping confirmation requires valid session = AUTH_HELPED/HUMAN)
[HYP] Debug endpoints on api.live-manager.de expose internal information or allow unauthorized actions
class: MISCONFIG
asset: https://api.live-manager.de/
confidence: 50
reasoning: API versioning and debug endpoints often leak information or allow unauthorized access if not properly secured.
evidence_needed: confirm the presence of debug endpoints (e.g., /debug, /test, /api/v1/debug) and whether they return sensitive information or allow unauthorized actions.
verify_steps: (passive-first) GET https://api.live-manager.de/ and https://api.live-manager.de/debug, https://api.live-manager.de/api/v1/debug, etc. Observe status codes and responses.
impact: Information disclosure or unauthorized actions — Medium to High.
testability: PASSIVE (read-only probing)
[HYP] ExtJS help app proxies to internal CBS endpoints, exposing backend discovery
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (ExtJS help.js) and help.json/resources.help
confidence: 42
reasoning: the ExtJS help app ships help.js containing live backend host wss://cbs-proxy.api.live-manager.de and an internal Proxy/Endpoint model. The documented help manifest and resources are publicly served, which can enumerate internal host/proxy names.
evidence_needed: whether further unauth endpoints/hosts are listed in the served ExtJS app and whether any expose data or allow on-behalf-of calls.
verify_steps: GET /help.json, /resources.help/*, and the app JS to list proxy/endpoint URLs (read-only); cross-reference found hostnames against scope before any further probe.
impact: surface/asset discovery and potential unauthorized internal call relay — Medium.
testability: PASSIVE (read-only asset enumeration)
[FINAL] cbs-proxy IDOR (65) — strongest: confirmed anonymous WS handshake to in-scope host reaching backend CBS servers; highest value class.
[FINAL] api.live-manager.de debug endpoints (50) — plausible but needs probing; higher tech exposure.
[PARKED] AppDesigner ExtJS endpoint enumeration (42): valid but lower impact; kept only as supporting for cbs-proxy chain.
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with explicit Upgrade/Sec-WebSocket headers (no auth) to confirm READY frame set and whether cid/service are validated pre-connect.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); 6 confirms the surface is far smaller than the 22-host inventory suggested, limiting breadth.
## 2026-09-04 00:32:59 UTC [target] (model bigpickle)
[PRIO] cbs-proxy.api.live-manager.de,8.05,a=8,b=9,t=10,g=10,c=6,f=2
[PRIO] api.live-manager.de,6.25,a=7,b=8,t=7,g=5,c=6,f=1
[PRIO] www.applicationdesigner.de,5.80,a=6,b=5,t=8,g=9,c=4,f=1
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}
confidence: 70
reasoning: Confirmed anonymous WS handshake reaches backend CBS servers with client-supplied cid/service and no observed token; highest-value class in inventory.
evidence_needed: confirm proxy enforces an authenticated session token tied to the claimed cid, and that requesting a foreign cid is denied; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: (passive-first) WS upgrade to wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid=1&service=<test> and observe CONNECT/READY frame set; compare a probe with a clearly foreign/unowned cid and note whether READY/data is still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debugging (PII/voice data) — High if unauthenticated actor can enumerate cid.
testability: PASSIVE (handshake reachable anonymously; auth-scoping confirmation requires valid session = AUTH_HELPED/HUMAN)
[HYP] Debug endpoints on api.live-manager.de expose internal information or allow unauthorized actions
class: MISCONFIG
asset: https://api.live-manager.de/
confidence: 50
reasoning: API versioning and debug endpoints often leak information or allow unauthorized access if not properly secured.
evidence_needed: confirm the presence of debug endpoints (e.g., /debug, /test, /api/v1/debug) and whether they return sensitive information or allow unauthorized actions.
verify_steps: (passive-first) GET https://api.live-manager.de/ and https://api.live-manager.de/debug, https://api.live-manager.de/api/v1/debug, etc. Observe status codes and responses.
impact: Information disclosure or unauthorized actions — Medium to High.
testability: PASSIVE (read-only probing)
[HYP] ExtJS help app proxies to internal CBS endpoints, exposing backend discovery
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (ExtJS help.js) and help.json/resources.help
confidence: 42
reasoning: ExtJS help app ships help.js containing live backend host wss://cbs-proxy.api.live-manager.de and an internal Proxy/Endpoint model. The documented help manifest and resources are publicly served, which can enumerate internal host/proxy names.
evidence_needed: whether further unauth endpoints/hosts are listed in the served ExtJS app and whether any expose data or allow on-behalf-of calls.
verify_steps: GET /help.json, /resources.help/*, and the app JS to list proxy/endpoint URLs (read-only); cross-reference found hostnames against scope before any further probe.
impact: surface/asset discovery and potential unauthorized internal call relay — Medium.
testability: PASSIVE (read-only asset enumeration)
[PARKED] ExtJS endpoint enumeration (42): valid but lower impact; kept only as supporting for cbs-proxy chain.
[FINAL] cbs-proxy IDOR (70) — strongest: confirmed anonymous WS handshake to in-scope host reaching backend CBS servers; highest value class.
[FINAL] api.live-manager.de debug endpoints (50) — plausible but needs probing; higher tech exposure.
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with explicit Upgrade/Sec-WebSocket headers (no auth) to confirm READY frame set and whether cid/service are validated pre-connect.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); 6 confirms the surface is far smaller than the 22-host inventory suggested, limiting breadth.
## 2026-09-04 05:08:59 UTC [target] (model bigpickle)
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid={customer_id}&service={service_number}
confidence: 72
reasoning: Live probe 2026-09-04 returned HTTP/1.1 101 Switching Protocols for an anonymous WS-upgrade carrying client-supplied cid=1&service=100 with no Authentication/token header; TLS valid. No proxy-level auth observed pre-upgrade. Whether the proxy binds the claimed cid to a server-side session is unverified.
evidence_needed: confirm the proxy enforces an authenticated session token bound to the claimed cid and denies foreign/unowned cid; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: Interactively complete a WS handshake with a cid the actor owns (valid session, AUTH_HELPED/HUMAN) and confirm READY only for that cid; a foreign cid should be denied. Do NOT subscribe to other customers' live call/data (out of program scope).
impact: cross-tenant exposure of customer business-system call streams / live debug (PII/voice) — HIGH if cid enumerable unauthenticated.
testability: AUTH_HELPED (handshake is anonymously reachable; cross-tenant scoping confirmation requires valid customer session + human)
[HYP] AppDesigner ExtJS help app exposes full internal proxy/endpoint model (supporting cbs-proxy chain)
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (help.js, help.json, resources.help/*)
confidence: 50
reasoning: ExtJS help app (uuid 3342eca3-...) ships a Proxy/Endpoint model that disclosed wss://cbs-proxy.api.live-manager.de; the served manifest/resources may list additional internal proxy/endpoint hostnames behind CDN that resolve to in-scope /22 — pure passive asset enumeration that feeds the cbs-proxy chain.
evidence_needed: whether help.json / resources.help / app JS list further anonymous endpoints/hosts and whether any allow on-behalf-of calls.
verify_steps: GET /help.json, /help.js, and /resources.help/* bundles; extract proxy/endpoint URLs (read-only); cross-reference every found host against scope before further probing.
impact: internal surface discovery and potential onward internal-call relay — MEDIUM, supporting role to the confirmed cbs-proxy.
testability: PASSIVE (read-only asset enumeration)
[HYP] (dropped) api.live-manager.de debug endpoints — host does not resolve; no surface to probe → removed.
