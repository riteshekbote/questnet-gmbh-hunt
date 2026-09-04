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
