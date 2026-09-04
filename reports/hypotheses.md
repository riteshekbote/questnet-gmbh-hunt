# Hypotheses (ranked)

## RANKED HYPOTHESES 2026-09-02 21:47:55 UTC

## RANKED HYPOTHESES 2026-09-02 23:58:48 UTC

## RANKED HYPOTHESES 2026-09-03 04:08:01 UTC

## RANKED HYPOTHESES 2026-09-03 09:02:43 UTC

## RANKED HYPOTHESES 2026-09-03 13:26:40 UTC

## RANKED HYPOTHESES 2026-09-03 17:33:15 UTC

## RANKED HYPOTHESES 2026-09-03 20:03:02 UTC
- [70] api.live-manager.de: API versioning + debug endpoints on api.live-manager.de (from art/lead_nemotron3.txt)
- [65] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated / unauth-token CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=<observable-test> with explicit Upgrade/Sec-WebSocket headers (no au
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://auth.live-manager.de/.well-known/openid-configuration (HEAD first, then GET if 2xx) — confirms auth subdomain serves OIDC discovery and is no
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su

## RANKED HYPOTHESES 2026-09-03 22:32:24 UTC
- [70] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with explicit Upgrade/Sec-WebSocket headers (no auth) to confir
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su

## RANKED HYPOTHESES 2026-09-04 00:40:48 UTC
- [70] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- NEXT(hypotheses-bigpickle.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with explicit Upgrade/Sec-WebSocket headers (no auth) to confir
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su

## RANKED HYPOTHESES 2026-09-04 05:17:20 UTC
- [72] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend

## RANKED HYPOTHESES 2026-09-04 09:50:34 UTC
- [72] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://www.applicationdesigner.de/help.json — extract full endpoint/proxy model from ExtJS manifest to discover additional internal hosts behind cbs
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend

## RANKED HYPOTHESES 2026-09-04 14:17:33 UTC
- [72] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=test with Upgrade: websocket, Connection: Upgrade, Sec-WebSocket-Ver
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe → removed from active hypotheses.
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend

## RANKED HYPOTHESES 2026-09-04 17:50:53 UTC
- [72] wss://cbs-proxy.api.live-manager.de?origin=LiveDemo|LiveDebugger&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://www.applicationdesigner.de/help.json — extract full endpoint/proxy model from ExtJS manifest to discover additional internal hosts behind cbs
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe → removed from active hypotheses.
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect.
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe → removed from active hypotheses.

## RANKED HYPOTHESES 2026-09-04 20:10:34 UTC
- [85] chain: Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS (from art/lead_bigpickle.txt)
- [72] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token={publicstatic}&customerId=2 vs customerId=131727 (read-only, ~2 req @1rps, n
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 with explicit Upgrade: websocket, Connection: Upgrade, Sec-WebSo
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory.
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service — cross-tenant BOLA candidate (
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-04 22:19:45 UTC
- [88] https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token={pub-static}&customer_id={cid}&srn={srn}: Cross-tenant live-debug/call attach via auth.php mint (public credential) + cbs-proxy WS (from art/lead_bigpickle.txt)
- [72] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://www.applicationdesigner.de/help.json — extract full endpoint/proxy model from ExtJS manifest to discover additional internal hosts behind cbs
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
