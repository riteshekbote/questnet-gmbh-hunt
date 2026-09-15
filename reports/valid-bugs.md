# Validated findings (running count 0)

- 1 lead(s) marked VALID at 2026-09-05 08:38:47 UTC
  - | **Q4 Provable** | **PARTIAL** — anonymous handshake + CONNECT/READY frames confirmed; final frame-level binding requires AUTH_HELPED (valid operator session) |

- 5 lead(s) marked VALID at 2026-09-06 06:10:35 UTC
  - **Verdict: VALID**
  - **Verdict: VALID**
  - | Q4 Provable | ❌ | Requires valid customer session; anonymous GET does not redirect |
  - | 2 | Static credential → auth.php token mint | **VALID** | **7.5** | File report |
  - | 3 | Voicenote metadata PII disclosure | **VALID** | **7.5** | File report |

- 2 lead(s) marked VALID at 2026-09-06 11:08:36 UTC
  - | 2 | Static credential → auth.php token mint | **VALID** | **7.5** | File report |
  - | 3 | Voicenote metadata PII disclosure | **VALID** | **7.5** | File report |

- 5 lead(s) marked VALID at 2026-09-06 21:29:49 UTC
  - **Verdict: VALID**
  - **Verdict: HOLD** (upgradeable to VALID with AUTH_HELPED frame-binding confirmation)
  - | Q2 Reachable? | **Unknown** — needs valid customer session (AUTH_HELPED). Anonymous variant (GET /?rs=) does NOT reflect value or redirect externally — already REJECTED by multiple models. |
  - | Q4 Provable? | **No** — requires valid customer session to test post-login behavior. Cannot be proven non-invasively. |
  - | 1 | auth.php static-credential token mint + voicenote PII disclosure | **VALID** | 7.5 HIGH | Broken Auth / IDOR — report via bugs.olivermaicher.eu |

- 10 lead(s) marked VALID at 2026-09-08 08:45:08 UTC
  - **Verdict: VALID — HIGH**
  - **Verdict: VALID — HIGH**
  - | Q5 Novel? | **YES** | This is the enabler for Leads 1 and 2. Reporting as standalone finding is valid for broken auth / credential exposure |
  - **Verdict: VALID — HIGH** (chain enabler)
  - | Q4 Provable? | **NO** | Requires valid customer session to test post-login behavior. Cannot be proven non-invasively |
  - **Verdict: HOLD — Requires AUTH_HELPED (valid customer session) to confirm post-login redirect behavior**
  - | Q4 Provable? | **NO** | Requires AUTH_HELPED (valid session) to test download gate |
  - | 1 | cbs-proxy WS BOLA | **VALID** | HIGH | 7.5 | File report |
  - | 2 | voicenote PII metadata | **VALID** | HIGH | 7.5 | File report |
  - | 3 | help.js static credential | **VALID** | HIGH | 7.5 | File report (chain enabler) |

- 5 lead(s) marked VALID at 2026-09-10 11:51:17 UTC
  - **Verdict: VALID**
  - **Verdict: VALID**
  - | Q4 Provable | **NO** | Requires AUTH_HELPED valid customer session |
  - | 1. CBS WS Proxy IDOR | **VALID** | 8.6 High | File |
  - | 2. auth.php + cbs-proxy chain | **VALID** | 9.1 Critical | File |

- 4 lead(s) marked VALID at 2026-09-12 05:09:43 UTC
  - **Verdict: VALID**
  - **Verdict: VALID**
  - | 1 | CBS Proxy WebSocket IDOR/BOLA | **VALID** | 8.6 |
  - | 2 | Static credential token mint + voicenote PII leak | **VALID** | 7.5 |

- 4 lead(s) marked VALID at 2026-09-13 21:23:12 UTC
  - | **Q4 Provable?** | **PARTIAL** — anonymous handshake + CONNECT/READY frames confirmed non-invasively; final frame-level binding requires AUTH_HELPED (valid operator session) |
  - **Verdict: HOLD** — upgrade to VALID when AUTH_HELPED frame-binding test completes. Anonymous handshake proof is solid but the final "does the backend reject a mismatched cid in the live_debug frame" 
  - **Verdict: VALID**
  - **Verdict: HOLD** — needs a second valid tenant's flexlist_id to prove cross-tenant read. If that evidence surfaces, upgrade to VALID.

