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
