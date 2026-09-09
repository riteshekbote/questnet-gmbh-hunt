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

## RANKED HYPOTHESES 2026-09-05 00:18:43 UTC
- [85] chain: Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS (from art/lead_nemotron3.txt)
- [72] wss://cbs-proxy.api.live-manager.de/?origin=<ClientType>&cid={cid}&service={service}: WS-side binding check absent: anonymous cbs-proxy upgrade accepts any client-supplied cid/service (no token binding on binary frames) (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): RAG: query corpus for any earlier valid-operator cbs-proxy handshake transcript (origin/cid/service frame exchange) before spending the remaining AUTH_HELPED co
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://www.applicationdesigner.de/help.json — extract full endpoint/proxy model from ExtJS manifest to discover additional internal hosts behind cbs
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 04:44:49 UTC
- [85] chain: Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS (from art/lead_nemotron3.txt)
- [84] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: cbs-proxy WS router is an unauthenticated full-duplex relay to the CBS backend for any client-chosen cid/service; no object-level control exists at the router layer (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant (obtain via normal login), mint live-debug auth for the OWN cid and present it in a live_debug frame to
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 08:42:00 UTC
- [85] chain: Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS (from art/lead_nemotron3.txt)
- [84] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: cbs-proxy WS router is an unauthenticated full-duplex relay to the CBS backend for any client-chosen cid/service; no object-level control exists at the router layer (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant (obtain via normal login), mint live-debug auth for the OWN cid and present it in a live_debug frame to
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 12:09:45 UTC
- [85] chain: Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 15:31:48 UTC
- [85] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding an unbound cbs-proxy WS frame layer (from art/lead_bigpickle.txt)
- [85] chain: Cross-tenant live-debug stream subscription via public-credential auth.php mint + cbs-proxy WS (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 17:50:12 UTC
- [85] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding an unbound cbs-proxy WS frame layer (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 19:35:24 UTC
- [85] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding unbound cbs-proxy WS frame layer (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with Upgrade: websocket, Connection: Upgrade, Sec-WebSoc
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-05 21:57:47 UTC
- [90] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding unbound cbs-proxy WS frame layer (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-06 03:56:36 UTC
- [90] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding unbound cbs-proxy WS frame layer (from art/lead_nemotron3.txt)
- [85] chain: Cross-tenant live-debug chain via public-credential auth.php mint feeding unbound cbs-proxy WS relay (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: single 1-rps GET series under https://www.applicationdesigner.de/AIDesigner/backend/ (config.php, config_coding.php confirmed 200; probe index.php, confi
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token (unchange
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses

## RANKED HYPOTHESES 2026-09-06 08:43:18 UTC
- [85] chain: Cross-tenant live-debug chain via public-credential auth.php mint feeding unbound cbs-proxy WS relay (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant, settle the two remaining open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token (unchange
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f

## RANKED HYPOTHESES 2026-09-06 12:28:37 UTC
- [90] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding unbound cbs-proxy WS frame layer (from art/lead_nemotron3.txt)
- [85] chain: Cross-tenant live-debug chain via public-credential auth.php mint feeding unbound cbs-proxy WS relay (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: with a valid operator session for an owned tenant, settle the two remaining open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token (unchange
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 

## RANKED HYPOTHESES 2026-09-06 15:44:54 UTC
- [90] chain: Cross-tenant live-debug/call attach via public-credential auth.php mint feeding unbound cbs-proxy WS frame layer (from art/lead_nemotron3.txt)
- [75] cbs-proxy.api.live-manager.de: LiveDebugger token is minted-but-unbound: same token passes cbs-proxy for cid=131727 and foreign cids, proving BOLA reachability is client-controlled (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: settlement of the last open hop on the driver chain, demo-tenant-sanctioned and read-only, <=1 rps. (1) GET https://www.applicationdesigner.de/extjs/live
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 

## RANKED HYPOTHESES 2026-09-06 17:59:32 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- [75] cbs-proxy.api.live-manager.de: LiveDebugger token is minted-but-unbound: same token passes cbs-proxy for cid=131727 and foreign cids, proving BOLA reachability is client-controlled (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: settlement of the last open hop on the driver chain, demo-tenant-sanctioned and read-only, <=1 rps. (1) GET https://www.applicationdesigner.de/extjs/live
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 

## RANKED HYPOTHESES 2026-09-06 20:20:28 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- [92] cbs-proxy.api.live-manager.de: Cross-tenant CBS live-debug attach: minted token is unbound to claimed cid at cbs-proxy — positively confirmed vs demo tenant (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: read-only confirmation of the voicenote metadata scope (the second already-VALID finding, extend to file-level metadata without touching raw audio): GET 
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing; no keys; dispatch
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} — AIDesigner dispatch NOT static-credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 

## RANKED HYPOTHESES 2026-09-06 22:13:06 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- [92] cbs-proxy.api.live-manager.de: Cross-tenant CBS live-debug attach: minted token is unbound to claimed cid at cbs-proxy — positively confirmed vs demo tenant (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: read-only confirmation of the voicenote metadata scope (the second already-VALID finding, extend to file-level metadata without touching raw audio): GET 
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing; no keys; dispatch
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} — AIDesigner dispatch NOT static-credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 

## RANKED HYPOTHESES 2026-09-07 00:06:54 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- [55] https://www.applicationdesigner.de/extjs/voicenotes/download.php?file={uuid-from-get.php}: voicenotes/download.php raw-audio gate is credential-satisfiable via the public-credential session chain (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: read-only confirmation of the voicenote metadata scope (the second already-VALID finding, extend to file-level metadata without touching raw audio): GET 
- NEXT(hypotheses-nemotron3.txt): HUMAN: with a valid operator session for an owned tenant, settle both open hops in one pass — (a) mint live-debug auth for the OWN cid via auth.php, present it 
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing; no keys; dispatch
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} — AIDesigner dispatch NOT static-credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
- LEARN: CHANGED id@ www.applicationdesigner.de/extjs/voicenotes/: single read-only probe now returns `Not logged in` + `No VPN detected.` tech-info (was success:true an
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete vs demo-tenant control, byte-identical frames (unchanged).
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid mint via public static credential, no ownership check (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public bundle ships static credential + endpoint map (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: zero-auth LLM-routing JSON; dispatch gated (unchanged).
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using a 
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 

## RANKED HYPOTHESES 2026-09-07 04:58:12 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={customer_id}&service={service_number}: Unauthenticated CBS WebSocket proxy allows arbitrary customer_id cross-tenant subscription (from art/lead_nemotron3.txt)
- [55] https://www.applicationdesigner.de/extjs/voicenotes/download.php?file={uuid-from-get.php}: voicenotes/download.php raw-audio gate is credential-satisfiable via the public-credential session chain (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: read-only confirmation of the voicenote metadata scope (the second already-VALID finding, extend to file-level metadata without touching raw audio): GET 
- NEXT(hypotheses-nemotron3.txt): PROBE: clean read-only re-confirmation of voicenote metadata gate — GET https://www.applicationdesigner.de/extjs/voicenotes/check.php?token=<public-static-sha25
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing; no keys; dispatch
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} — AIDesigner dispatch NOT static-credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WS upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — cross-t
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid live-debug token mint via public static credential, success:true for f
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full LiveDebugger/CallBuilder/AIDesigner endpoint
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing; no keys; dispatch
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} — AIDesigner dispatch NOT static-credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de debug endpoints: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
- LEARN: CHANGED id@ www.applicationdesigner.de/extjs/voicenotes/: single read-only probe now returns `Not logged in` + `No VPN detected.` tech-info (was success:true an
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete vs demo-tenant control, byte-identical frames (unchanged).
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid mint via public static credential, no ownership check (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public bundle ships static credential + endpoint map (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: zero-auth LLM-routing JSON; dispatch gated (unchanged).
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using st
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb8
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 
- LEARN: CHANGED id@ www.applicationdesigner.de/extjs/voicenotes/: single read-only probe now returns `Not logged in` + `No VPN detected.` tech-info (was success:true an
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth token for arbitrary customer_id using st
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de: ExtJS help app (help.js, help.json, resources.help/*) publicly exposes internal CBS proxy endpoints and backend
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb8
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without the public demo credent
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: GET /?rs= not reflected/server-side redirected to external domain, so no anonymous open redirect
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: DEDICATED-DEEP.md confirms 8632 resolving hostnames all share CDN/wildcard IPs — no dedicated subdomain su
- LEARN: REJECTED api.live-manager.de debug endpoints: host does not resolve; no surface to probe — removed from active hypotheses
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — system-prompt-ask.md/apply.md/.md/-coding.md all 
- LEARN: CHANGED id@ www.applicationdesigner.de/extjs/voicenotes/: single read-only probe now returns `Not logged in` + `No VPN detected.` tech-info (was success:true an

## RANKED HYPOTHESES 2026-09-07 10:14:17 UTC
- [85] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [55] www.applicationdesigner.de/extjs/voicenotes/get.php|check.php?token=LIVE_DEMO_CUSTOMER_TOKEN&customer_id={cid}: Voicenote metadata surface now VPN-gated (was anonymous token-scoped) (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: read-only confirmation of the voicenote metadata scope (the second already-VALID finding, extend to file-level metadata without touching raw audio): GET 
- NEXT(hypotheses-nemotron3.txt): PROBE: WS upgrade to cbs-proxy.api.live-manager.de with arbitrary cid — `wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100` — confi
- LEARN: CHANGED id@ www.applicationdesigner.de/extjs/voicenotes/: single read-only probe now returns `Not logged in` + `No VPN detected.` tech-info (was success:true an
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete vs demo-tenant control, byte-identical frames (unchanged).
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid mint via public static credential, no ownership check (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public bundle ships static credential + endpoint map (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: zero-auth LLM-routing JSON; dispatch gated (unchanged).
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: CHANGED id@ www.applicationdesigner.de/extjs/voicenotes/: single read-only probe now returns `Not logged in` + `No VPN detected.` tech-info (was success:true an
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cre
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 

## RANKED HYPOTHESES 2026-09-07 16:03:12 UTC
- [85] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [55] www.applicationdesigner.de/extjs/agent/get_agent_token.php?token=<pub-static: AI Designer agent-token endpoint mints per-cid tokens for arbitrary customerId via public static credential (parallel to auth.php) (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token=<public-static sha256 8d2faac1…>&customerId=131727 then customerId=2; compar
- NEXT(hypotheses-nemotron3.txt): PROBE: WS upgrade to cbs-proxy.api.live-manager.de with arbitrary cid — `wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100` — confi
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete vs demo-tenant control, byte-identical frames (unchanged).
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid mint via public static credential, no ownership check; success:true fo
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: re-confirmed cross-tenant un-scoped index, NOT VPN-gated; "No VPN detected" was placehold
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public bundle ships static credential + endpoint map (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: zero-auth LLM-routing JSON; dispatch gated (unchanged).
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php: AIDesigner dispatch NOT static-credential-satisfiable (unchanged).
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped (unchanged).
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: no secrets-bearing anonymous siblings (unchanged).
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cre
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-07 19:51:51 UTC
- [92] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane binding for arbitrary cid (live-closure remainder) (from art/lead_bigpickle.txt)
- [90] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customerId=
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatr
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-07 22:43:03 UTC
- [92] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane binding for arbitrary cid (live-closure remainder) (from art/lead_bigpickle.txt)
- [90] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customerId=
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customerId=
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatr
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete vs demo-tenant control, byte-identical frames (unchanged).
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous per-cid mint via public static credential, no ownership check; success:true fo
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: re-confirmed cross-tenant un-scoped index, NOT VPN-gated; "No VPN detected" was placehold
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public bundle ships static credential + endpoint map (unchanged).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: zero-auth LLM-routing JSON; dispatch gated (unchanged).
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php: AIDesigner dispatch NOT static-credential-satisfiable (unchanged).
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged).
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged).
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged).
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-08 00:44:14 UTC
- [90] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [55] www.applicationdesigner.de/extjs/livedebugger/auth.php?token=<pub: auth.php per-cid token mint status (contested after VPN-gate signal) (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customer_id=131
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://www.applicationdesigner.de/extjs/agent/get_agent_token.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customerId=
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-08 05:51:14 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane binds minted foreign-cid token to real tenant frames (from art/lead_bigpickle.txt)
- [90] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: hand operator the end-to-end POC for frame-binding — (1) GET auth.php?token=3498fkgkds…(sha256 8d2faac1…)&customer_id=2&srn=100 → mint f12731c3…; (2) WS 
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-08 11:01:01 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane binds minted foreign-cid token to real tenant frames (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET `https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customer_id=13
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete, byte-identical frames for demo vs foreign cid, confirmed still live (426 Up
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: re-confirmed cross-tenant, NOT VPN-gated with real public demo token — unchanged.
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: session-gated, no anonymous mint, byte-identical Zugriff verweigert for both cids — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate persistent — anonymous mint BLOCKED, contested status persists pending clean re-
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints — unchanged.
- LEARN: REJECTED api.live-manager.de: host non-resolving — unchanged.
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-08 15:08:55 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane binds minted foreign-cid token to real tenant frames (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET `https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customer_id=13
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: cross-tenant BOLA transport-complete, byte-identical frames for demo vs foreign cid, confirmed still live (426 Up
- LEARN: ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: re-confirmed cross-tenant, NOT VPN-gated with real public demo token — unchanged.
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: session-gated, no anonymous mint, byte-identical Zugriff verweigert for both cids — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate persistent — anonymous mint BLOCKED, contested status persists pending clean re-
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints — unchanged.
- LEARN: REJECTED api.live-manager.de: host non-resolving — unchanged.
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-08 18:50:36 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-08 21:48:25 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane frame binding for foreign-cid minted token (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: `GET https://www.applicationdesigner.de/extjs/flexlist/getFields.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&flexlist_id=1
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-09 00:00:33 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane frame binding for foreign-cid minted token (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: operator holds two tenant accounts — create one flexlist under a second owned tenant, then `GET https://www.applicationdesigner.de/extjs/flexlist/getDeta
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted (HTTP 200 `{"success":true,…}`), 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped — 10 flexlists, all customer_id=131727 (demo tenant only); no f
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant data read NOT observed anonymous — no foreign flexlist_id known without out-o
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-09 04:32:30 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane frame binding for foreign-cid minted token (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: `GET https://www.applicationdesigner.de/extjs/voicenotes/details.php?token=3498fkgkds458g35h9g835npz98qq4839kajlfhg38963a98z35h898E3DFG38d3&customer_id=1
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted, reads resolve live per-id data; 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped, all customer_id=131727; global autoincrement id space (138–345
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant NOT observed — no foreign flexlist_id known; needs operator with second owned
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted (HTTP 200 `{"success":true,…}`), 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped — 10 flexlists, all customer_id=131727 (demo tenant only); no f
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant data read NOT observed anonymous — no foreign flexlist_id known without out-o
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 

## RANKED HYPOTHESES 2026-09-09 09:16:01 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane frame binding for foreign-cid minted token (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: operator creates one flexlist under a second owned tenant, then `GET https://www.applicationdesigner.de/extjs/flexlist/getDetails.php?token=3498fkgkds458
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/details.php: per-record read hierarchy-checked on customer_id+log_id (byte-identical "Kundennumme
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/check.php: demo index empty this cycle (total=0,max_id=0).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted, reads resolve live per-id data; 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped, all customer_id=131727; global autoincrement id space (138–345
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant NOT observed anonymous — no foreign flexlist_id known; needs operator with se
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted (HTTP 200 `{"success":true,…}`), 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped — 10 flexlists, all customer_id=131727 (demo tenant only); no f
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant data read NOT observed anonymous — no foreign flexlist_id known without out-o
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-09 13:52:59 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane frame binding for foreign-cid minted token (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: operator creates one flexlist under a second owned tenant, then `GET https://www.applicationdesigner.de/extjs/flexlist/getDetails.php?token=3498fkgkds458
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/details.php: per-record read hierarchy-checked on customer_id+log_id (byte-identical "Kundennumme
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/check.php: demo index empty this cycle (total=0,max_id=0).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted, reads resolve live per-id data; 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped, all customer_id=131727; global autoincrement id space (138–345
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant NOT observed anonymous — no foreign flexlist_id known; needs operator with se
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted (HTTP 200 `{"success":true,…}`), 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped — 10 flexlists, all customer_id=131727 (demo tenant only); no f
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant data read NOT observed anonymous — no foreign flexlist_id known without out-o
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/details.php: per-record read hierarchy-checked on customer_id+log_id (byte-identical "Kundennumme
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-09 17:45:28 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDebugger&cid={cid}&service={service}&token={minted}: cbs-proxy data-plane frame binding for foreign-cid minted token (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/details.php: per-record read hierarchy-checked on customer_id+log_id (byte-identical "Kundennumme
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/check.php: demo index empty this cycle (total=0,max_id=0).
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted, reads resolve live per-id data; 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped, all customer_id=131727; global autoincrement id space (138–345
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant NOT observed anonymous — no foreign flexlist_id known; needs operator with se
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: session-gated, byte-identical "Zugriff verweigert" for both cids; sole untested para
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — anonymous mint BLOCKED.
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential + full endpoint map including /api/callbuilder/ pro
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing; no keys; dispatch
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} — AIDesigner dispatch NOT static-credent
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted (HTTP 200 `{"success":true,…}`), 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped — 10 flexlists, all customer_id=131727 (demo tenant only); no f
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant data read NOT observed anonymous — no foreign flexlist_id known without out-o
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/details.php: per-record read hierarchy-checked on customer_id+log_id (byte-identical "Kundennumme
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch

## RANKED HYPOTHESES 2026-09-09 20:51:36 UTC
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: cbs-proxy data-plane cross-tenant frame binding (chain capstone) (from art/lead_bigpickle.txt)
- [95] wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid={cid}&service={service}: Cross-tenant CBS WebSocket subscription via unauthenticated cid/service parameters (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: WS-upgrade GET to wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 with explicit Upgrade: websocket, Connection: Upgrade, S
- LEARN: ACCEPTED IDOR @ cbs-proxy.api.live-manager.de: anonymous WebSocket upgrade reaches backend CBS servers with client-supplied cid/service and no observed token — 
- LEARN: CHANGED AUTH @ www.applicationdesigner.de/extjs/livedebugger/auth.php: VPN gate deployed — now returns `Not logged in` + `No VPN detected` with public static cr
- LEARN: CHANGED→ACCEPTED IDOR @ www.applicationdesigner.de/extjs/voicenotes/check.php: VPN gate was placeholder-token artifact; re-probe with real public demo token sho
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/extjs/flexlist/getFields.php|getDetails.php: public static credential accepted (HTTP 200 `{"success":true,…}`), 
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/flexlist/getList.php: directory token-scoped — 10 flexlists, all customer_id=131727 (demo tenant only); no f
- LEARN: REJECTED (partial) IDOR @ www.applicationdesigner.de/extjs/flexlist/: cross-tenant data read NOT observed anonymous — no foreign flexlist_id known without out-o
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/agent/get_agent_token.php: no anonymous per-cid agent-token mint — HTTP 200 `{"success":false,"message":"Zugrif
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/extjs/voicenotes/details.php: per-record read hierarchy-checked on customer_id+log_id (byte-identical "Kundennumme
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/help.js: public ExtJS bundle ships static backend credential (LIVE_DEMO_CUSTOMER_TOKEN=3498fkgkds458g35h9g835npz
- LEARN: ACCEPTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatri
- LEARN: ACCEPTED CONTROL @ www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential 
- LEARN: REJECTED IDOR @ www.applicationdesigner.de/extjs/common/getCustomers.php: token-scoped — returns only demo customer 131727; no global tenant directory (unchange
- LEARN: REJECTED AUTH @ www.live-manager.de rs param: no anonymous open redirect (unchanged)
- LEARN: REJECTED wildcard-subdomain-enum @ *.live-manager.de: 8632 hostnames, 0 dedicated endpoints (unchanged)
- LEARN: REJECTED api.live-manager.de: host non-resolving (unchanged)
- LEARN: REJECTED MISCONFIG @ www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe closed 2026-09-06 — no secrets-bearing anonymous sibling exists (unch
