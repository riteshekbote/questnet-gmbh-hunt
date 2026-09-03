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
