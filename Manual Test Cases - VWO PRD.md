# Manual Test Cases - VWO PRD

## Summary

Priority Count:
- High: 16
- Medium: 10
- Low: 0

Category Count:
- Smoke: 6
- Functional: 18
- Negative: 2

| TC ID | Title | Preconditions | Steps | Expected Result | Priority | Category | Spec File |
|---|---|---|---|---|---|---|---|
| TC-01 | Verify user can log in and access the dashboard | Valid user credentials and active account exist | 1. Open VWO login page. 2. Enter valid username and password. 3. Click Sign In. | User is authenticated and lands on the dashboard successfully. | High | Smoke | PRD_FR_1 |
| TC-02 | Create a basic A/B experiment | User is logged in with experiment creation access | 1. Navigate to Experiments. 2. Click Create Experiment. 3. Select A/B Test. 4. Enter hypothesis and metric. 5. Save and launch. | Experiment is created successfully and appears in the experiment list with correct status. | High | Functional | PRD_FR_1 |
| TC-03 | Create a split URL experiment | User has access to create split URL tests | 1. Open Create Experiment. 2. Select Split URL. 3. Enter URL variants and audience. 4. Save. | Split URL experiment is created with the specified configurations. | High | Functional | PRD_FR_1 |
| TC-04 | Create a multivariate experiment | User has experiment creation rights | 1. Open Create Experiment. 2. Select Multivariate. 3. Define multiple variations and goals. 4. Save. | Multivariate experiment is created and saved successfully. | High | Functional | PRD_FR_1 |
| TC-05 | Configure audience targeting based on behavior | Logged-in user with edit access | 1. Create experiment. 2. Open audience targeting section. 3. Select behavior-based segment. 4. Save. | Audience rules are applied and visible in the experiment configuration. | High | Functional | PRD_FR_5 |
| TC-06 | Validate experiment variations can be previewed | Experiment draft exists | 1. Open created experiment. 2. Click Preview Variations. 3. Review preview. | Preview displays the configured variations correctly. | Medium | Functional | PRD_FR_1 |
| TC-07 | Schedule experiment launch and monitor status | Valid experiment exists | 1. Open experiment. 2. Set future start date. 3. Save and verify status. | Experiment is scheduled and status reflects scheduled state until start date. | Medium | Functional | PRD_FR_1 |
| TC-08 | Verify SmartStats report is generated after experiment run | Experiment has sufficient traffic and completed data | 1. Open completed experiment. 2. Click View Results. | SmartStats-based analysis is displayed with statistically validated results. | High | Functional | PRD_FR_2 |
| TC-09 | Create experiment using visual editor | User has access to visual editor | 1. Start a new experiment. 2. Choose visual editor. 3. Make edits and save. | Experiment is created using visual editor without errors. | High | Functional | PRD_FR_3 |
| TC-10 | Create experiment using code editor | User has developer-level access | 1. Start new experiment. 2. Choose code editor. 3. Enter custom code. 4. Save. | Experiment is created and code is preserved correctly. | High | Functional | PRD_FR_3 |
| TC-11 | Generate heatmap for selected page | User has access to Insights module | 1. Open Insights. 2. Select target page. 3. Generate heatmap. | Heatmap is generated with interactions displayed correctly. | High | Functional | PRD_FR_4 |
| TC-12 | Record user session and review playback | Insights access available | 1. Open Insights. 2. Start session recording. 3. Review recording. | Session recording is available and playable. | High | Functional | PRD_FR_4 |
| TC-13 | Create funnel analytics report | Valid page flow data exists | 1. Open Insights. 2. Define funnel steps. 3. Generate report. | Funnel report is created with expected drop-off data. | High | Functional | PRD_FR_4 |
| TC-14 | Create personalized experience for a segment | User has personalization access | 1. Open Personalize. 2. Select segment. 3. Configure content variation. 4. Save. | Personalized experience is created and attached to the selected segment. | High | Functional | PRD_FR_7 |
| TC-15 | Verify personalized content is delivered in real time | Personalized experience is active | 1. Browse as a user matching the segment. 2. Load the target page. | Personalized content is displayed for matching users. | High | Functional | PRD_FR_7 |
| TC-16 | Verify real-time dashboard updates | Experiment is live and collecting data | 1. Open dashboard. 2. Monitor live stats. | Dashboard updates reflect current experiment activity. | Medium | Functional | PRD_FR_6 |
| TC-17 | Validate connector integration with analytics platform | Integration account exists | 1. Configure connector. 2. Authorize connection. 3. Send sample data. | Data sync is successful and visible in downstream reporting. | High | Functional | PRD_FR_8 |
| TC-18 | Validate failure handling for failed integration | Connector credentials are invalid or endpoint unavailable | 1. Configure connector with invalid credentials. 2. Attempt sync. | Error message is displayed and no misleading success state appears. | High | Negative | PRD_FR_8 |
| TC-19 | Verify collaboration and workflow management task flow | Team workspace exists | 1. Create plan/program. 2. Assign task. 3. Update workflow status. | Collaboration workflow updates correctly and reflects assigned ownership. | Medium | Functional | PRD_FR_9 |
| TC-20 | Verify RBAC prevents unauthorized access | User with viewer role exists | 1. Log in with viewer account. 2. Try to edit or launch experiment. | Access is denied and system displays an authorization message. | High | Negative | NFR_2 |
| TC-21 | Verify 2FA enforcement for privileged users | Admin account without 2FA is configured | 1. Log in to admin account. 2. Trigger protected action. | 2FA challenge appears before sensitive actions proceed. | High | Functional | NFR_2 |
| TC-22 | Verify audit logs capture sensitive actions | Admin user performs an action | 1. Perform configuration or permission change. 2. Open activity log. | Activity log records the action with timestamp and user details. | High | Functional | NFR_2 |
| TC-23 | Verify GDPR/CCPA privacy handling | Test data includes user data and consent state | 1. Submit data export/delete request. 2. Review system response. | Request is processed and user data handling follows privacy policy. | High | Functional | NFR_4 |
| TC-24 | Validate response time for editing workflows | User has a valid account and a test page | 1. Perform edits in the editing workflow. 2. Measure response time. | System responds within 2 seconds for editing workflows. | High | Functional | NFR_1 |
| TC-25 | Validate scalability with high-volume traffic simulation | Test environment supports performance load simulation | 1. Simulate high visitor volume. 2. Monitor page loading and reporting. | System remains functional and performs without critical degradation. | High | Functional | NFR_3 |
| TC-26 | Verify reliability and uptime behavior | Environment is available for monitoring | 1. Repeatedly access the platform over a defined test window. 2. Monitor service availability. | Platform remains available and errors are within acceptable thresholds. | High | Functional | NFR_5 |

## QA Review Section

### 1. Coverage Gaps

- Pricing and licensing workflows are not covered in detail because the PRD provides high-level information only.
- Mobile-specific SDK functionality is out of scope for this version.

### 2. Risks

- Integration behavior may vary by third-party platform.
- Statistical results may require domain-specific validation.
- Performance under peak traffic should be confirmed in a dedicated load test.

### 3. Automation Candidates

- Login and authentication flow
- Experiment creation and scheduling
- Audience targeting configuration
- Personalization activation checks
- RBAC denial validation
- Reporting and dashboard refresh validation

### 4. Recommended Next Steps

- Add detailed UAT scenarios for business users.
- Create API-level tests for connector sync and reporting endpoints.
- Expand performance and scalability tests using load tools.
