# Questnet GmbH inventory (discovery seed 2026-09-02)
# NOTE: hosts below are discovery candidates from passive DNS/CT; confirm in-scope vs program scope before active testing.
account.live-manager.de
admin.live-manager.de
app.live-manager.de
applicationdesigner.de
auth.live-manager.de
billing.live-manager.de
dashboard.live-manager.de
dev.applicationdesigner.de
dev.live-manager.de
live-manager.de
login.live-manager.de
m.live-manager.de
mail.live-manager.de
my.live-manager.de
portal.live-manager.de
sso.live-manager.de
staging.live-manager.de
support.live-manager.de
test.live-manager.de
web.live-manager.de
www.applicationdesigner.de
www.live-manager.de

## PASSIVE RECON 2026-09-02 (read-only, non-intrusive)

> Recon observations only. These are NOT confirmed vulnerabilities; ownership/in-scope of each host must be confirmed against the program scope before any active testing. Hosts resolve + serve HTTP — investigation requires scoped authorization.

**Probed:** 22 hosts | **Live HTTP:** 0

| Host | Status | Server/Tech |
|---|---|---|

## 2026-09-02 21:47:55 UTC

## 2026-09-02 23:58:48 UTC

## 2026-09-03 04:08:01 UTC

## 2026-09-03 09:02:43 UTC

## 2026-09-03 13:26:40 UTC

## 2026-09-03 17:33:15 UTC

## 2026-09-03 20:03:02 UTC
- NEW cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
- CHANGED applicationdesigner.de/www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
- CHANGED live-manager.de/www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
- CHANGED dev.applicationdesigner.de live but 403 internal-only page; dev/staging/test/portal/account.live-manager.de do not serve HTTP.

## 2026-09-03 22:32:24 UTC
- NEW cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
- CHANGED applicationdesigner.de / www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
- CHANGED live-manager.de / www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
- CHANGED dev.applicationdesigner.de live but 403 internal-only page; dev.live-manager.de / staging.live-manager.de / test.live-manager.de / portal.live-manager.de / account.live-manager.de do not serve HTTP.
- NEW cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
- CHANGED applicationdesigner.de / www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
- CHANGED live-manager.de / www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
- CHANGED dev.applicationdesigner.de live but 403 internal-only page; dev.live-manager.de / staging.live-manager.de / test.live-manager.de / portal.live-manager.de / account.live-manager.de do not serve HTTP.

## 2026-09-04 00:40:48 UTC

## 2026-09-04 05:17:20 UTC
- NEW cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
- CHANGED www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
- CHANGED www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
- CHANGED dev.applicationdesigner.de live but 403 internal-only page; dev.live-manager.de / staging.live-manager.de / test.live-manager.de / portal.live-manager.de / account.live-manager.de do not serve HTTP.
- NEW auth.live-manager.de: inventory host with 0 live HTTP — likely wildcard mirror; needs live confirmation.
- NEW cbs-proxy.api.live-manager.de: WebSocket proxy (Ratchet/0.4.4) to backend CBS systems, IP 185.158.98.53 (in-scope /22), discovered via AppDesigner help.js; not in inventory.
- CHANGED www.applicationdesigner.de confirmed live (PHP/8.3.21, login.php/playground.php/docs.php ExtJS 7.8 app); prior recon reported "Live HTTP: 0".
- CHANGED www.live-manager.de confirmed live (IIS 8.5 / ASP.NET 4.0, Login.aspx customer portal + base64 rs return-url).
- CHANGED dev.applicationdesigner.de live but 403 internal-only page; dev.live-manager.de / staging.live-manager.de / test.live-manager.de / portal.live-manager.de / account.live-manager.de do not serve HTTP.
- NEW auth.live-manager.de: inventory host with 0 live HTTP — likely wildcard mirror; needs live confirmation.

## 2026-09-04 09:50:34 UTC

## 2026-09-04 14:17:33 UTC

