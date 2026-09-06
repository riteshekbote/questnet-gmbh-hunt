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
