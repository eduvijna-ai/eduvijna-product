# Security Standards

**ID:** ENG-SEC-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Applies to:** Teacher OS implementation on existing auth/tenant model

---

## 1. Authentication & authorization

1. Use existing JWT / `Authorize()` patterns — do not invent parallel auth.  
2. Enforce school/tenant isolation on all Artifact/Work/Queue queries.  
3. Teachers cannot approve or view other schools’ Artifacts.  
4. Feature flags never grant privilege escalation.

---

## 2. AI publish gate

1. AI Assists, Teacher Decides — server-side enforcement.  
2. Clients cannot force `Published` without passing Approved.  
3. Review Queue transitions are authorized and audited.

---

## 3. Secrets & config

1. No secrets in git, logs, or telemetry.  
2. Use existing env / secret manager patterns.  
3. LLM provider keys remain in server config only.

---

## 4. PII & student data

1. Minimize collection; purpose-limit analytics.  
2. No student PII in client logs or third-party analytics payloads.  
3. Parent drafts treated as sensitive until/after send.  
4. Align with Privacy by Design product principle.

---

## 5. Input safety

1. Validate and sanitize user and AI outputs before render where XSS risk exists.  
2. Dependency updates follow existing repo security practices (secret scanning already enabled on product docs repo; app repos follow their own).

---

## 6. Related

- `API_STANDARDS.md` · `OBSERVABILITY_STANDARDS.md` · `FEATURE_FLAG_STANDARDS.md`  
