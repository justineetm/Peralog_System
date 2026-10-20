PeraLog — Current Architecture and Limitations
 
Last updated: 2026-10-20
 
1. Purpose
 
This document records the current architecture of the existing PeraLog expense tracker before new savings-management features are developed.
 
The goal is to preserve working behavior, understand the current limitations, and establish a safe baseline for future improvements.
 
2. Current Architecture
 
Frontend
 
The existing app uses vanilla HTML, CSS, and JavaScript without a required build step.
 
- "index.html" — application page and interface structure.
- "style.css" — layout, styling, and responsive presentation.
- "app.js" — application logic and expense-tracking interactions.
- "manifest.json" — Progressive Web App (PWA) metadata.
- "sw.js" — service worker used for offline asset caching.
- "img/" — image assets.
- ".vscode/" — editor configuration.
 
Data Storage
 
Project documentation describes browser "localStorage" as the primary data store for expenses and preferences.
 
No backend database or account-based synchronization is documented in the current architecture.
 
Backup and Restore
 
The app supports CSV export and import. Manual CSV backup is important because browser-local data may be lost if site data is cleared or the browser storage is removed.
 
CSV restoration was tested using fictional expense data in a separate browser session.
 
Currency
 
The documented design stores raw numeric amounts and formats them for display. Currency selection changes the displayed currency; it does not perform exchange-rate conversion.
 
Offline and Installation Support
 
The app includes a web app manifest and service worker. It is designed to support PWA installation and offline asset caching.
 
Offline behavior and installation behavior require separate testing before being considered fully verified.
 
3. Verified Baseline Behavior
 
The following behavior was reported during manual testing with fictional data:
 
- The app loads through a local HTTP server.
- The dashboard, expense form, and spending list display correctly.
- Expense entry works.
- Category filtering and text search work.
- The chart and currency selector work.
- CSV export produces a file with the expected expense columns.
- CSV import restores the tested expenses with their dates, amounts, and categories.
- Delete, undo, and bulk-delete operations work.
 
These are manual test results, not a complete automated test suite or security audit.
 
4. Known Limitations and Risks
 
1. Browser-local storage: Data is not automatically synchronized between separate browsers or devices.
2. Data-loss risk: Clearing browser site data can remove locally stored expenses and preferences. Maintain external backups.
3. Manual backup: CSV backup and restoration require user action.
4. No documented remote account system: Cloud backup, authentication, and multi-device synchronization are not part of the documented current design.
5. Currency conversion: Changing the display currency does not convert stored amounts using exchange rates.
6. Offline verification: Full offline operation, cache-update behavior, and installation behavior still need dedicated tests.
7. Security review: This baseline is not a formal security audit. Storage protection, import validation, and other security-sensitive implementation details need code review before expanding the system.
8. Savings management: New savings-goal behavior and its relationship to expense transactions must be designed before implementation to avoid double-counting money.
 
5. Preservation Rules
 
- Keep the original "expense-tracker" repository unchanged unless a change is explicitly approved.
- Develop approved changes in "Peralog_System".
- Avoid a framework migration unless a demonstrated need justifies it.
- Use fictional financial data during development and testing.
- Preserve CSV export and restore capability.
- Test existing features after any future changes.
- Do not connect real financial data to a backend until cost, access control, and security have been reviewed.
 
6. Evidence and Follow-up
 
This document combines project documentation with the manual tests reported during the baseline inspection. Features described in project documentation are not automatically considered independently verified.
 
Remaining work:
 
- Review the implementation of storage and import validation.
- Test offline operation and PWA installation.
- Record any additional defects found during inspection.
- Create the baseline report and update the roadmap when its acceptance criteria are met.