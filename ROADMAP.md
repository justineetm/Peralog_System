# PeraLog System Roadmap
 
Last updated: 2026-10-20
 
## Project Goal
 
Build a personal expense and savings management system while preserving the existing PeraLog expense tracker.
 
Budget target: ₱0, using free tools where practical.
 
## Milestone 0 — Establish the Baseline
 
- [x] Confirm the existing app loads locally.
- [x] Test basic expense management and key existing features.
- [x] Export a CSV backup and inspect its columns.
- [x] Restore the CSV in a separate browser session.
- [x] Document the current architecture and known limitations.
- [x] Complete a baseline report and identify remaining tests.
 
Exit criteria: Existing behavior and limitations are documented, and a safe rollback point is established before new features are implemented.
 
## Milestone 1 — Personal Savings Management
 
- [ ] Define savings goals, target amounts, and optional target dates.
- [ ] Define contributions and withdrawals.
- [ ] Decide how savings activity relates to expenses to avoid double-counting.
- [ ] Design the screens and local data model.
- [ ] Implement and test one small feature at a time.
 
Exit criteria: Savings goals can be tracked locally without breaking existing expense and budget features.
 
## Milestone 2 — Backend Decision and Design
 
- [ ] Decide whether local-only storage is sufficient.
- [ ] Compare free-tier backend options if remote backup or sync is needed.
- [ ] Document data ownership, security, backup, and failure handling.
 
Exit criteria: A cost-checked design is approved before any real financial data is uploaded.
 
## Milestone 3 — Optional Secure Sync
 
- [ ] Add authentication only if needed.
- [ ] Design sync, retry, error, and conflict handling.
- [ ] Test offline changes and recovery using fictional data.
- [ ] Preserve local export and backup options.
 
Exit criteria: Sync is tested with fictional data and failure scenarios before personal data is used.
 
## Project Guardrails
 
- Keep the existing vanilla HTML, CSS, and JavaScript unless a concrete need justifies a change.
- Prefer small, reversible changes.
- Use fictional financial data for testing.
- Never commit secrets or private financial data.
- Verify free-tier pricing and limits before adopting a service.
- Treat AI recommendations as proposals; the project owner makes final decisions.