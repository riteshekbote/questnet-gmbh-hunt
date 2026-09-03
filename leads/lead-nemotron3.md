## 2026-09-03 17:33:05 UTC [target] (model nemotron3)
## 2026-09-03 20:02:52 UTC [target] (model nemotron3)
[PRIO] api.live-manager.de,8.65,attack_surface=9,business_value=10,tech_exposure=9,gate_ease=8,cloud_surface=8,freshness=5
[PRIO] auth.live-manager.de,7.95,attack_surface=8,business_value=10,tech_exposure=8,gate_ease=7,cloud_surface=7,freshness=5
[PRIO] dev.live-manager.de,6.95,attack_surface=8,business_value=6,tech_exposure=8,gate_ease=6,cloud_surface=7,freshness=5
[PRIO] admin.live-manager.de,6.85,attack_surface=7,business_value=9,tech_exposure=7,gate_ease=5,cloud_surface=6,freshness=5
[PRIO] app.live-manager.de,6.55,attack_surface=7,business_value=8,tech_exposure=6,gate_ease=6,cloud_surface=6,freshness=5
[PRIO] dashboard.live-manager.de,6.10,attack_surface=6,business_value=8,tech_exposure=6,gate_ease=5,cloud_surface=6,freshness=5
[PRIO] billing.live-manager.de,5.85,attack_surface=6,business_value=9,tech_exposure=5,gate_ease=4,cloud_surface=5,freshness=5
[PRIO] applicationdesigner.de,5.75,attack_surface=6,business_value=7,tech_exposure=5,gate_ease=6,cloud_surface=5,freshness=5
[HYP] API versioning + debug endpoints on api.live-manager.de
class: MISCONFIG
asset: api.live-manager.de
confidence: 70
reasoning: Wildcard DNS suggests API behind CDN; versioned paths (/api/v1, /api/v2, /api/beta, /api/internal) and debug flags (?debug, ?test, ?dev) commonly exposed on API gateways. No auth on /health, /metrics, /actuator, /swagger, /openapi.json often leaks schema.
evidence_needed: 200 OK on /api/v1, /api/v2, /api/internal, /swagger.json, /openapi.json, /actuator/health with sensitive data
verify_steps: GET https://api.live-manager.de/api/v1; GET https://api.live-manager.de/api/v2; GET https://api.live-manager.de/api/internal; GET https://api.live-manager.de/swagger.json; GET https://api.live-manager.de/openapi.json; GET https://api.live-manager.de/actuator/health; GET https://api.live-manager.de/health; GET https://api.live-manager.de/metrics
impact: Full API schema enumeration → IDOR/BOLA candidates, mass assignment fields, hidden endpoints. Severity: HIGH if PII/money endpoints exposed.
testability: PASSIVE
[HYP] OAuth/OIDC misconfiguration on auth.live-manager.de
class: AUTH
asset: auth.live-manager.de
confidence: 65
reasoning: Auth subdomain likely hosts OAuth/OIDC flows. Common flaws: redirect_uri validation bypass (open redirect → code theft), state parameter missing/weak, PKCE downgrade, implicit flow enabled, token endpoint leaking refresh tokens, /userinfo over-disclosure.
evidence_needed: 302 redirect to arbitrary redirect_uri; missing state enforcement; token response with refresh_token on public client; /userinfo returning email/roles without scope check
verify_steps: GET https://auth.live-manager.de/.well-known/openid-configuration; GET https://auth.live-manager.de/authorize?client_id=test&redirect_uri=https://evil.com&response_type=code; GET https://auth.live-manager.de/authorize?client_id=test&redirect_uri=https://evil.com&response_type=code&state=fixed; POST https://auth.live-manager.de/token with grant_type=authorization_code&code=...&redirect_uri=https://evil.com
impact: ATO via code theft (redirect_uri bypass) or token leakage. Severity: CRITICAL.
testability: PASSIVE
[HYP] Debug/test endpoints on dev.live-manager.de / staging.live-manager.de
class: MISCONFIG
asset: dev.live-manager.de
confidence: 60
reasoning: Dev/staging environments often have relaxed auth, debug endpoints, test users, Swagger UI enabled, GraphQL introspection, fake billing flows. Wildcard DNS means they share CDN but may have different path routing.
evidence_needed: 200 on /swagger-ui, /graphql (introspection), /actuator/env, /h2-console, test credentials working, billing sandbox with real logic
verify_steps: GET https://dev.live-manager.de/swagger-ui.html; GET https://dev.live-manager.de/graphql with introspection query; GET https://dev.live-manager.de/actuator/env; GET https://dev.live-manager.de/h2-console; GET https://staging.live-manager.de/swagger-ui.html; GET https://staging.live-manager.de/graphql
impact: Full API access, PII exposure, business logic bypass (fake payments). Severity: HIGH.
testability: PASSIVE
[PARKED] API versioning + debug endpoints on api.live-manager.de: Host `api.live-manager.de` not in inventory — may not exist as separate subdomain; API paths likely under `app.live-manager.de/api/*` or `live-manager.de/api/*`. Verify host existence first.
[PARKED] OAuth/OIDC misconfiguration on auth.live-manager.de: Host `auth.live-manager.de` is in inventory but passive recon shows 0 live HTTP — may be wildcard-only. Need to confirm it serves distinct content vs wildcard.
[PARKED] Debug/test endpoints on dev.live-manager.de / staging.live-manager.de: Both in inventory but 0 live HTTP confirmed. Wildcard filtering suggests they resolve to same CDN IP — may not have distinct content.
[FINAL] No surviving hypotheses with confidence ≥40 AND verifiable host. All three require live host confirmation first.
[NEXT] PROBE: GET https://auth.live-manager.de/.well-known/openid-configuration (HEAD first, then GET if 2xx) — confirms auth subdomain serves OIDC discovery and is not wildcard-mirror.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists. Attack surface is path-based behind CDN.
[RISK] questnet-gmbh: 35 — Wildcard-dominated DNS surface with 0 confirmed live HTTP endpoints. Real risk depends entirely on path-based API/auth endpoints behind CDN. No evidence of exposed vulnerabilities yet; passive-only phase yields low confidence. Risk increases significantly if any auth/api endpoint responds with debug/OIDC/swagger data.
## 2026-09-03 22:32:14 UTC [target] (model nemotron3)
[NEW] cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
[CHANGED] applicationdesigner.de / www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
[CHANGED] live-manager.de / www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
[CHANGED] dev.applicationdesigner.de live but 403 internal-only page; dev.live-manager.de / staging.live-manager.de / test.live-manager.de / portal.live-manager.de / account.live-manager.de do not serve HTTP.
[PRIO] cbs-proxy.api.live-manager.de,8.40,attack_surface=9,business_value=10,tech_exposure=9,gate_ease=10,cloud_surface=8,freshness=5
[PRIO] www.live-manager.de,7.10,attack_surface=7,business_value=10,tech_exposure=7,gate_ease=6,cloud_surface=6,freshness=5
[PRIO] www.applicationdesigner.de,6.55,attack_surface=8,business_value=7,tech_exposure=8,gate_ease=6,cloud_surface=5,freshness=5
[PRIO] auth.live-manager.de,5.95,attack_surface=6,business_value=10,tech_exposure=6,gate_ease=5,cloud_surface=6,freshness=5
[PRIO] dev.applicationdesigner.de,5.35,attack_surface=6,business_value=6,tech_exposure=6,gate_ease=4,cloud_surface=5,freshness=5
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}
confidence: 70
reasoning: help.js builds WS URL with client-side placeholders (cid=a.context.customerId, service=service_number) and passes origin=LiveDemo/LiveDebugger. Anonymous WS upgrade succeeded with zero credentials, emitting proxy CONNECT frames to CBS100/CBS190/CBS200 then READY. No token/Authorization was required or validated in observed handshake; cid/service scoping enforcement is unverified.
evidence_needed: proxy enforces authenticated session token tied to claimed cid, and requesting foreign cid is denied; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: WS upgrade to wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid=1&service=<test> observe CONNECT/READY frame set; probe with clearly foreign/unowned cid and note whether READY/data still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debugging (PII/voice data) — HIGH if unauthenticated actor can enumerate cid.
testability: PASSIVE (handshake reachable anonymously; auth-scoping confirmation requires valid session = AUTH_HELPED/HUMAN)
[HYP] ExtJS help app on www.applicationdesigner.de exposes internal CBS proxy endpoints and backend hostnames
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (ExtJS help.js) and /help.json, /resources.help/*
confidence: 55
reasoning: ExtJS help app (Sencha Cmd, app uuid 3342eca3-...) ships help.js containing live backend host wss://cbs-proxy.api.live-manager.de and internal Proxy/Endpoint model. The documented help manifest (help.json) and resources (resources.help/) are publicly served, which can enumerate internal host/proxy names beyond the already-confirmed one.
evidence_needed: further unauth endpoints/hosts listed in served ExtJS app and whether any expose data or allow on-behalf-of calls.
verify_steps: GET /help.json, /resources.help/*, and app JS to list proxy/endpoint URLs (read-only); cross-reference found hostnames against scope before any further probe.
impact: surface/asset discovery and potential unauthorized internal call relay — MEDIUM.
testability: PASSIVE (read-only asset enumeration)
[HYP] OAuth/OIDC misconfiguration on auth.live-manager.de
class: AUTH
asset: auth.live-manager.de
confidence: 45
reasoning: Auth subdomain in inventory but passive recon shows 0 live HTTP — may be wildcard-only. If it serves distinct content, common flaws: redirect_uri validation bypass (open redirect → code theft), state parameter missing/weak, PKCE downgrade, implicit flow enabled, token endpoint leaking refresh tokens, /userinfo over-disclosure.
evidence_needed: 302 redirect to arbitrary redirect_uri; missing state enforcement; token response with refresh_token on public client; /userinfo returning email/roles without scope check.
verify_steps: HEAD https://auth.live-manager.de/.well-known/openid-configuration; if 2xx, GET same; then GET https://auth.live-manager.de/authorize?client_id=test&redirect_uri=https://evil.com&response_type=code to test redirect_uri validation.
impact: ATO via code theft (redirect_uri bypass) or token leakage. Severity: CRITICAL.
testability: PASSIVE (needs live host confirmation first)
[PARKED] OAuth/OIDC misconfiguration on auth.live-manager.de: Host auth.live-manager.de is in inventory but passive recon shows 0 live HTTP — may be wildcard-only. Need to confirm it serves distinct content vs wildcard mirror before investing confidence.
[FINAL] 1. wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (70)
[FINAL] 2. www.applicationdesigner.de/docs.php: ExtJS help app exposes internal CBS proxy endpoints and backend hostnames (55)
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key: <base64> headers (no auth) to confirm the READY frame set and whether cid/service are validated pre-connect or merely forward-connected; ~1 req, read-only handshake, no data subscription.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists. Attack surface is path-based behind CDN.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); confirmed live surface is far smaller than the 22-host inventory suggested (only www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de responding), limiting breadth but concentrating value on the CBS proxy and customer portal auth flows.
[NEW] cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
[CHANGED] applicationdesigner.de / www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
[CHANGED] live-manager.de / www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
[CHANGED] dev.applicationdesigner.de live but 403 internal-only page; dev.live-manager.de / staging.live-manager.de / test.live-manager.de / portal.live-manager.de / account.live-manager.de do not serve HTTP.
[PRIO] cbs-proxy.api.live-manager.de,8.40,attack_surface=9,business_value=10,tech_exposure=9,gate_ease=10,cloud_surface=8,freshness=5
[PRIO] www.live-manager.de,7.10,attack_surface=7,business_value=10,tech_exposure=7,gate_ease=6,cloud_surface=6,freshness=5
[PRIO] www.applicationdesigner.de,6.55,attack_surface=8,business_value=7,tech_exposure=8,gate_ease=6,cloud_surface=5,freshness=5
[PRIO] auth.live-manager.de,5.95,attack_surface=6,business_value=10,tech_exposure=6,gate_ease=5,cloud_surface=6,freshness=5
[PRIO] dev.applicationdesigner.de,5.35,attack_surface=6,business_value=6,tech_exposure=6,gate_ease=4,cloud_surface=5,freshness=5
[HYP] Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription
class: IDOR
asset: wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}
confidence: 70
reasoning: help.js builds WS URL with client-side placeholders (cid=a.context.customerId, service=service_number) and passes origin=LiveDemo/LiveDebugger. Anonymous WS upgrade succeeded with zero credentials, emitting proxy CONNECT frames to CBS100/CBS190/CBS200 then READY. No token/Authorization was required or validated in observed handshake; cid/service scoping enforcement is unverified.
evidence_needed: proxy enforces authenticated session token tied to claimed cid, and requesting foreign cid is denied; without that, cross-tenant live call/debug stream subscription is possible.
verify_steps: WS upgrade to wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid=1&service=<test> observe CONNECT/READY frame set; probe with clearly foreign/unowned cid and note whether READY/data still returned. Do NOT subscribe to live customer call data.
impact: cross-tenant exposure of customer business-system call streams / live debugging (PII/voice data) — HIGH if unauthenticated actor can enumerate cid.
testability: PASSIVE (handshake reachable anonymously; auth-scoping confirmation requires valid session = AUTH_HELPED/HUMAN)
[HYP] ExtJS help app on www.applicationdesigner.de exposes internal CBS proxy endpoints and backend hostnames
class: MISCONFIG
asset: https://www.applicationdesigner.de/docs.php (ExtJS help.js) and /help.json, /resources.help/*
confidence: 55
reasoning: ExtJS help app (Sencha Cmd, app uuid 3342eca3-...) ships help.js containing live backend host wss://cbs-proxy.api.live-manager.de and internal Proxy/Endpoint model. The documented help manifest (help.json) and resources (resources.help/) are publicly served, which can enumerate internal host/proxy names beyond the already-confirmed one.
evidence_needed: further unauth endpoints/hosts listed in served ExtJS app and whether any expose data or allow on-behalf-of calls.
verify_steps: GET /help.json, /resources.help/*, and app JS to list proxy/endpoint URLs (read-only); cross-reference found hostnames against scope before any further probe.
impact: surface/asset discovery and potential unauthorized internal call relay — MEDIUM.
testability: PASSIVE (read-only asset enumeration)
[HYP] OAuth/OIDC misconfiguration on auth.live-manager.de
class: AUTH
asset: auth.live-manager.de
confidence: 45
reasoning: Auth subdomain in inventory but passive recon shows 0 live HTTP — may be wildcard-only. If it serves distinct content, common flaws: redirect_uri validation bypass (open redirect → code theft), state parameter missing/weak, PKCE downgrade, implicit flow enabled, token endpoint leaking refresh tokens, /userinfo over-disclosure.
evidence_needed: 302 redirect to arbitrary redirect_uri; missing state enforcement; token response with refresh_token on public client; /userinfo returning email/roles without scope check.
verify_steps: HEAD https://auth.live-manager.de/.well-known/openid-configuration; if 2xx, GET same; then GET https://auth.live-manager.de/authorize?client_id=test&redirect_uri=https://evil.com&response_type=code to test redirect_uri validation.
impact: ATO via code theft (redirect_uri bypass) or token leakage. Severity: CRITICAL.
testability: PASSIVE (needs live host confirmation first)
[PARKED] OAuth/OIDC misconfiguration on auth.live-manager.de: Host auth.live-manager.de is in inventory but passive recon shows 0 live HTTP — may be wildcard-only. Need to confirm it serves distinct content vs wildcard mirror before investing confidence.
[FINAL] 1. wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (70)
[FINAL] 2. www.applicationdesigner.de/docs.php: ExtJS help app exposes internal CBS proxy endpoints and backend hostnames (55)
[NEXT] PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Version: 13, Sec-WebSocket-Key: <base64> headers (no auth) to confirm the READY frame set and whether cid/service are validated pre-connect or merely forward-connected; ~1 req, read-only handshake, no data subscription.
[LEARN] ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — candidates for cross-tenant BOLA.
[LEARN] REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
[LEARN] REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain surface exists. Attack surface is path-based behind CDN.
[RISK] questnet-gmbh: 55 — One confirmed in-scope live WebSocket proxy with anonymous handshake to customer business systems (high-value BOLA candidate); confirmed live surface is far smaller than the 22-host inventory suggested (only www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de responding), limiting breadth but concentrating value on the CBS proxy and customer portal auth flows.
