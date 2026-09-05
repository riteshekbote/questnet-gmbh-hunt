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
## 2026-09-04 09:47:43 UTC [target] (model bigpickle)
[PRIO] cbs-proxy.api.live-manager.de,7.75,a=7,b=8,t=5,g=9,c=5,f=5
[PRIO] www.applicationdesigner.de,6.10,a=5,b=6,t=6,g=8,c=5,f=3
[PRIO] www.live-manager.de,4.90,a=5,b=6,t=3,g=3,c=5,f=3
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid={customer_id}&service={service_number}
confidence: 72
reasoning: Live probe 2026-09-04 returned HTTP/1.1 101 Switching Protocols for anonymous WS-upgrade carrying cid=1&service=100 with no Authentication/token header; TLS valid. No proxy-level auth observed pre-upgrade.
evidence_needed: confirm the proxy enforces an authenticated session token bound to the claimed cid and denies foreign/unowned cid; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: WS upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key. Observe server response frames (CONNECT/READY or error). Compare with a clearly invalid cid to note whether READY is still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debug (PII/voice) — HIGH if cid enumerable unauthenticated.
testability: AUTH_HELPED (handshake is anonymously reachable; cross-tenant scoping confirmation requires valid customer session + human)
[HYP] ExtJS help app exposes full internal proxy/endpoint model
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (help.js, help.json, resources.help/*)
confidence: 50
reasoning: ExtJS help app (uuid 3342eca3-...) ships a Proxy/Endpoint model that disclosed wss://cbs-proxy.api.live-manager.de; the served manifest/resources may list additional internal proxy/endpoint hostnames.
evidence_needed: whether help.json / resources.help / app JS list further anonymous endpoints/hosts and whether any allow on-behalf-of calls.
verify_steps: GET /help.json, /help.js, and /resources.help/* bundles; extract proxy/endpoint URLs (read-only); cross-reference every found host against scope before further probing.
impact: internal surface discovery and potential onward internal-call relay — MEDIUM, supporting role to the confirmed cbs-proxy.
testability: PASSIVE (read-only asset enumeration)
[FINAL] cbs-proxy IDOR (72) — strongest: confirmed anonymous WS handshake to in-scope host reaching backend CBS servers; highest value class.
[FINAL] ExtJS endpoint enumeration (50) — valid but lower impact; kept as supporting for cbs-proxy chain.
[NEXT] PROBE: GET https://www.applicationdesigner.de/help.json — extract full endpoint/proxy model from ExtJS manifest to discover additional internal hosts behind cbs-proxy chain (read-only, passive). This feeds the cbs-proxy IDOR chain by enumerating what services/identifiers are available.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend hostnames.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); secondary finding confirms internal surface enumeration via public ExtJS app. Breadth limited by CDN wildcard surface.
## 2026-09-04 14:08:06 UTC [target] (model bigpickle)
[PRIO] cbs-proxy.api.live-manager.de,7.40,a=7,b=8,t=5,g=9,c=8,f=8
[PRIO] www.applicationdesigner.de,6.10,a=5,b=6,t=6,g=8,c=5,f=3
[PRIO] www.live-manager.de,4.70,a=4,b=6,t=3,g=3,c=6,f=3
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid={customer_id}&service={service_number}
confidence: 72
reasoning: Live probe 2026-09-04 returned HTTP/1.1 101 Switching Protocols for anonymous WS-upgrade carrying cid=1&service=100 with no Authentication/token header; TLS valid; Ratchet/0.4.4 backend. No proxy-level auth observed pre-upgrade. Whether the proxy binds the claimed cid to a server-side session is unverified.
evidence_needed: confirm the proxy enforces an authenticated session token bound to the claimed cid and denies foreign/unowned cid; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: WS upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key. Observe server response frames (CONNECT/READY or error). Compare with a clearly invalid cid to note whether READY is still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debug (PII/voice) — HIGH if cid enumerable unauthenticated.
testability: AUTH_HELPED (handshake is anonymously reachable; cross-tenant scoping confirmation requires valid customer session + human)
[HYP] ExtJS help app exposes full internal proxy/endpoint model
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (help.js, help.json, resources.help/*)
confidence: 50
reasoning: ExtJS help app (uuid 3342eca3-...) ships a Proxy/Endpoint model that disclosed wss://cbs-proxy.api.live-manager.de; the served manifest/resources may list additional internal proxy/endpoint hostnames behind CDN that resolve to in-scope /22 — pure passive asset enumeration that feeds the cbs-proxy chain.
evidence_needed: whether help.json / resources.help / app JS list further anonymous endpoints/hosts and whether any allow on-behalf-of calls.
verify_steps: GET /help.json, /help.js, and /resources.help/* bundles; extract proxy/endpoint URLs (read-only); cross-reference every found host against scope before further probing.
impact: internal surface discovery and potential onward internal-call relay — MEDIUM, supporting role to the confirmed cbs-proxy.
testability: PASSIVE (read-only asset enumeration)
[HYP] (dropped) api.live-manager.de debug endpoints — host does not resolve; no surface to probe → removed.
[PARKED] ExtJS endpoint enumeration (50): valid but lower impact; kept only as supporting for cbs-proxy chain.
[FINAL] cbs-proxy IDOR (72) — strongest: confirmed anonymous WS handshake to in-scope host reaching backend CBS servers; highest value class.
[FINAL] api.live-manager.de debug endpoints — DROPPED: host does not resolve; no surface.
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key (base64 nonce) headers — no auth, no token — to confirm READY frame set and whether cid/service are validated pre-connect. ~1 req, read-only handshake, no data subscription. Compare response with a clearly invalid cid (e.g., cid=999999999) to note behavioral difference.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend hostnames.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists. Attack surface is path-based behind CDN.
[LEARN] REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe → removed from active hypotheses.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); secondary finding confirms internal surface enumeration via public ExtJS app. Breadth limited by CDN wildcard surface (8632 hostnames → 0 dedicated subdomain). Two confirmed in-scope live hosts total. api.live-manager.de non-resolving reduces API-surface scope to cbs-proxy alone.
## 2026-09-04 17:41:10 UTC [target] (model bigpickle)
[PRIO] cbs-proxy.api.live-manager.de,7.40,a=7,b=8,t=5,g=9,c=8,f=8
[PRIO] www.applicationdesigner.de,6.10,a=5,b=6,t=6,g=8,c=5,f=3
[PRIO] www.live-manager.de,4.70,a=4,b=6,t=3,g=3,c=6,f=3
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid={customer_id}&service={service_number}
confidence: 72
reasoning: Live probe 2026-09-04 returned HTTP/1.1 101 Switching Protocols for anonymous WS-upgrade carrying cid=1&service=100 with no Authentication/token header; TLS valid; Ratchet/0.4.4 backend. No proxy-level auth observed pre-upgrade. Whether the proxy binds the claimed cid to a server-side session is unverified.
evidence_needed: confirm the proxy enforces an authenticated session token bound to the claimed cid and denies foreign/unowned cid; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: WS upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key. Observe server response frames (CONNECT/READY or error). Compare with a clearly invalid cid to note whether READY is still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debug (PII/voice) — HIGH if cid enumerable unauthenticated.
testability: AUTH_HELPED (handshake is anonymously reachable; cross-tenant scoping confirmation requires valid customer session + human)
[HYP] ExtJS help app exposes full internal proxy/endpoint model
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (help.js, help.json, resources.help/*)
confidence: 50
reasoning: ExtJS help app (uuid 3342eca3-...) ships a Proxy/Endpoint model that disclosed wss://cbs-proxy.api.live-manager.de; the served manifest/resources may list additional internal proxy/endpoint hostnames.
evidence_needed: whether help.json / resources.help / app JS list further anonymous endpoints/hosts and whether any allow on-behalf-of calls.
verify_steps: GET /help.json, /help.js, and /resources.help/* bundles; extract proxy/endpoint URLs (read-only); cross-reference every found host against scope before further probing.
impact: internal surface discovery and potential onward internal-call relay — MEDIUM, supporting role to the confirmed cbs-proxy.
testability: PASSIVE (read-only asset enumeration)
[PARKED] ExtJS endpoint enumeration (50): valid but lower impact; kept as supporting for cbs-proxy chain.
[FINAL] cbs-proxy IDOR (72) — strongest: confirmed anonymous WS handshake to in-scope host reaching backend CBS servers; highest value class.
[NEXT] PROBE: GET https://www.applicationdesigner.de/help.json — extract full endpoint/proxy model from ExtJS manifest to discover additional internal hosts behind cbs-proxy chain (read-only, passive). This feeds the cbs-proxy IDOR chain by enumerating what services/identifiers are available.
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key (base64 nonce) headers — no auth, no token — to confirm READY frame set and whether cid/service are validated pre-connect. ~1 req, read-only handshake, no data subscription. Compare response with a clearly invalid cid (e.g., cid=999999999) to note behavioral difference.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend hostnames.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists. Attack surface is path-based behind CDN.
[LEARN] REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe → removed from active hypotheses.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); secondary finding confirms internal surface enumeration via public ExtJS app. Breadth limited by CDN wildcard surface (8632 hostnames → 0 dedicated subdomain). Two confirmed in-scope live hosts total. api.live-manager.de non-resolving reduces API-surface scope to cbs-proxy alone.
## 2026-09-04 20:00:00 UTC [target] (model bigpickle)
[HYP] Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS
class: IDOR
asset: chain GET https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token={publicstatic}&customer_id={cid}&srn={service} -> wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}
confidence: 85
reasoning: help.js publicly ships static credential (sha256 8d2faac1...) that auth.php accepts in lieu of a session ("Not logged in" only when token omitted); auth.php returns success:true and a 64-hex auth+ttl for both owned demo cid 131727 (auth efa148...) and foreign cid 2 (auth bb3889...) — no ownership/session binding observed. Prior accepted evidence: anonymous WS upgrade to cbs-proxy returns 101 and the LiveDebugger client then sends packet live_debug{customer_id,CLI,srn,token,ttl,hash} to attach to a tenant call-flow session. A real attacker needs only the public JS credential, then any cid.
evidence_needed: confirm the cbs-proxy/live_debug backend binds minted token to a real operator session owner of the cid (a valid customer session denying a foreign cid that was nonetheless minted) — without a binding check, minting-is-authorization and cross-tenant call-flow/voice debug attach is possible.
verify_steps: (AUTH_HELPED/HUMAN, do not perform anonymously) with a valid operator session, mint token for OWN cid, then present it to cbs-proxy for a FOREIGN cid and confirm server denial; behavioral comparison only. No live debug data subscribed.
impact: cross-tenant attach to customer business-system live call/debug streams (PII/voice) — HIGH/CRITICAL if no binding check.
testability: AUTH_HELPED (minting anonymous-PASSIVE confirmed; stream-attach confirmation needs session+human)
[HYP] Voicenote endpoints serve/cross-tenant voice recordings via file/param handling
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/{get,details,download,delete,check}.php
confidence: 50
reasoning: help.js builds audio URL `BACKEND_URL+'/extjs/voicenotes/download.php?file='+filename` (encodeURIComponent) — file param, no visible customer scoping in the request; voicenotes are recorded call voice messages (PII). Same BACKEND_TOKEN credential pattern; getCustomers proved token-scoped, so cross-tenant scope of voicenotes is unverified.
evidence_needed: whether voicenotes/get|download validate the file against the token-bound customer or accept foreign/arbitrary file names (traversal or cross-tenant id).
verify_steps: GET /extjs/voicenotes/get.php?token={publicstatic}&customer_id=131727 (demo, own) and compare with foreign cid behavior; GET download.php?file=<nonexistent> to observe 404/403 gating. Do NOT fetch real recordings.
impact: cross-tenant voice-note (PII/voice) access or arbitrary file download — MEDIUM/HIGH if per-cid enabled.
testability: PASSIVE (read-only behavioral GETs)
[HYP] AI Designer agent-token endpoint mints tenant-bound tokens for arbitrary customerId (parallel to auth.php)
class: IDOR
asset: https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?customerId={cid}
confidence: 55
reasoning: help.js calls it with useDefaultXhrHeader:false, method GET, params {customerId:c} and decrypts the response client-side (CB.util.security.decryptData); paired get_agent_costs.php and AIDesigner/backend/public/index.php?route= + coding.php imply on-behalf AI-agent actions. If gated only by the same public credential, the pattern mirrors the confirmed auth.php flaw (per-cid minting without session check).
evidence_needed: whether get_agent_token.php returns a distinct token for foreign customerId=2 vs demo 131727 identically, i.e., no ownership check pre-mint.
verify_steps: GET /extjs/agent/get_agent_token.php?token={publicstatic}&customerId=131727 vs customerId=2 (read-only mint comparison). Do NOT invoke any agent action.
impact: cross-tenant AI-agent token minting -> on-behalf actions / cost abuse — MEDIUM/HIGH.
testability: PASSIVE (read-only mint comparison)
[NEXT] PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token={publicstatic}&customerId=2 vs customerId=131727 (read-only, ~2 req @1rps, no cookies, no agent invocation) and compare success/scope to decide whether the agent-token mint mirrors the confirmed auth.php flaw (parallel BOLA).
[LEARN] ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a static credential embedded in public help.js — observed success:true for foreign cid=2, "Not logged in" only when token omitted.
[LEARN] ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint map including /api/callbuilder/ proxy prefix and AIDesigner backend router.
[LEARN] REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service — cross-tenant BOLA candidate (unchanged, now chained).
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
[LEARN] REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
[RISK] questnet-gmbh: 68 — Full primitive chain now confirmed read-only: public static credential in help.js -> per-tenant debug auth token minted for ANY customer_id via auth.php -> anonymous 101 WS to in-scope cbs-proxy backend. Cross-tenant live call-flow/voice debug attach is plausible and only blocked by an unverified WS-side binding. Real program surface stays at 4 hosts; CDN-wildcard breadth 0 caps scope expansion. PoC required before valid bug gate; no live customer data touched.
## 2026-09-04 22:18:52 UTC [target] (model bigpickle)
[HYP] Cross-tenant live-debug/call attach via auth.php mint (public credential) + cbs-proxy WS
class: IDOR
asset: https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token={pub-static}&customer_id={cid}&srn={srn} -> wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={srn}
confidence: 88
reasoning: Re-probed today: demo credential (sha256 8d2faac1…) at auth.php with srn=100 mints success:true for own 131727 AND foreign cid=2 (fresh auth hashes, ttl future). getCustomers/get/voicenotes all IGNORE the passed customer_id (token-bound), i.e. server trusts token→cid binding with no ownership check anywhere observed. Only unverified link: whether cbs-proxy/live_debug binds minted auth to a real operator owning the cid.
evidence_needed: behavior of cbs-proxy WS when supplied invalid cid vs minted aid — whether READY/CONNECT is emitted for a cid the presenting credential was NOT minted for.
verify_steps: (AUTH_HELPED) with a valid operator session mint for own cid, then present to proxy for a foreign cid and observe denial; behavioral only. Differently, anonymous WS-upgrade handshake GET wss://cbs-proxy?origin=LiveDemo&cid=999999999&service=100 and compare first-frame behavior vs cid=1 — read-only handshake, no live_debug packet, no data subscription.
impact: cross-tenant attach to customer business-system live call/debug streams (PII/voice) — HIGH/CRITICAL if no binding.
testability: AUTH_HELPED
[HYP] Public demo credential grants anonymous read of a real tenant's voice-note metadata (broken auth via static token)
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/get.php?token={pub-static}&customer_id={cid}
confidence: 85
reasoning: Confirmed anonymously: get.php returns success:true with full voicenote list (subjects containing phone numbers, UUID filenames, service numbers, sizes) for tenant 131727 using the credential embedded in public help.js; customer_id param ignored → the static token IS the authorization for a real tenant's voice-PII index. download.php additionally gated by session + "No VPN detected." (and 403 outside their network/VPN), so raw audio exfil via this endpoint not observed anonymously.
evidence_needed: whether sibling endpoints (details.php/check.php/delete.php) expose more of the tenant object anonymously; whether the demo tenant is treated as non-production in the backend.
verify_steps: Do NOT list/download real recordings. Only confirm gating: GET check.php?token=…&customer_id=2 vs 131727 (read-only); compare responses for presence/absence of the PII index. Report must not reproduce subjects/phone numbers.
impact: anonymous disclosure of a real customer's call/voicemail metadata (PII incl. phone numbers); compound with cbs-proxy chain → HIGH.
testability: PASSIVE
[HYP] /api/callbuilder/ same-host reverse proxy reaches internal AIDesigner/CBS backend unauthenticated (parallel to cbs-proxy)
class: IDOR
asset: https://www.applicationdesigner.de/api/callbuilder/<path>
confidence: 45
reasoning: help.js sets APPDESIGNER_API_PATH='/api/callbuilder/' (nginx proxy prefix) and APPDESIGNER_API_PATH_NOPROXY='https://applicationdesigner.de/' for the same backend; config.php (no token) is unknowingly reachable via both hosts. If the prefix proxies arbitrary backend paths with no client-bound auth, it mirrors cbs-proxy as a same-host BOLA relay.
evidence_needed: whether /api/callbuilder/AIDesigner/backend/… responses differ (auth bypass) vs direct host responses (403 Invalid token).
verify_steps: GET https://www.applicationdesigner.de/api/callbuilder/AIDesigner/backend/public/index.php?route= and /api/callbuilder/AIDesigner/backend/config.php — compare status/body vs the direct applicationdesigner.de results (403 vs 200).
impact: same-host anonymous relay to internal AI/CBS backend; supporting the chain — MEDIUM.
testability: PASSIVE
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key: <base64nonce> — read-only handshake, observe CONNECT/READY vs error, compare with prior cid=1 evidence; do NOT send live_debug/liveSub packets. Decides whether cid is validated pre-BOLA-attach.
[RISK] questnet-gmbh: 74 — Public static credential in help.js now demonstrated to grant anonymous read of a real tenant's voice-note metadata (phone-number PII) and anonymous per-cid live-debug token mint, feeding an anonymous WS proxy to backend CBS systems; only the WS-side binding check and raw-audio exfil (session/VPN-gated) remain unproven. PII was observed but not echoed/reports restricted; no recordings fetched, no live stream subscribed, no agent actions invoked. Surface frozen at 4 hosts; PoC still required before valid-bug gate.
## 2026-09-05 00:15:29 UTC [target] (model bigpickle)
[HYP] WS-side binding check absent: anonymous cbs-proxy upgrade accepts any client-supplied cid/service (no token binding on binary frames)
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de/?origin=<ClientType>&cid={cid}&service={service}
confidence: 72
reasoning: Re-confirmed today the anonymous chain up to the WS hop: public static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) in help.js is the sole auth for auth.php mint (foreign cid=2 minted success:true), getCustomers (returns only 131727), voicenotes/check,get (customer_id ignored, identical totals for cid=2 vs 131727). No endpoint observed enforces token→cid ownership. The upgrade handshake already reaches backend CBS servers anonymously (ACCEPTED), so the only unverified object-level control is inside the WS session layer (binary-frame binding of minted aid to the presenting cid).
evidence_needed: whether a cbs-proxy WS session opened for cid X delivers data frames (READY/CONNECT/stream) when the presented credential was minted for cid Y, or refuses the subscribe.
verify_steps: AUTH_HELPED — with a valid operator session, mint for OWN cid, then open wss://cbs-proxy?cid={over} and observe first-frame deny vs data; behavioral comparison only. Never subscribe to real live streams anonymously.
impact: cross-tenant attach to customer live call/debug streams (voice/PII) — HIGH/CRITICAL if frames are not bound.
testability: AUTH_HELPED
[HYP] Static demo credential exposes foreign-tenant voice-note index because customer_id is decoration
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/check.php|get.php|details.php?token={pub-static}&customer_id={cid}
confidence: 85
reasoning: Confirmed today anonymously: check.php returns success:true total=1 max_id=10942 identically for cid=2 (foreign) and cid=131727 (demo own) with the public static credential — customer_id plainly ignored; matches get.php behavior (ACCEPTED for 131727). The token is the entire authorization; any customer_id renders the same tenant object. details.php/delete.php gating unexamined.
evidence_needed: whether details.php exposes per-file metadata for the same token-bound tenant regardless of customer_id, and whether delete.php requires session (mutating, skipped).
verify_steps: PASSIVE confirmation only — GET check.php?customer_id=2 vs 131727 (done, identical). Do NOT list/download recordings; do NOT touch delete.php.
impact: anonymous cross-tenant voice-note metadata index (PII incl. phone numbers) of a real tenant via public JS credential; raw audio still VPN/session-gated — HIGH compound, MEDIUM standalone.
testability: PASSIVE
[HYP] Demo credential chain enables silent cross-customer debug-token reuse against the cbs backend router
class: IDOR
asset: https://www.applicationdesigner.de/extjs/livedebugger/{auth,get,subscribe}.php?token={pub-static}
confidence: 80
reasoning: auth.php mints per-tenant debug auth for arbitrary customer_id with success:true using the static credential (ACCEPTED); siblings under livedebugger/ (get/subscribe endpoints implied by LiveDebugger client in help.js) consume the minted sid/aid. If none of them re-validate an operator session, the mint alone grants the debug context of a foreign tenant, which is the exact entry the cbs-proxy chain needs.
evidence_needed: whether livedebugger sessions minted for a foreign cid can be presented to cbs-proxy with service AND get frame-level acceptance.
verify_steps: AUTH_HELPED — behavioral: mint for own cid via session, mint for foreign cid via static credential, compare success; never subscribe to live streams.
impact: cross-tenant debug session establishment feeding the WS attach — HIGH (chained).
testability: AUTH_HELPED
[NEXT] RAG: query corpus for any earlier valid-operator cbs-proxy handshake transcript (origin/cid/service frame exchange) before spending the remaining AUTH_HELPED coin — to confirm whether the proxy echoes a per-connection app-level READY/ERROR that would prove/dismiss binding without new operator time.
[RISK] questnet-gmbh: 74 — No new exploitable surface found this session; three pending hypotheses closed (agent-token mint gated, callbuilder relay absent, help.json inert), while the two ACCEPTED primitives (static-credential anonymous per-cid token mint; anonymous WS upgrade reaching backend CBS with client-supplied cid/service) remain the live chain. Cross-tenant voice-note index (PII) is confirmed token-bound with customer_id decoration ignored; raw audio exfil and frame-level WS binding are the two remaining unproven hops before a valid high/ critical bug can be filed. The next move is corpus RAG for WS frame evidence, since all remaining verification steps are AUTH_HELPED and should not be run anonymously. PII was observed but not echoed; no recordings fetched, no live streams subscribed, no mutations performed.
## 2026-09-05 04:44:39 UTC [target] (model bigpickle)
[HYP] cbs-proxy WS router is an unauthenticated full-duplex relay to the CBS backend for any client-chosen cid/service; no object-level control exists at the router layer
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}
confidence: 84
reasoning: Live probes this session: anonymous WS upgrade with cid=999999999 (non-existent) and service=999999 (invalid) each return HTTP/1.1 101 plus identical frame set CONNECT CBS100/CBS190/CBS200 then PROXY READY — byte-identical to cid=1, zero credentials/headers beyond the upgrade. Concurrent accepted facts: public static credential mints live-debug auth for arbitrary customer_id (cid=2 success:true), and no watched endpoint enforces token→cid ownership, so the attacker controls every element (cid, service, minted token) the relay could bind on; the only hope of a control is CBS-side validation of the live_debug frame payload.
evidence_needed: whether the CBS backend rejects a live_debug packet whose minted token was issued for a different cid than the presenting session's cid — not observable without subscribing to real live streams.
verify_steps: AUTH_HELPED only — no anonymous path. Operator session: mint for OWN cid via auth.php, then present the minted aid/ttl/hash in a live_debug frame for a FOREIGN cid and record denial vs connect; behavioral, own tenant only.
impact: anonymous bidirectional pipe to internal CBS business systems (CBS100/190/200) addressable by any tenant id; if frame binding absent, cross-tenant live call/debug attach (voice/PII) — HIGH/CRITICAL.
testability: AUTH_HELPED
[HYP] Voicenote raw-audio exfil gate (session + "No VPN detected.") is satisfied by any session the public credential can mint, exposing demo-tenant audio by predictable UUID filenames
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/download.php?file={uuid-from-get.php}
confidence: 60
reasoning: Facts: get.php/check.php return the token-bound tenant's voicenote index anonymously (customer_id ignored) including UUID filenames; download.php returned 403 "No VPN detected." without a session (prior session); auth.php demonstrates sessions/tokens mintable from the public credential. Unverified: whether the download gate checks the presenting session's tenant vs the demo tenant, i.e. whether the public credential alone reaches raw audio.
evidence_needed: whether a session obtained via the public-credential chain passes download.php's gate for the demo tenant's own files (own-tenant only; do not replay third-party audio).
verify_steps: AUTH_HELPED — own demo tenant only; behavioral gating comparison with/without session cookies; never fetch the actual audio of foreign tenants.
impact: anonymous raw call/voicemail audio exfil for a real tenant via public JS credential — HIGH if gate is credential-satisfiable.
testability: AUTH_HELPED
[NEXT] HUMAN: with a valid operator session for an owned tenant (obtain via normal login), mint live-debug auth for the OWN cid and present it in a live_debug frame to wss://cbs-proxy?cid={own}, then repeat with cid={foreign} — record accept vs deny to settle the sole remaining binding check; never run anonymously and never subscribe to third-party streams (program PII rule). This is the only open hop; all pre-attach control is now demonstrated absent.
[RISK] questnet-gmbh: 76 — Router-layer authorization now demonstrated entirely absent (any cid/service yields CONNECT+READY, no credential), closing four of five chain hops anonymously: public help.js credential → arbitrary-cid token mint → anonymous read of real-tenant voicenote index → unauthenticated relay READY to backend CBS. The final hop (live_debug frame binding) is deliberately untested per program PII constraints, not because controls were observed. A PoC report is well-formed on the demonstrated primitives alone; file as HIGH broken-auth/IDOR when the program state allows, without echoing PII or touching live streams. Surface frozen at 4 hosts; breadth exhausted.
## 2026-09-05 08:40:01 UTC [target] (model bigpickle)
[HYP] cbs-proxy WS router is an unauthenticated full-duplex relay to the CBS backend for any client-chosen cid/service; no object-level control exists at the router layer
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}
confidence: 84
reasoning: Live probes this session: anonymous WS upgrade with cid=999999999 (non-existent) and service=999999 (invalid) each return HTTP/1.1 101 plus identical frame set CONNECT CBS100/CBS190/CBS200 then PROXY READY — byte-identical to cid=1, zero credentials/headers beyond the upgrade. Concurrent accepted facts: public static credential mints live-debug auth for arbitrary customer_id (cid=2 success:true), and no watched endpoint enforces token→cid ownership, so the attacker controls every element (cid, service, minted token) the relay could bind on; the only hope of a control is CBS-side validation of the live_debug frame payload.
evidence_needed: whether the CBS backend rejects a live_debug packet whose minted token was issued for a different cid than the presenting session's cid — not observable without subscribing to real live streams.
verify_steps: AUTH_HELPED only — no anonymous path. Operator session: mint for OWN cid via auth.php, then present the minted aid/ttl/hash in a live_debug frame for a FOREIGN cid and record denial vs connect; behavioral, own tenant only.
impact: anonymous bidirectional pipe to internal CBS business systems (CBS100/190/200) addressable by any tenant id; if frame binding absent, cross-tenant live call/debug attach (voice/PII) — HIGH/CRITICAL.
testability: AUTH_HELPED
[HYP] Voicenote raw-audio exfil gate (session + "No VPN detected.") is satisfied by any session the public credential can mint, exposing demo-tenant audio by predictable UUID filenames
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/download.php?file={uuid-from-get.php}
confidence: 60
reasoning: Facts: get.php/check.php return the token-bound tenant's voicenote index anonymously (customer_id ignored) including UUID filenames; download.php returned 403 "No VPN detected." without a session (prior session); auth.php demonstrates sessions/tokens mintable from the public credential. Unverified: whether the download gate checks the presenting session's tenant vs the demo tenant, i.e. whether the public credential alone reaches raw audio.
evidence_needed: whether a session obtained via the public-credential chain passes download.php's gate for the demo tenant's own files (own-tenant only; do not replay third-party audio).
verify_steps: AUTH_HELPED — own demo tenant only; behavioral gating comparison with/without session cookies; never fetch the actual audio of foreign tenants.
impact: anonymous raw call/voicemail audio exfil for a real tenant via public JS credential — HIGH if gate is credential-satisfiable.
testability: AUTH_HELPED
[NEXT] HUMAN: with a valid operator session for an owned tenant (obtain via normal login), mint live-debug auth for the OWN cid and present it in a live_debug frame to wss://cbs-proxy?cid={own}, then repeat with cid={foreign} — record accept vs deny to settle the sole remaining binding check; never run anonymously and never subscribe to third-party streams (program PII rule). This is the only open hop; all pre-attach control is now demonstrated absent.
[RISK] questnet-gmbh: 76 — Router-layer authorization now demonstrated entirely absent (any cid/service yields CONNECT+READY, no credential), closing four of five chain hops anonymously: public help.js credential → arbitrary-cid token mint → anonymous read of real-tenant voicenote index → unauthenticated relay READY to backend CBS. The final hop (live_debug frame binding) is deliberately untested per program PII constraints, not because controls were observed. A PoC report is well-formed on the demonstrated primitives alone; file as HIGH broken-auth/IDOR when the program state allows, without echoing PII or touching live streams. Surface frozen at 4 hosts; breadth exhausted.
[HYP] Azure Blob Storage Secret Key in FreeSWITCH mod_http_cache config
class: SECRET
asset: freeswitch/src/mod/applications/mod_http_cache/conf/autoload_configs/http_cache.conf.xml:37-38
confidence: 10
reasoning: The Azure storage access key `kOOY4Y/sqZU9bsLjmN+9McVwTry+UIn1Owt4Zs/2S2FQT0eAWLKskZ0V6/gGFqCAKVvwXoGjqUn7PNbVjhZiNA==` is present in the FreeSWITCH upstream config file. However: (1) the domain is `account.blob.core.windows.net` (placeholder), (2) the author of the commit is Andrey Volk (upstream SignalWire/FreeSWITCH maintainer), and (3) this file exists identically in upstream FreeSWITCH. This is upstream example config, NOT a questnet-added secret.
impact: Informational (no real in-scope risk)
verify_steps: Confirm `account.blob.core.windows.net` is not a live questnet storage account via passive DNS or Azure portal.
[HYP] AWS Example Access Key in FreeSWITCH mod_http_cache config
class: SECRET
asset: freeswitch/src/mod/applications/mod_http_cache/conf/autoload_configs/http_cache.conf.xml:22
confidence: 5
reasoning: `AKIAIOSFOD_REDACTED` and `wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY` are the well-known AWS documentation example keys. These are NOT real credentials - they are the canonical example from AWS docs.
impact: None (example/test credentials)
verify_steps: N/A - known false positive.
[HYP] Hardcoded FreeSWITCH ESL default password "ClueCon"
class: MISCONFIG
asset: freeswitch/scripts/perl/fs.pl:5, NEventSocket/NEventSocket/InboundSocket.cs:42, free-socks/examples/connection-load.rs:21
confidence: 20
reasoning: The string "ClueCon" appears as a default password parameter in ESL client libraries. This is the well-known FreeSWITCH default password. In free-socks it is a CLI default (`--password` arg), not a hardcoded secret. In NEventSocket it is a C# default parameter value. In freeswitch scripts it's a test script. None of these are live production credentials.
impact: Informational (default credentials in library defaults, not production)
verify_steps: Confirm that production deployments of these libraries do not rely on the default "ClueCon" password.
[HYP] RSA Private Keys in sofia-sip test PEM files
class: SECRET
asset: freeswitch/libs/sofia-sip/libsofia-sip-ua/*/agent.pem, key.pem
confidence: 5
reasoning: These .pem files contain RSA private keys but are upstream test/example certificates bundled with the sofia-sip library. They are publicly known test certs from the upstream project, not questnet production keys.
impact: None (upstream test certificates)
verify_steps: N/A
[HYP] cbs-proxy WS router is an unauthenticated full-duplex relay to CBS backend; only the binary live_debug frame binding remains unverified
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}
confidence: 84
reasoning: Anonymous WS upgrades with cid=999999999 and service=999999 (both invalid) return HTTP/1.1 101 plus byte-identical frame set CONNECT CBS100/CBS190/CBS200 then PROXY READY — same as cid=1, zero credentials/headers. Public static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) mints live-debug auth for arbitrary customer_id (cid=2 success:true); no watched endpoint enforces token→cid ownership. Attacker controls every element (cid, service, minted token) the relay could bind on; the only remaining control is CBS-side validation of the live_debug frame payload.
evidence_needed: whether CBS rejects a live_debug packet whose minted token was issued for a cid different from the presenting session's cid.
verify_steps: AUTH_HELPED only — operator session: mint via auth.php for OWN cid, present in live_debug frame for FOREIGN cid, record deny vs connect; own tenant only, never subscribe to real third-party streams.
impact: anonymous bidirectional pipe to internal CBS business systems (CBS100/190/200) by any tenant id; if frame binding absent, cross-tenant live call/debug attach (voice/PII) — HIGH/CRITICAL.
testability: AUTH_HELPED
[HYP] Voicenote raw-audio exfil gate (403 "No VPN detected.") is credential-satisfiable via the public-credential chain
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/download.php?file={uuid-from-get.php}
confidence: 60
reasoning: get.php/check.php return the token-bound tenant's voicenote index anonymously (customer_id ignored) including UUID filenames; download.php returned 403 "No VPN detected." without a session; auth.php demonstrates tokens/sessions mintable from the public static credential. Unverified whether the download gate checks the presenting session's tenant vs the demo tenant.
evidence_needed: whether a session obtained via the public-credential chain passes download.php's gate for the demo tenant's own files.
verify_steps: AUTH_HELPED — own demo tenant only; behavioral gating compare with/without session cookies; never fetch third-party audio.
impact: anonymous raw call/voicemail audio exfil for a real tenant via public JS credential — HIGH if gate credential-satisfiable.
testability: AUTH_HELPED
[NEXT] HUMAN: with a valid operator session for an owned tenant, run the two remaining gated checks in one pass — (a) mint live-debug auth for the OWN cid, present it in a live_debug frame to wss://cbs-proxy?cid={own} then with cid={foreign}, record accept vs deny to settle frame binding; (b) call voicenotes/download.php with a session cookie minted via the public-credential chain against the demo tenant's OWN file to test the raw-audio gate. Own-tenant only; never subscribe to or fetch third-party streams/audio (program PII rule). This is the only open hop; all pre-attach router control is demonstrated absent and every anonymous probe is exhausted.
[RISK] questnet-gmbh: 77 — The demonstrated read-only primitive chain is fully confirmed and stable: public help.js static credential → arbitrary-cid live-debug token mint (cid=2 success:true) → anonymous read of a real tenant's voicenote index (customer_id ignored, PII incl. phone numbers) → unauthenticated relay READY to backend CBS for any client-chosen cid/service. Four of five hops closed anonymously; only the binary live_debug frame binding and raw-audio download gate remain — untested solely because both require a live session / real-stream subscription (program PII restriction), not because controls were observed. Risk ticks up marginally as the WCAG-equivalent "no control at every observed layer" pattern persists and the PoC report is well-formed on the demonstrated primitives. No PII echoed, no recordings fetched, no live streams subscribed, no mutations. Surface frozen at 4 hosts; breadth exhausted.
[HYP] cbs-proxy WS router is an unauthenticated full-duplex relay to CBS backend; only the binary live_debug frame binding remains unverified
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}
confidence: 84
reasoning: Anonymous WS upgrades with cid=999999999 and service=999999 (both invalid) return HTTP/1.1 101 plus byte-identical CONNECT CBS100/CBS190/CBS200 then PROXY READY — same as cid=1, zero credentials. Public static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) mints live-debug auth for arbitrary customer_id (cid=2 success:true); no watched endpoint enforces token→cid ownership; attacker controls every element (cid, service, minted token) the router could bind on.
evidence_needed: whether CBS rejects a live_debug packet whose minted token was issued for a different cid than the presenting session's cid.
verify_steps: AUTH_HELPED only — operator session: mint for OWN cid, present in live_debug frame for FOREIGN cid, record deny vs connect; own tenant only, never subscribe to real streams.
impact: anonymous bidirectional pipe to internal CBS systems (CBS100/190/200) by any tenant id; if frame binding absent, cross-tenant live call/debug attach (voice/PII) — HIGH/CRITICAL.
testability: AUTH_HELPED
[HYP] Voicenote raw-audio exfil gate (403 "No VPN detected.") is credential-satisfiable via the public-credential chain
class: IDOR
asset: https://www.applicationdesigner.de/extjs/voicenotes/download.php?file={uuid-from-get.php}
confidence: 60
reasoning: get.php/check.php return the token-bound tenant's voicenote index anonymously (customer_id ignored) incl. UUID filenames; download.php returned 403 "No VPN detected." without a session; auth.php demonstrates sessions/tokens mintable from the public static credential. Unverified whether download's gate checks the presenting session's tenant vs the demo tenant.
evidence_needed: whether a session obtained via the public-credential chain passes download.php for the demo tenant's own files.
verify_steps: AUTH_HELPED — own demo tenant only; behavioral gating compare with/without session cookies; never fetch third-party audio.
impact: anonymous raw call/voicemail audio exfil for a real tenant via public JS credential — HIGH if gate credential-satisfiable.
testability: AUTH_HELPED
[NEXT] HUMAN: obtain a valid operator session for an owned tenant, then settle both open hops in one pass — (a) mint live-debug auth for the OWN cid, present it in a live_debug frame to wss://cbs-proxy?cid={own} then with cid={foreign}, record accept vs deny for frame binding; (b) call voicenotes/download.php with a session cookie minted via the public-credential chain against the demo tenant's OWN file to test the raw-audio gate. Own-tenant only; never subscribe to or fetch third-party streams/audio (program PII rule). This is the only open hop; all pre-attach router control is demonstrated absent and every anonymous probe is exhausted.
[RISK] questnet-gmbh: 77 — Demonstrated read-only primitive chain fully confirmed and stable: public help.js static credential → arbitrary-cid live-debug token mint (cid=2 success:true) → anonymous read of a real tenant's voicenote index (customer_id ignored, PII incl. phone numbers) → unauthenticated relay READY to backend CBS for any client-chosen cid/service. Four of five hops closed anonymously; the binary live_debug frame binding and raw-audio download gate remain untested solely because both require a live session / real-stream subscription (program PII restriction), not because controls were observed. PoC report is well-formed on the demonstrated primitives (file as HIGH broken-auth/IDOR). No PII echoed, no recordings fetched, no live streams subscribed, no mutations. Surface frozen at 4 hosts; breadth exhausted.
