# Release Standards

**ID:** ENG-REL-001  
**Parent:** ENGINEERING_CONSTITUTION.md  
**Complements:** EBP-001 `ROLLBACK_PLAN.md` · `DEPLOYMENT_NOTES`

---

## 1. Deploy order

1. **API** first (flags, Artifact/Queue endpoints, session hooks).  
2. **Web** second (Teacher OS module).  
3. **Enable flags** only on intended cohort (Preview → Pilot → GA).  
4. Child flags after parent: dashboard → review_queue → continuous_context.

---

## 2. Pre-release verification

- [ ] Automated tests green on release candidate  
- [ ] Flag defaults safe (off in prod unless cohort)  
- [ ] Flag-off classic path verified  
- [ ] Generate → Queue → Approve path verified on Preview  
- [ ] No student visibility without Approved + publish  
- [ ] Mission performance smoke  

---

## 3. Rollback

**Flag-first** within minutes:

1. Disable `teacher_os_enabled` (+ children).  
2. Confirm classic home/nav.  
3. Confirm generators still work.  
4. Retain Artifact/Work data (no destructive rollback migrations).

Code revert only if flags insufficient.

---

## 4. Backward compatibility

- Never break existing schools (Constitution).  
- Dual-run legacy nav until removal criteria met.  
- Document breaking changes in PR + release notes.

---

## 5. Release notes (minimum)

- Flags changed  
- Teacher-visible behaviour  
- Known gaps / empty Mission soft deps  
- Rollback contact  

---

## 6. Related

- `FEATURE_FLAG_STANDARDS.md`  
- EBP-001 rollout checklist  