## 2026-09-04 17:50:53 UTC
- NEW No new hosts discovered since 2026-09-04 14:17 UTC; surface frozen at 4 live in-scope hosts (cbs-proxy.api.live-manager.de, www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de)
- CHANGED auth.live-manager.de remains unconfirmed (0 live HTTP) — consistent with wildcard mirror assessment from DEDICATED-DEEP.md.
- CHANGED api.live-manager.de confirmed non-resolving (dropped from all models).
- CHANGED Probe results remain empty — no new passive/active data since last[0m

## 2026-09-04 20:10:34 UTC

## 2026-09-04 22:19:45 UTC

## 2026-09-05 00:18:43 UTC
- NEW www.applicationdesigner.de/extjs/livedebugger/auth.php: confirmed anonymous minting of per-tenant live-debug auth tokens for arbitrary customer_id (cid=2 success:true) using static credential (sha256 
- NEW Cross-tenant chain primitive confirmed: public static credential in help.js → auth.php token mint for ANY cid → anonymous WS 101 to cbs-proxy.api.live-manager.de
- CHANGED cbs-proxy.api.live-manager.de IDOR confidence raised to 72 (live probe 2026-09-04: HTTP/1.1 101, CONNECT frames to CBS100/190/200, READY, zero credentials)
- CHANGED www.applicationdesigner.de MISCONFIG confidence raised to 55 (help.js ships full LiveDebugger/CallBuilder/AIDesigner endpoint map + /api/callbuilder/ proxy prefix + AIDesigner backend router)
- CHANGED Risk score increased to 68 (full primitive chain confirmed read-only)

## 2026-09-05 04:44:49 UTC
- NEW www.applicationdesigner.de/help.json: ExtJS manifest confirms help.js as sole JS entry; resources.help/ directory listing blocked (403) — endpoint map only in help.js
- CHANGED help.js static credential `LIVE_DEMO_CUSTOMER_TOKEN` (sha256: 8d2faac1...) and `APPDESIGNER_API_PATH=/api/callbuilder/` proxy prefix confirmed in live source; backend router endpoints for LiveDebugger
- CHANGED cbs-proxy.api.live-manager.de WebSocket handshake (HTTP 101) with zero credentials confirmed 2026-09-04; CONNECT frames to CBS100/190/200 then READY — cid/service scoping enforcement still unverified

## 2026-09-05 08:42:00 UTC
- NEW www.applicationdesigner.de/help.json: ExtJS manifest confirms help.js as sole JS entry; resources.help/ directory listing blocked (403) — endpoint map only in help.js (from inventory 2026-09-05 04:44:
- CHANGED help.js static credential `LIVE_DEMO_CUSTOMER_TOKEN` (sha256: 8d2faac1...) and `APPDESIGNER_API_PATH=/api/callbuilder/` proxy prefix confirmed in live source; backend router endpoints for LiveDebugger
- CHANGED cbs-proxy.api.live-manager.de WebSocket handshake (HTTP 101) with zero credentials confirmed 2026-09-04; CONNECT frames to CBS100/190/200 then READY — cid/service scoping enforcement still unverified 

## 2026-09-05 12:09:45 UTC
- NEW www.applicationdesigner.de/help.json: ExtJS manifest confirms help.js as sole JS entry; resources.help/ directory listing blocked (403) — endpoint map only in help.js (from inventory 2026-09-05 04:44:
- CHANGED help.js static credential `LIVE_DEMO_CUSTOMER_TOKEN` (sha256: 8d2faac1...) and `APPDESIGNER_API_PATH=/api/callbuilder/` proxy prefix confirmed in live source; backend router endpoints for LiveDebugger
- CHANGED cbs-proxy.api.live-manager.de WebSocket handshake (HTTP 101) with zero credentials confirmed 2026-09-04; CONNECT frames to CBS100/190/200 then READY — cid/service scoping enforcement still unverified 
- CHANGED cbs-proxy.api.live-manager.de: WS handshake (HTTP 101) with zero credentials confirmed 2026-09-04; CONNECT frames to CBS100/190/200 then READY — cid/service scoping enforcement still unverified
- CHANGED www.applicationdesigner.de/help.js: static credential `LIVE_DEMO_CUSTOMER_TOKEN` (sha256: 8d2faac1...) and `APPDESIGNER_API_PATH=/api/callbuilder/` proxy prefix confirmed in live source; backend route
- CHANGED www.applicationdesigner.de/extjs/livedebugger/auth.php: anonymous minting of per-tenant live-debug auth tokens for arbitrary customer_id (cid=2 success:true) using static credential confirmed
- NEW Cross-tenant chain primitive confirmed read-only: help.js credential → auth.php mint for ANY cid → anonymous WS 101 to cbs-proxy backend
- CHANGED Risk score increased to 68 (full primitive chain confirmed read-only; no live customer data touched)

## 2026-09-05 15:31:48 UTC
- CHANGED Surface frozen at 4 live in-scope hosts since 2026-09-04: cbs-proxy.api.live-manager.de, www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de
- CHANGED auth.live-manager.de remains unconfirmed (0 live HTTP, wildcard mirror)
- CHANGED api.live-manager.de confirmed non-resolving (dropped from all models)
- CHANGED Cross-tenant primitive chain confirmed read-only: help.js static credential (sha256 8d2faac1...) → auth.php mints per-cid token for ANY customer_id → anonymous WS 101 to cbs-proxy with client-supplied
- CHANGED Bigpickle probe 2026-09-05 04:44: anonymous WS upgrade with cid=999999999/service=999999 returns HTTP/1.1 101 + identical CONNECT CBS100/190/200 + PROXY READY frames — zero credentials, byte-identical

## 2026-09-05 17:50:12 UTC
- NEW Bigpickle probe 2026-09-05 04:44: anonymous WS upgrade with `cid=999999999&service=999999` returns HTTP/1.1 101 + identical CONNECT CBS100/190/200 + PROXY READY frames — zero credentials, byte-identic
- CHANGED Cross-tenant primitive chain confirmed read-only: help.js static credential (sha256 8d2faac1...) → auth.php mints per-cid token for ANY customer_id → anonymous WS 101 to cbs-proxy with client-supplied
- CHANGED Surface frozen at 4 live in-scope hosts since 2026-09-04: cbs-proxy.api.live-manager.de, www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de
- CHANGED auth.live-manager.de remains unconfirmed (0 live HTTP, wildcard mirror)
- CHANGED api.live-manager.de confirmed non-resolving (dropped from all models)

## 2026-09-05 19:35:24 UTC

## 2026-09-05 21:57:47 UTC
- CHANGED Live probe 2026-09-05 21:50 UTC: WS-upgrade GET wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=999999999&service=100 → HTTP/1.1 101 + CONNECT CBS100/190/200 + PROXY READY frames (byte-identi
- CHANGED Live probe 2026-09-05 21:51 UTC: WS-upgrade GET wss://cbs-proxy.api.live-manager.de/?origin=LiveDemo&cid=1&service=100 → HTTP/1.1 101 + identical frame set — cid parameter not validated at proxy layer
- CHANGED Live probe 2026-09-05 21:52 UTC: GET https://www.applicationdesigner.de/extjs/livedebugger/auth.php?token=LIVE_DEMO_CUSTOMER_TOKEN&customer_id=999999999&srn=100 → success:true, 64-hex auth+ttl — arbit
- CHANGED Live probe 2026-09-05 21:53 UTC: GET https://www.applicationdesigner.de/extjs/livedebugger/auth.php (no token) → success:false, "Not logged in" — token is sole auth gate
- CHANGED Live probe 2026-09-05 21:54 UTC: WS-upgrade with minted token (origin=LiveDebugger&cid=2&service=100&token=...) → HTTP/1.1 101 + identical CONNECT/READY — token accepted but no observable scoping enfo

## 2026-09-06 03:56:36 UTC
- NEW www.applicationdesigner.de/AIDesigner/backend/: config.php + config_coding.php return anonymous HTTP 200 zero-auth JSON — internal LLM routing (ollama.codermatrix.de/v1, 6 providers, model→system-prom
- CHANGED AIDesigner dispatch is NOT satisfiable via the static-credential chain (unlike auth.php) — positive control: this router's token gate holds, sharpening the auth.php-mint anomaly.

## 2026-09-06 08:43:18 UTC
- CHANGED www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe executed 2026-09-06 — config.php/config_coding.php re-confirmed HTTP 200 zero-auth (public provider URLs, model→prompt map, zero k
- CHANGED AIDesigner MISCONFIG downgraded from open hypothesis to closed LOW: prompt files gated, dispatch 403-gated with AND without public demo credential (sha256 8d2faac1…), mint (get_agent_token.php) sessio

## 2026-09-06 12:28:37 UTC
- CHANGED www.applicationdesigner.de/AIDesigner/backend/: passive sibling probe executed 2026-09-06 — config.php/config_coding.php re-confirmed HTTP 200 zero-auth (public provider URLs, model→prompt map, zero k
- CHANGED AIDesigner MISCONFIG downgraded from open hypothesis to closed LOW: prompt files gated, dispatch 403-gated with AND without public demo credential (sha256 8d2faac1…), mint (get_agent_token.php) sessio
- NEW www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatrix.de/v1, 6 providers, model→system-prompt map); dispatch gate
- NEW www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential (sha256 8d2faac1…) — AIDesigner dispatch NOT static-credent
- CHANGED AIDesigner MISCONFIG downgraded to closed LOW: prompt files 403-gated, dispatch 403-gated with/without static credential, get_agent_token.php requires session+VPN — no anonymous sibling (2026-09-06 pa
- CHANGED cbs-proxy.api.live-manager.de: two byte-identical probe cycles (2026-09-04, 2026-09-05 21:50/21:51 UTC) confirm anonymous WS 101 + CONNECT CBS100/190/200 + READY for any cid/service — cid parameter no
- CHANGED Cross-tenant primitive chain confirmed read-only: help.js static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) → auth.php mints per-cid token for ANY customer_id

## 2026-09-06 15:44:54 UTC
- NEW cbs-proxy.api.live-manager.de: two byte-identical probe cycles (2026-09-04, 2026-09-05 21:50/21:51 UTC) confirm anonymous WS 101 + CONNECT CBS100/190/200 + READY for any cid/service — cid parameter no
- CHANGED Cross-tenant primitive chain confirmed read-only: help.js static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) → auth.php mints per-cid token for ANY customer_id
- CHANGED AIDesigner MISCONFIG downgraded to closed LOW: prompt files 403-gated, dispatch 403-gated with/without static credential, get_agent_token.php requires session+VPN — no anonymous sibling (2026-09-06 pa
- CHANGED www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential (sha256 8d2faac1…) — AIDesigner dispatch NOT static-credent
- NEW www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatrix.de/v1, 6 providers, model→system-prompt map); dispatch gate

## 2026-09-06 17:59:32 UTC
- NEW cbs-proxy.api.live-manager.de: two byte-identical probe cycles (2026-09-04, 2026-09-05 21:50/21:51 UTC) confirm anonymous WS 101 + CONNECT CBS100/190/200 + READY for any cid/service — cid parameter no
- CHANGED Cross-tenant primitive chain confirmed read-only: help.js static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) → auth.php mints per-cid token for ANY customer_id
- CHANGED AIDesigner MISCONFIG downgraded to closed LOW: prompt files 403-gated, dispatch 403-gated with/without static credential, get_agent_token.php requires session+VPN — no anonymous sibling (2026-09-06 pa
- CHANGED www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential (sha256 8d2faac1…) — AIDesigner dispatch NOT static-credent
- NEW www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatrix.de/v1, 6 providers, model→system-prompt map); dispatch gate
- NEW No new in-scope hosts discovered since 2026-09-04; surface frozen at 4 live hosts (cbs-proxy.api.live-manager.de, www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de)
- NEW www.applicationdesigner.de/AIDesigner/backend/config.php: anonymous HTTP 200 zero-auth JSON exposes internal LLM routing (ollama.codermatrix.de/v1, 6 providers, model→system-prompt map); no keys obser
- NEW www.applicationdesigner.de/AIDesigner/backend/public/index.php?route=: 403 {"error":"Invalid token"} with AND without public demo credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be7008
- CHANGED AIDesigner MISCONFIG downgraded to closed LOW: prompt files 403-gated, dispatch 403-gated with/without static credential, get_agent_token.php requires session+VPN — no anonymous sibling exists (2026-0
- CHANGED cbs-proxy.api.live-manager.de: two byte-identical probe cycles (2026-09-04, 2026-09-05 21:50/21:51 UTC) confirm anonymous WS 101 + CONNECT CBS100/190/200 + READY for any cid/service — cid parameter no
- CHANGED Cross-tenant primitive chain confirmed read-only: help.js static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf) → auth.php mints per-cid token for ANY customer_id

## 2026-09-06 20:20:28 UTC
- NEW No new in-scope hosts discovered since 2026-09-04; surface frozen at 4 live hosts (cbs-proxy.api.live-manager.de, www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de)
- CHANGED AIDesigner MISCONFIG downgraded to closed LOW: prompt files 403-gated, dispatch 403-gated with/without static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf), get_
- CHANGED Cross-tenant primitive chain confirmed read-only and probe-verified: help.js static credential → auth.php mints per-cid token for ANY customer_id (tested cid=2, 999999999) → anonymous WS 101 to cbs-pr
- CHANGED cbs-proxy.api.live-manager.de: two byte-identical probe cycles (2026-09-04, 2026-09-05 21:50/21:51 UTC) confirm anonymous WS 101 + CONNECT CBS100/190/200 + READY for any cid/service — cid parameter no

## 2026-09-06 22:13:06 UTC
- NEW No new in-scope hosts discovered since 2026-09-04; surface frozen at 4 live hosts (cbs-proxy.api.live-manager.de, www.live-manager.de, www.applicationdesigner.de, dev.applicationdesigner.de)
- CHANGED AIDesigner MISCONFIG downgraded to closed LOW: prompt files 403-gated, dispatch 403-gated with/without static credential (sha256 8d2faac1b96e020c077fb81aa3452b590d015d59bb826be700899187a0095cbf), get_
- CHANGED Cross-tenant primitive chain confirmed read-only and probe-verified: help.js static credential → auth.php mints per-cid token for ANY customer_id (tested cid=2, 999999999) → anonymous WS 101 to cbs-pr
- CHANGED cbs-proxy.api.live-manager.de: two byte-identical probe cycles (2026-09-04, 2026-09-05 21:50/21:51 UTC) confirm anonymous WS 101 + CONNECT CBS100/190/200 + READY for any cid/service — cid parameter no
