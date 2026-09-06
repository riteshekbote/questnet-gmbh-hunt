## REPOSCAN 2026-09-03 15:55:49 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-03 19:09:53 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-03 21:45:30 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-03 23:48:47 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 03:16:18 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 08:04:41 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 12:46:44 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 16:48:32 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 19:20:37 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 21:40:58 UTC
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
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-04 23:18:43 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 01:07:11 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 06:03:41 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 10:04:00 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 13:28:32 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 16:15:46 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 18:23:12 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 20:49:22 UTC
[HYP] FreeSWITCH Event Socket with default "ClueCon" password, ACL disabled, bound to 0.0.0.0
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/autoload_configs/event_socket.conf.xml:3-6
confidence: 85
reasoning: The `insideout` profile is the only Questnet-customized FreeSWITCH config (contains hardcoded internal IP 192.168.86.254 in vars.xml:14, proving human modification). It configures the ESL with `listen-ip=0.0.0.0`, `password=ClueCon` (well-known FreeSWITCH default), and `apply-inbound-acl` is commented out. This means the ESL control socket (port 8021) is exposed to all network interfaces with no ACL restriction. If deployed, any network-reachable client can authenticate with the trivially known default password and issue arbitrary FreeSWITCH API commands (originate calls, bridge, record, shutdown, etc.). The `vanilla` profile (included by the main freeswitch.xml) also uses `listen-ip=::` with `password=ClueCon` and ACL commented out.
impact: high
verify_steps: 1) Check if any FreeSWITCH instance from Questnet exposes port 8021 (nmap -sV <target> -p 8021) 2) Attempt connection with `fs_cli -H <target> -P ClueCon` 3) If connected, issue `status` or `eval $${local_ip_v4}` to confirm full control 4) Check if bugs.olivermaicher.eu or any in-scope VoIP endpoint runs FreeSWITCH on this port
[HYP] Rayo XMPP shared-secret "ClueCon" and test user "usera" with password "1"
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/rayo/autoload_configs/rayo.conf.xml:99,115
confidence: 75
reasoning: The rayo.conf.xml configures the Rayo XMPP server with `shared-secret="ClueCon"` (line 99) and an authorized user `name="usera" password="1"` (line 115). The Rayo listener is bound to `port="5222"` with `acl=""` (empty ACL, line 118). If deployed, this allows unauthenticated XMPP connections to control calls via the Rayo protocol using the trivially known default credentials.
impact: high
verify_steps: 1) Check if port 5222 is open on any in-scope host 2) Attempt XMPP connection with usera/ClueCon credentials 3) If Rayo is active, attempt to create/monitor calls via the Rayo protocol
[HYP] Hardcoded internal IP address 192.168.86.254 leaked in config
class: OTHER
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/vars.xml:14
confidence: 90
reasoning: The `insideout` profile's vars.xml contains `<X-PRE-PROCESS cmd="set" data="internal_ip_v4=192.168.86.254"/>`. This is a private RFC1918 address committed to a public repo, revealing Questnet's internal network topology. This IP appears to be an actual deployment address (not a placeholder) because it is specific (not 192.168.1.1 or 10.0.0.1) and is the only non-default modification in the insideout profile.
impact: low
verify_steps: 1) This is an information disclosure only — no direct exploitation 2) Could aid internal network reconnaissance if combined with other findings 3) Verify this IP is not routable from the internet
[HYP] Default SIP directory passwords "1234" across all FreeSWITCH profiles
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/directory/default/*.xml (1018.xml, 1002.xml, brian.xml, 1019.xml, 1015.xml, 1011.xml, 1017.xml, 1012.xml, 1008.xml, 1000.xml)
confidence: 80
reasoning: All 10 SIP user entries in the insideout directory use `password="1234"` and `vm-password=<extension_number>`. The vanilla profile uses `$${default_password}` which resolves to `1234`. These are the well-known FreeSWITCH defaults. If deployed, any SIP client can register as any extension using "1234" and make toll-fraud calls.
impact: medium
verify_steps: 1) Attempt SIP REGISTER with extension 1000-1019 and password 1234 against any in-scope SIP endpoint 2) Check if any SIP port (5060/5061) is exposed on bugs.olivermaicher.eu or related hosts
[HYP] Default credentials in multiple service configurations (AMQP, Redis, SMTP, DB, XML-RPC)
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/vanilla/autoload_configs/*.xml
confidence: 70
reasoning: The vanilla profile (included by the active freeswitch.xml) contains: AMQP password "guest" (amqp.conf.xml:9,17,51,74), Redis password "redis" (hiredis.conf.xml:7,13), SMTP password "mypassword" (switch.conf.xml:119), XML-RPC user "freeswitch" / pass "works" (xml_rpc.conf.xml:7-8), DB password "password" (easyroute.conf.xml:5), SMPP password "password" (smpp.conf.xml:10), PostgreSQL connection with user:freeswitch password:'' (switch.conf.xml:172). These are all upstream FreeSWITCH defaults. If any of these services are deployed with these configs, they are trivially compromiseable.
impact: medium
verify_steps: 1) Check if AMQP (5672), Redis (6379), XML-RPC (8021 HTTP) ports are exposed 2) Attempt default credential authentication against any running services
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-05 22:40:59 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-06 00:38:29 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-06 05:10:27 UTC
[HYP] FreeSWITCH Event Socket with default "ClueCon" password, bound to 0.0.0.0, ACL disabled
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/autoload_configs/event_socket.conf.xml:3-6
confidence: 85
reasoning: The `insideout` profile (Questnet-customized, distinct from upstream vanilla) configures ESL with listen-ip=0.0.0.0, password=ClueCon, and apply-inbound-acl commented out. The vanilla profile (also included by the main freeswitch.xml) similarly binds to :: with password=ClueCon and ACL loopback.auto commented out. If deployed on any host in the 185.158.96.0/22 range, the ESL control socket (port 8021) is exposed to all network interfaces with the trivially known default password, allowing arbitrary FreeSWITCH API commands (originate, bridge, record, shutdown).
impact: high
verify_steps: 1) nmap -sV 185.158.96.0/22 -p 8021 to find exposed ESL ports 2) fs_cli -H <target> -P ClueCon to authenticate 3) If connected, issue `status` or `eval $${local_ip_v4}` to confirm full control 4) Check bugs.olivermaicher.eu or *.live-manager.de for port 8021
[HYP] Hardcoded internal RFC1918 IP address 192.168.86.254 leaked in FreeSWITCH config
class: OTHER
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/vars.xml:14
confidence: 90
reasoning: vars.xml contains `<X-PRE-PROCESS cmd="set" data="internal_ip_v4=192.168.86.254"/>`. This is a specific non-default private IP (not 192.168.1.1) committed to a public repo, suggesting it is an actual Questnet deployment address. It is the only human modification in the insideout profile (the rest is stock FreeSWITCH). Could aid internal network reconnaissance if combined with other findings.
impact: low
verify_steps: 1) Information disclosure only — no direct exploitation 2) Verify this IP is not routable from the internet 3) Could be correlated with other internal network details if found
[HYP] Default SIP directory passwords "1234" across all FreeSWITCH extensions
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/directory/default/*.xml (1018.xml, 1002.xml, brian.xml, 1019.xml, 1015.xml, 1011.xml, 1017.xml, 1012.xml, 1008.xml, 1000.xml, plus 1001-1010)
confidence: 80
reasoning: All 20+ SIP user entries in the insideout directory use password="1234" and vm-password=<extension_number>. The vanilla profile uses $${default_password} which resolves to "1234". If deployed, any SIP client can register as any extension using the trivially known default and make toll-fraud calls.
impact: medium
verify_steps: 1) Attempt SIP REGISTER with extension 1000-1019 and password 1234 against any in-scope SIP endpoint 2) Check if SIP ports 5060/5061 are exposed on *.live-manager.de or 185.158.96.0/22 3) Use sipsak or pjsua to test registration
[HYP] Rayo XMPP shared-secret "ClueCon" and test user "usera" password "1" with empty ACL
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/rayo/autoload_configs/rayo.conf.xml:99,115,105
confidence: 75
reasoning: The rayo.conf.xml configures the Rayo XMPP server with shared-secret="ClueCon" (line 99), an authorized user name="usera" password="1" (line 115), and a listener on port 5222 with acl="" (empty ACL, line 105). This allows unauthenticated XMPP connections to control calls via the Rayo protocol using trivially known default credentials. The rayo profile is not the active profile (insideout is), but it is present in the repo and could be deployed.
impact: high
verify_steps: 1) Check if port 5222 is open on any in-scope host 2) Attempt XMPP connection with usera/ClueCon credentials 3) If Rayo is active, attempt to create/monitor calls via the Rayo protocol
[HYP] Default service credentials across multiple FreeSWITCH vanilla configs (AMQP, Redis, SMTP, DB, XML-RPC)
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/vanilla/autoload_configs/{amqp,hiredis,switch,xml_rpc,easyroute,smpp}.conf.xml
confidence: 50
reasoning: The vanilla profile (included by the active freeswitch.xml) contains: AMQP password "guest" (amqp.conf.xml:9,17,51,74), Redis password "redis" (hiredis.conf.xml:7,13), SMTP password "mypassword" (switch.conf.xml:119), XML-RPC user "freeswitch"/pass "works" (xml_rpc.conf.xml), DB password "password" (easyroute.conf.xml:5), SMPP password "password" (smpp.conf.xml:10). These are all upstream FreeSWITCH defaults. The risk depends on whether these services are actually deployed — the insideout profile (the active one) does not include these configs.
impact: medium
verify_steps: 1) Check if AMQP (5672), Redis (6379), XML-RPC (8021 HTTP) ports are exposed on in-scope hosts 2) Attempt default credential authentication against any running services
[HYP] Azure Blob Storage access key in upstream FreeSWITCH mod_http_cache example config
class: SECRET
asset: questnet/freeswitch — src/mod/applications/mod_http_cache/conf/autoload_configs/http_cache.conf.xml:37-38
confidence: 10
reasoning: The Azure storage access key kOOY4Y/sqZU9bsLjmN+9McVwTry+UIn1Owt4Zs/2S2FQT0eAWLKskZ0V6/gGFqCAKVvwXoGjqUn7PNbVjhZiNA== is present in the upstream example config. However: (1) the domain is account.blob.core.windows.net (placeholder), (2) the commit author is Andrey Volk (upstream SignalWire/FreeSWITCH maintainer), and (3) this file exists identically in upstream FreeSWITCH. This is upstream example config, NOT a Questnet-added secret.
impact: informational
verify_steps: N/A — known upstream example credential. Confirm account.blob.core.windows.net is not a live Questnet storage account via passive DNS.
[HYP] Drachtio-freeswitch-modules example config with default secrets "cymru" and "ClueCon"
class: MISCONFIG
asset: questnet/drachtio-freeswitch-modules — examples/config/default.json:5,10
confidence: 30
reasoning: The example config contains "secret": "cymru" for the drachtio server and "secret": "ClueCon" for FreeSWITCH ESL. These are well-known defaults for drachtio and FreeSWITCH respectively. This is an example file, but if deployed without modification, the drachtio server would be accessible with the default secret.
impact: low
verify_steps: 1) Check if drachtio (port 9022) is exposed on any in-scope host 2) If exposed, attempt connection with the default "cymru" secret
[HYP] Internal IP and default credentials in FreeSWITCH conf/insideout switch.conf.xml
class: MISCONFIG
asset: questnet/freeswitch (v1.10-qn branch) — conf/insideout/autoload_configs/switch.conf.xml:52
confidence: 40
reasoning: The insideout switch.conf.xml contains "password mypassword" on line 52 (in a comment or configuration context). This appears to be a default/example value, not a real credential. However, its presence in the Questnet-customized profile warrants verification.
impact: low
verify_steps: 1) Verify if this is a comment or active configuration 2) If active, check what service this password protects
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
## REPOSCAN 2026-09-06 09:31:04 UTC
TARGET_ORG not configured for questnet-gmbh; skipping public-org deep scan.