- 15 lead(s) marked VALID at 2026-09-14 07:11:48 UTC
  - **VERDICT: VALID**
  - | Q7 | Reasonable triager? | **YES** — broken authentication allowing arbitrary tenant token minting is a clear valid bug |
  - **VERDICT: VALID** (mitigated as of 2026-09-07, VPN gate deployed)
  - | Q7 | Reasonable triager? | **YES** — anonymous access to real customer's call/voicemail metadata via public JS credential is clearly a valid finding |
  - **VERDICT: VALID**
  - **VERDICT: HOLD** — Valid as supporting context for Lead 1 (cbs-proxy) but insufficient standalone severity for a triager to accept it as a separate finding. Report as part of the chain.
  - | Q4 | Provable non-invasively? | **NO** — requires valid customer session to test post-login redirect. No passive proof. |
  - **VERDICT: HOLD** — Valid finding but POST-only requires active probing; report only if willing to demonstrate resource consumption.
  - | Q7 | Reasonable triager? | **YES** — authorization data leakage via broken auth is a valid finding |
  - **VERDICT: VALID**
  - **VERDICT: HOLD** — Valid misconfiguration (public static credential grants data access) but cross-tenant impact unproven; HOLD pending operator confirmation of second tenant's ID.
  - | 1 | cbs-proxy anonymous WS BOLA | **VALID** | 8.6 | High |
  - | 2 | auth.php cross-tenant token mint | **VALID** (mitigated) | 8.1 | High |
  - | 3 | voicenotes cross-tenant PII | **VALID** | 7.5 | High |
  - | 11 | get_user_rights.php authz leak | **VALID** | 6.5 | Medium |

- 15 lead(s) marked VALID at 2026-09-15 11:55:37 UTC
  - | Q4 Provable | **PARTIAL** — anonymous handshake + CONNECT/READY frames confirmed non-invasively; final frame-level binding requires AUTH_HELPED (valid operator session) |
  - **Verdict: HOLD** — Upgrade to VALID when AUTH_HELPED frame-binding test completes. Anonymous handshake proof is solid; the sole remaining question is whether the CBS backend rejects a live_debug pack
  - | Q7 Reasonable triager | **YES** — broken authentication via exposed credential is a clear valid finding |
  - **Verdict: VALID**
  - **Verdict: VALID**
  - **Verdict: VALID (mitigated)**
  - **Verdict: VALID**
  - | Q2 Reachable | **NO** — anonymous GET /?rs= does NOT redirect externally; 302→/?rs= with no reflection; post-login behavior unverifiable without valid customer session |
  - | Q7 Reasonable triager | **NO** — needs second valid tenant's flexlist_id to prove cross-tenant read |
  - **Verdict: HOLD** — upgrade to VALID when operator confirms a second tenant's flexlist_id exists in the global id space
  - **Verdict: HOLD** — valid candidate but requires active POST to confirm; file only if willing to demonstrate
  - | 2 | help.js static credential | **VALID** | 7.5 | File report |
  - | 3 | Voicenote metadata PII | **VALID** | 7.5 | File report |
  - | 4 | auth.php token mint | **VALID (mitigated)** | 8.1→7.5 | File report + note VPN gate |
  - | 5 | get_user_rights.php leak | **VALID** | 6.5 | File report |

- 10 lead(s) marked VALID at 2026-09-15 16:36:51 UTC
  - **Verdict: HOLD** — upgrade to VALID when AUTH_HELPED frame-binding test completes.
  - **Verdict: VALID**
  - **Verdict: VALID**
  - **Verdict: VALID (mitigated)**
  - **Verdict: VALID**
  - **Verdict: HOLD** — valid candidate; file only if willing to demonstrate.
  - | 2 | help.js static credential | **VALID** | 7.5 | File report |
  - | 3 | Voicenote metadata PII | **VALID** | 7.5 | File report |
  - | 4 | auth.php token mint | **VALID (mitigated)** | 8.1→7.5 | File + note VPN gate |
  - | 5 | get_user_rights.php leak | **VALID** | 6.5 | File report |
