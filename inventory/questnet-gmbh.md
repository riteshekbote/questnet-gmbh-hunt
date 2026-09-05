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
