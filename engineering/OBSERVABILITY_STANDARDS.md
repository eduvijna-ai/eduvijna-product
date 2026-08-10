# Observability Standards

**ID:** ENG-OBS-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Rule:** Every new feature emits telemetry; logs are structured and PII-safe

---

## 1. Logging

1. Use existing logging frameworks/patterns in each repo.  
2. **No PII** in logs (student names, full parent message bodies, tokens, passwords).  
3. Correlate with `request_id` / correlation id, plus `work_id` / `artifact_id` when available.  
4. Log Artifact lifecycle transitions at info.  
5. Errors: structured message + code; stacks server-side only.  
6. Do not log raw LLM prompts/responses in production by default.

---

## 2. Telemetry events (minimum for Teacher OS)

| Event | When |
|-------|------|
| `mission.viewed` | Mission opened |
| `mission.review_cta_clicked` | Review → |
| `artifact.generated` | Entered **Generated** (ADR-046) |
| `artifact.review_opened` | Opened from Queue |
| `artifact.approved` | Approved |
| `artifact.rejected` | Rejected |
| `artifact.published` | Published/assigned/sent |
| `work.continued` | Continue Work |
| `context.followup` | Continuous Context refine |
| `flag.evaluated` | Sampled debug of flag state |

Properties: `artifact_type`, `lifecycle_state`, `school_id` (non-PII), cohort/flag keys as needed.

---

## 3. Performance signals

Track or smoke:

- Mission/Dashboard load time (target &lt; 2s)  
- Navigation interaction snappiness (target &lt; 100 ms perceived)  
- AI status update latency (target &lt; 500 ms where applicable)  

---

## 4. Alerts (Pilot+)

- Publish/share without Approved state → **page-level** incident  
- Error rate spike on generate/approve  
- Mission p95 above budget sustained  

---

## 5. Related

- `SECURITY_STANDARDS.md` (PII)  
- `API_STANDARDS.md` (audit)  
- EBP-001 performance targets  
