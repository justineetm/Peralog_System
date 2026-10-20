PeraLog — Baseline Test Report
 
Last updated: 2026-10-20
 
1. Purpose
 
This report records the initial manual testing of the existing PeraLog expense tracker before implementing new savings-management features.
 
The goal is to establish a working baseline, preserve existing functionality, and identify areas requiring further inspection.
 
2. Test Environment
 
- Application: PeraLog expense tracker
- Original repository: "justineetm/expense-tracker"
- Development repository: "justineetm/Peralog_System"
- Local environment: Windows, Visual Studio Code, Google Chrome
- Local server: Python HTTP server
- Test URL: "http://localhost:8000"
- Test data: Fictional expense entries
- Testing type: Manual functional testing
 
3. Test Results
 
Test| Result| Notes
Application loads locally| PASS| Dashboard and main interface displayed
Expense form| PASS| Test expenses were added successfully
Spending list| PASS| Entries appeared in the list
Category filtering and search| PASS| Reported working during manual testing
Chart| PASS| Reported working during manual testing
Currency selector| PASS| Reported working during manual testing
CSV export| PASS| Exported file contained expected expense columns and test entries
CSV import and restoration| PASS| Test expenses were restored in a separate browser session
Delete and undo| PASS| Reported working during manual testing
Bulk deletion| PASS| Reported working during manual testing
 
Important: These results reflect the manual tests performed and reported during the baseline inspection. They are not the results of an automated test suite or a formal security audit.
 
4. Observations
 
Data storage
 
The existing application documentation identifies browser "localStorage" as the primary storage for expenses and preferences. Data is not automatically synchronized between separate browser profiles or devices.
 
CSV backup and restoration
 
CSV export and import were tested with fictional expense data. The exported file was opened in Google Sheets, and the expenses were successfully imported into a separate browser session.
 
Regular and Incognito Chrome sessions use separate browser storage. Therefore, their expense lists may differ unless data is imported or otherwise transferred.
 
Currency behavior
 
The documented design uses currency selection for display formatting, not exchange-rate conversion. Stored expense amounts should remain numeric and unchanged when the display currency changes.
 
Offline and installation behavior
 
The application includes a web app manifest and service worker. Full offline functionality, installation, and cache-update behavior have not yet been independently verified.
 
5. Known Limitations and Risks
 
1. Browser-local data may be lost if site data is cleared.
2. Backup and restoration require manual CSV export and import.
3. Automatic multi-device synchronization is not documented in the current design.
4. Currency selection does not perform actual currency conversion.
5. Offline behavior and PWA installation still require dedicated tests.
6. Storage handling and CSV import validation require further code review.
7. Savings-goal functionality has not yet been implemented or tested.
 
6. Follow-up Actions
 
- [ ] Review how expenses and preferences are stored.
- [ ] Inspect CSV import validation and duplicate handling.
- [ ] Test offline behavior and PWA installation.
- [ ] Record any additional defects discovered during inspection.
- [ ] Review and approve the current architecture documentation.
- [ ] Update the roadmap after the baseline documentation is reviewed.
 
7. Baseline Conclusion
 
The existing PeraLog expense tracker loaded locally and its core expense-tracking, CSV backup/restoration, and other reported features passed the manual checks listed above.
 
The application is ready for continued baseline inspection and documentation. New savings-management features should begin only after the architecture and baseline findings have been reviewed and accepted.
 
No claim is made that the application has passed comprehensive security, automated, or cross-device testing.