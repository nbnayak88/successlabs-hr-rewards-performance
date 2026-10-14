# Compensation Configuration Sequence Journal

> Source: [Notion — Compensation Configuration Sequence Journal](https://app.notion.com/p/niladrinayak/Compensation-Configuration-Sequence-Journal-3f9ce6de608980b5ac8ee5436b0028c9?source=copy_link)  
> Case study: **OmniVerse Energy Ltd.**  
> Lab: **SuccessLabs HR Rewards & Performance · 05 Build Implementation Intelligence**  
> Purpose: Preserve the journal’s implementation sequence and add an implementation-analysis lens. Treat UI paths, feature availability, technical limits, and configuration behavior as release-sensitive; verify them against current SAP Help and the target tenant before execution.

## Analysis and implementation guidance

### What the journal covers
The source lays out five broad phases: preparation and access; data integration and technical setup; compensation-plan design; compensation-cycle execution; and publishing, reporting, and statements. It covers the principal implementation workstreams: tenant readiness, permissions, employee data, tables and mappings, XML validation when required, Employee Central integration, templates, planner hierarchy, route maps, budgets, eligibility, guidelines, ratings, worksheet launch, publish, reporting, auditing, and employee statements.

### Recommended control gates
| Gate | Exit criteria | Evidence to retain |
|---|---|---|
| 1. Scope and design sign-off | Business outcomes, employee populations, plan types, currencies, approval model, and integration path agreed | Signed requirements and configuration workbook |
| 2. Tenant readiness | Required features and permissions verified; named administrators and controlled Provisioning access established | Readiness checklist and access review |
| 3. Data readiness | Source-of-record decision made; field mappings, effective dates, UDF/import rules, data quality, and privacy controls validated | Data mapping, reconciliation, sample import results |
| 4. Plan design baseline | Template, worksheet fields, eligibility, budgets, guidelines, rating sources, route map, and publish behavior approved | Versioned configuration workbook and design decisions |
| 5. Pre-launch assurance | Check Tool findings reviewed; hierarchy, planners, formulas, permissions, eligibility, and test results accepted | Signed test pack, defect log, go/no-go record |
| 6. Cycle operation | Worksheets launched to intended populations; jobs monitored; changes and exceptions controlled | Launch log, job monitoring, exception log |
| 7. Publish and close | Published records reconciled to approved awards; reports, statements, audit evidence, and retention actions completed | Publish report, reconciliation, statement report, closure approval |

### High-impact dependencies and risk points
1. **Employee Central versus external HRIS:** This decision changes the data integration approach, field mapping, publish design, and testing scope. Do not build a hybrid design without a clear requirement and ownership model.
2. **Effective dating and launch irreversibility:** The source journal highlights the worksheet effective date as a decision that cannot be changed once forms are launched. Confirm the intended effective-date behavior in the tenant and obtain sign-off before launch.
3. **Eligibility precedence:** The source notes that UDF eligibility flags can override eligibility-engine rules. Test precedence explicitly with representative employee records.
4. **Budget and guideline integrity:** Check for formula coverage gaps, catch-all behavior, boundary overlaps, proration alignment, and over-budget handling.
5. **Compensation data sensitivity:** Apply least-privilege role-based permissions, access segregation, protected exports, appropriate audit coverage, and approved retention rules. Do not grant broad administrator access beyond controlled setup and testing.
6. **Publishing risk:** Validate target pay components, event reasons, effective dates, business-rule behavior, duplicate records, and forward propagation in a non-production environment before publishing approved results.
7. **Release-sensitive details:** Paths, feature names, technical limits, XML attributes, and product behaviors in the original journal may change. Confirm current documentation for the release and tenant instead of treating the journal as an unconditional runbook.

### Connect the configuration journal to business architecture
Use the following traceability chain as an analytical overlay, not as a claim that all concepts form a strict hierarchy:

**Value Flow** (end-to-end workforce value) → **Value Stream** (Reward to Retain) → **Value Stages** (design, plan, review, approve, communicate) ↔ **Business Activities** and **Business Processes**; enable these through **Business Capabilities** such as Compensation Planning, Workforce Data Management, Budget Governance, Approval Management, and Reward Communication. **Business Areas** define organizational accountability; **Segments** clarify the population or business partition in scope. Map each requirement to its process, capability, owner, SAP configuration object, and test evidence.

### Suggested implementation sequence
1. Align scope, policy, population, target outcome, and source-of-record.
2. Confirm tenant readiness, features, access, and security.
3. Complete the configuration workbook and data mappings.
4. Prepare required import files and reference tables; validate data.
5. Configure Employee Central integration and publish mappings where applicable.
6. Configure the plan template, worksheet design, hierarchy, and route map.
7. Configure budgets, eligibility, guidelines, and rating sources.
8. Execute end-to-end tests, including negative and exception cases.
9. Run configuration checks and sign off the launch gate.
10. Launch and monitor worksheets; update only under controlled change.
11. Publish approved results; reconcile outcomes with source approvals.
12. Produce reports, statements, audit evidence, and operational handover.

---

## Source journal (preserved)


<empty-block/>
<empty-block/>
For your client, OmniVerse Energy Ltd., implementing the SAP SuccessFactors Compensation module involves a structured sequence of activities designed to configure the system to meet their specific compensation needs. This guide outlines a detailed implementation plan drawing directly from the provided SAP SuccessFactors Compensation Academy documentation.
The implementation process guides you through the configurations necessary to implement SAP SuccessFactors Compensation. It emphasizes building expertise to help customers attain goals and solve problems by implementing a best-practice approach to their compensation needs.
Here is a detailed sequence of activities for implementing the SAP SuccessFactors Compensation module for OmniVerse Energy Ltd.:
### Phase 1: Getting Started and Initial Preparation
1. **Understand Functionality and Locate Resources**
	- **Summarize the functionality of SAP SuccessFactors Compensation** for OmniVerse Energy Ltd., focusing on how it helps standardize compensation planning, assure rewards are calculated correctly and fairly, and retain top performers.
	- **Identify appropriate resources**:
		- **SAP SuccessFactors site** for general product and marketing materials.
		- **SAP SuccessFactors Community** for connecting with peers, discussion forums, support, training, and new release information. For implementation questions, the **Partner Delivery Community** is recommended for certified consultants.
		- **SAP SuccessFactors HCM Cloud Partner Services** for implementation and operational tools, including demo requests and operations service desk.
		- **SAP PartnerEdge** for implementation templates like project timelines based on SAP Activate.
		- **SAP Help Portal** for implementation guides, including role-based permissions, data protection, and privacy, and specific product pages like Compensation and Variable Pay. Ensure to look for the "production" status for final versions of guides.
		- **SAP Support Portal** (SAP ONE Support Launchpad) for help, submitting, and managing tickets.
		- **SAP Community Network** for forums, blogs, and wikis, including a Compensation-specific wiki.
	- **Download course files and relevant configuration files** as they will be used in various exercises throughout the course.
	- **Familiarize yourself with your role as a consultant**:
		- Configure the SAP SuccessFactors solution to meet OmniVerse Energy Ltd.'s needs.
		- Train OmniVerse Energy Ltd. on how to maintain the solution.
		- Point them to additional available training and resources.
2. **Preliminary System Setup (Provisioning and Upgrades)**
	- **Enable necessary upgrades from Upgrade Center**:
		- Navigate to *Admin Center* → *Upgrade Center*.
		- Upgrade **Reward and Recognition**, **Intelligent Services**, and **Compensation and Variable Pay Role-based Permissions Upgrade** from the recommended list.
	- **Enable Compensation management settings in Provisioning**. Access to Provisioning is typically for internal or partner consultants with customer authorization. These settings become available in the Compensation Home interface for customers to manage post-go-live.
	- **Grant full Compensation permissions to administrators** for OmniVerse Energy Ltd.:
		- Navigate to *Manage Permission Roles* → *System Admin*.
		- Go to *Administrator Permissions* → *Manage Compensation & Variable Pay* → **Select All**.
		- Go to *Administrator Permissions* → *Manage Compensation* → **Select All**.
		- Go to *User Permissions* → *Compensation and Variable Pay* → **Select All**.
		- **Save changes and log out**.
### Phase 2: Core Configuration and Data Integration
1. **Data Integration Strategy and Configuration Workbook**
	- **Determine HRIS integration method**: SAP SuccessFactors Compensation integrates with internal (Employee Central) and external HRIS. Most customers using SAP SuccessFactors Compensation also use SAP SuccessFactors Employee Central as their system of record.
		- If using external HRIS, determine if API, FTP, or manual import of a user data file will be used.
		- If using Employee Central, employee-specific data will be pulled directly.
	- **Utilize the SAP SuccessFactors Compensation Configuration Workbook**:
		- Obtain the latest Configuration Workbook from SAP PartnerEdge.
		- Use it with OmniVerse Energy Ltd. to identify customer configuration requirements.
		- Explain available options, provide feedback, and configure the instance based on documented requests after sign-off.
		- The *Data Integration* tab describes pre-delivered standard compensation fields and allows for custom fields.
	- **Manage the User Data File (UDF)**:
		- **Identify and map general user and compensation fields** within the UDF via the Succession Data Model. Note that some general user data fields (e.g., STATUS, USERID) that clients often want to display on compensation forms but cannot be mapped directly need to be duplicated as custom fields.
		- **Observe data import guidelines**: Do not import symbols (currency, percentage), avoid leading zeros, and use MM/DD/YYYY for dates.
		- **Ensure active users are in the system**; inactive users or those not in the system will be assigned N/A values.
		- **Import the UDF without compensation fields as needed**, and with compensation fields on a "need only" basis, at least once for the planning cycle.
		- **Schedule recurring UDF imports** from HRIS if OmniVerse Energy Ltd. requires continuous updates to salary information during planning.
		- **Be aware of data protection and privacy features** and their configuration.
	- **Create Compensation Tables (Plan Specific Data)**:
		- **Currency Conversion Tables**: Create a conversion table for each currency combination needed for planning (CSV format, no commas/headers, specific column order). *Leading practice recommends creating a new table for each planning year*.
		- **Salary Pay Matrix (Pay Ranges)**: Define salary ranges (min, mid, max) for pay grades. Up to 3 additional attributes can be used without Employee Central, unlimited with Employee Central integration. *Do not update tables referenced in prior cycle forms; create new ones for changes*.
		- **Manager Promotion Map**: If promoting employees manually, define visible new pay grades.
		- **Job Code and Pay Grade Mapping Tables**: Required if using the Job Selector function (CSV format, two columns: Jobcode, Paygrade).
		- **Job Families and Roles**: Create these if using Job Selector or promotions tool. Can be done via Admin Center or CSV import for large numbers.
		- **Lookup Tables**: Assign data to employees based on multiple attributes (CSV format, Input/Output columns). Can be encrypted for sensitive data.
		- **Stock Tables (for Long-Term Incentives)**: Create Stock Value, Stock Factor, and Stock Participation Guideline tables. Stock participation may require XML template enablement.
2. **XML DTD Validation (if modifying XML)**
	- **Understand Data Type Definition (DTD)**: The DTD acts as an XML dictionary for SAP SuccessFactors Compensation elements and attributes (specifically `sf-form.dtd`).
	- **Validate XML templates against the DTD**: This is crucial if you need to modify the compensation XML plan, as compensation planning is XML-based.
	- **Steps for validation**:
		1. Clone a pre-configured compensation plan or download the XML plan.
		2. Copy `sf-form.dtd` to the same folder as the XML plan.
		3. Open both files in an XML editor.
		4. Change the URL at the top of the XML plan for easier validation.
		5. Make desired configuration changes and then select *Validate*.
		6. Upload the validated XML plan as a new plan.
3. **Integrate Compensation Template with SAP SuccessFactors Employee Central (if applicable)**
	- **Define Field Mapping**: Map compensation fields to Employee Central fields (in XML or Design Worksheet). Compensation can retrieve data from Job Information, Compensation Information, Pay Component Recurring/NonRecurring, Personal Information, Employment Information, Job Relationships, Pay Component Group, and custom MDF objects.
	- **Configure Pay Components**: If OmniVerse Energy Ltd. uses Employee Central, specify which pay components are used for compensation planning (`Comp`, `Varpay`, or `Both`). An employee can only have one pay component flagged as `COMP` or `BOTH`.
	- **Determine Planning Method**: Decide if planning is in annualized amounts or user pay rate. This impacts configuration setup. If using Pay Component Groups for annualized planning, be aware that publishing currently only supports individual pay components.
	- **Set Employee Central Settings**:
		- **Define Worksheet Effective Date**: This controls which records are pulled from Employee Central to the Compensation worksheet. A future effective date (e.g., 12/31/2099) ensures the most current data, including future changes, is pulled. This date cannot be changed once forms are launched.
		- **Configure Publish Settings**: Map recurring and non-recurring pay components, set effective dates, and event reasons for publishing.
	- **Map Salary Ranges**: Integrate Employee Central salary pay matrix. Ensure pay grade is the first association in the corporate data model.
	- **Handle Hybrid Templates (if applicable)**: If OmniVerse Energy Ltd. has employees in both Employee Central and other HRIS, use hybrid templates, but be aware of increased complexity. It's recommended to use separate templates for each population.
	- **Additional Employee Central Configuration**: This may include adding custom fields, new pay components, event reasons, or business rules in Employee Central itself.
	- **Enable EC Promotion Integration**:
		- Enable the setting in *Actions for All Plans* → *Company Settings*.
		- Set role-based permissions under *User Permissions* → *Employee Central-Compensation Integration*.
		- Map promotion-related fields to the *EC Promotion* category.
		- Ensure promotion custom fields are reloadable and read-only.
		- Enable *Promotion Planning* checkbox in *Plan Setup* → *Settings* → *Display Settings*.
		- Define XML `finalAttribute` field in *Calculation Settings* to avoid miscalculated post-promotion pay ranges.
	- **Extensive Testing and Validation**: Crucial to ensure data flows accurately from Employee Central to Compensation, eligibility rules are correct, and final results publish correctly.
### Phase 3: Designing the Compensation Plan
1. **Create and Configure Compensation Plan Template**
	- **Start with a template**: Use a new template from SuccessStore (e.g., "Salary Planning (EC-Integrated)") or clone an existing one.
	- **Define Plan Information**: Enter plan name, fiscal year end date, and other basic settings.
	- **Configure the Worksheet**:
		- **Planning Sheet Tabs**: Set up Salary, Stock, and Summary tabs.
		- **Budget Calculation and Guidelines**: Configure how these are displayed.
		- **Approval or Route Map Steps**: Define the workflow.
		- **Form Instructions and Currency Views**.
		- Allow planners to **show/hide columns and apply filters**.
		- Consider **advanced filtering capabilities** on worksheets and executive review.
		- Enable **Advanced Mass Actions** for adjusting compensation values across filtered employee populations.
	- **Set up the Salary Sheet**: Include employee information, current/final salary, merit guidelines, and lump sum. Enable Custom Views and Compensation Profile for additional employee information if needed.
	- **Set up the Stock Sheet**: Configure for Long Term Incentive (LTI) awards, options, RSUs, etc.. Ensure guidelines (min-max) are configured based on criteria like grade and country.
	- **Configure ****`comp-salary-rule`**** (Optional)**: Define threshold limits for Final Salary and Final Pay based on compa-ratio or Position in Range. Can be used for "Lumpsum split" where excess salary is moved to lump sum. Configurable in XML or Admin Center.
2. **Define Hierarchy and Route Maps**
	- **Choose a Hierarchy Method**: Determines who the compensation planners are and for whom they plan. Options include:
		- **Standard Suite Hierarchy**: Every employee with at least one direct report is a planner; simplest but susceptible to organizational changes.
		- **Compensation Manager Hierarchy (Designated/Second Manager)**: Planner can be customized using the `SECOND_MANAGER` column in the UDF; creates a separate hierarchy for compensation planning. Requires administrative work to maintain.
		- **Rollup Hierarchy (Skip Levels)**: Forms created only for designated compensation planners; responsibility rolls up to the next planner. Can reduce form complexity but has limitations with certain functions and reports.
	- **Create Route Maps**: Defines the approval process and workflow for worksheets.
		- Assign roles for each step (e.g., `E` for first-level managers, `EM` for second-level managers, `EH` for HR Rep, `U` for User/Admin).
		- Use a **Staging Step** for final admin checks before forms are routed.
		- Use a **Holding Step** to hold forms during Executive Review.
		- Consider mass routing options (forward/backward) and mass route without validation.
		- **Avoid over-complicating with too many approval levels**.
	- **Implement Force Comments (Optional)**: Require planners to add comments based on triggers (e.g., recommendations outside guidelines, no raise given). Configurable in *Plan Setup* → *Design Worksheet* → *Define Standard Validation Rules*.
	- **Configure Number Format Rules (Optional)**: Determine how numbers are displayed (money, percent, amount, rating, ratio value, proration).
3. **Develop Budgets for the Compensation Plan**
	- **Define Budget Calculation**: Select **Mode** (e.g., `PercentofCurSal`, `PercentOfCustomField`, `Direct Amount`, `Guideline`), **Use For** (worksheet tab), **Components** (fields that spend budget), **Budget Value**, and **Based On** (`User`, `Group`, `Template`, `Planner`).
		- Consider budget proration consistent with salary proration (e.g., if merit is prorated, prorate merit budget).
		- For OmniVerse Energy Ltd., if they need budget based on complex criteria, `PercentOfCustomField` using a lookup table offers flexibility but is harder to configure.
	- **Configure Budget Rules**: Determine system behavior when recommendations exceed budget (`Allow`, `Warn`, `Disallow`). *Leading practice is to set a soft limit (warn) at the planner level*.
	- **Implement ****`groupBy`**** (Optional)**: For display purposes only, group budget panel by local currency code or custom string field.
	- **Budgeting by Groups (Optional)**: Create budget groups (compensation groups) for different employee populations (e.g., by country, job level) if OmniVerse Energy Ltd. requires different budget strategies. *Note that compensation groups are static and require regular updates to membership*.
		- *Consider using a custom field and lookup table for assigning different percentages to different employee populations for enhanced flexibility*.
4. **Define Eligibility Rules**
	- **Choose Starting Point Eligibility**:
		- **All active employees are eligible (default)**: Create rules to EXCLUDE employees.
		- **No employees are eligible**: Create rules to INCLUDE employees.
	- **Define Rules at Multiple Levels**:
		- **Compensation plan template level**: Exclude/include from the whole planning cycle.
		- **Component level**: Exclude/include from Salary or Equity Planning tabs.
		- **Field level**: Gray out specific planning fields (Merit, Lumpsum, Stock, etc.).
	- **Method for Managing Rules**:
		- **Using the Eligibility Engine (UI)**: Best for straightforward rules. Navigate to *Plan Setup* → *Plan Details* → *Eligibility*.
		- **Using MDF Business Rule Engine (for EC-integrated plans)**: Leverage Employee Central objects to create robust rules. The `IF` section filters population, `THEN` section is configured in the compensation plan.
		- **Using the User Data File (UDF)**: Preferable for complex rules with many exceptions, by setting eligibility flags (`TRUE`/`FALSE`) in UDF columns. *UDF flags will overwrite Eligibility Rules engine settings*.
	- **Apply Eligibility Rules to Custom Fields**: Enable custom fields for eligibility to use custom formulas as criteria (e.g., for budget calculations).
5. **Define and Create Guidelines**
	- **Standardize Increases**: Guidelines help planners standardize increases based on criteria.
	- **Create Guideline Matrixes/Tables**: Can be done in Admin Center or by importing a CSV file.
	- **Add New Rules and Formulas**: Define min/max recommendations for each compensation program (Merit, Promo, Extra, Lumpsum, Stock, etc.).
	- **Set Rule Settings**:
		- **Type**: Select appropriate compensation program.
		- **Criteria**: Consider Rating, Benchmark (range penetration/compa-ratio), Job Level, Pay Grade, Budget Group, or up to five Custom Fields.
		- **Mode**: Amount or Percentage.
		- **Hard Limit**: `Yes` (cannot go outside values) or `No` (warning issued).
		- **Prorating**: If `Yes`, guidelines follow system proration setup.
		- **Force Default on Rating Change**: If `Yes`, default guideline populates worksheet upon rating change.
		- **High/Low Action**: Set to `Warn` for soft limits (typically used when min/max are not displayed).
	- **Utilize Guideline Optimization**: Enable this checkbox, especially for over 1,000 guidelines, to improve system performance.
	- **Create Catch-All Formula**: Ensure employees not meeting specific criteria still receive a guideline range. Position it at the bottom of the formula list.
	- **Ensure Guidelines Without Gaps**: Make sure the top of one range matches the bottom of the next.
	- **Compensation Modeling (Optional)**: If OmniVerse Energy Ltd. needs to perform complex calculations and analyze how base salary and equity should be awarded, enable Generic Objects and Attachment Manager in Provisioning, and relevant RBP for Comp Admin.
		- Create models to analyze costs, set targets, measure impact of adjustments, and potentially create new templates.
		- System provides recommendations and allows pushing models to a live template once targets are met.
6. **Add Rating Source to Compensation Plan**
	- **Identify Rating Source**: Employee ratings can come from various sources:
		- **SAP SuccessFactors Performance Management**: Most common method. Pulls ratings directly, adds hyperlink to review form.
		- **Manual Rating**: If Performance Management isn't used or forms are unavailable; add `Comp Rating` field and assign a rating scale.
		- **Combination**: Pulls from PM form, allows manual input if PM rating not found.
		- **Third-Party System**: Import ratings via the user data file.
		- **Employee Profile**: If using ratings integrated with Calibration and Succession solutions (e.g., Performance, Competency, Objective, Potential). Ensure Scorecard is enabled.
	- **Configure Rating Source**:
		- Navigate to *Plan Setup* → *Plan Details* → *Rating Sources*.
		- Add New Rating Source, specify form name (if PM), completed status, calculated rating, import key (if third-party), and rating scale.
		- **Note**: Only one rating source and type (PM or Employee Profile) is allowed per pay component.
		- Choose rating type (e.g., `overallPerformance` is most common).
		- Consider `checkRatingSourceAcrossTemplates` XML attribute for behavior with multiple performance reviews.
		- For Employee Profile, choose rating type (standard or custom) and effective date.
### Phase 4: Running the Compensation Cycle
1. **Worksheet Creation and Management**
	- **Use the Check Tool**:
		- **Run checks before launching forms** to identify configuration and data-related issues.
		- Grant necessary permissions (*Access Check Tool*, *Allow Configuration Export*).
		- Perform checks like `cyclic dependency`, `head of hierarchy`, `inactive planners`, `users without planners`, `formula configuration issues`, `invalid configuration`, `reloadable/reportable custom fields`, and `statement setup`.
	- **Launch Compensation Worksheets**:
		- Navigate to *Manage Worksheets* → *Create Worksheets*.
		- Enter worksheet name, start/end dates, and due date.
		- Select the top-level manager/planner.
		- Consider options like `Include Inactive Users`, `Create worksheet for head of Planning only` (for testing), and `Send Email Notifications`.
		- For OmniVerse Energy Ltd., if worksheets need to be launched at different times for different groups (e.g., by country or division), create **Employee Groups** and select `Create worksheets by employee group` and `Do not duplicate employees on worksheets` in *Advanced Settings*.
		- **Monitor job status** using *Monitor Compensation Jobs* in Admin Center or Provisioning.
	- **Update Worksheets**:
		- Some data changes (e.g., guidelines with optimization, pay matrix updates) reflect automatically. Other changes require manual updates.
		- **Update All Worksheets** (for a template) or **Update a Specific Worksheet**.
		- Options include adding new employees, creating worksheets for new managers, removing inactive employees/planners, updating eligibility, and updating budget.
		- **Manage Employee Membership** to move, delete, or add employees to worksheets.
	- **Delete Worksheets**:
		- For small numbers (under 100), use *Manage Worksheets*.
		- For larger numbers (over 100), use *Delete Document* via *Admin Center* → *Manage Employees* → *Manage Forms by User*.
		- Enable automatic purging of deleted worksheets for performance improvement. Explore Data Retention Management (DRM) and Data Retention Time Management (DRTM) for comprehensive purging.
### Phase 5: Post-Planning and Reporting
1. **Publish Data to SAP SuccessFactors Employee Central**
	- **Map Source to Target Fields**: Ensure mapping between Compensation fields and Employee Central entities (`payComponentRecurring`, `payComponentNonRecurring`, `JobInfo`) is defined.
	- **Define ****`componentType`****, ****`componentCode`****, ****`eventReason`****, and ****`effectiveDate`** for new records.
	- **Understand Publishing Behavior**:
		- Recurring pay components: New component created on first publish, subsequent publishes update existing.
		- Non-recurring pay components: Stand-alone, multiple can be published.
		- **Crucial considerations**: Completed forms, business rules (use `Do not trigger EC rules` if needed), forward propagation, unique pay component names, effective dates, and handling of multiple `compInfo` records.
		- Optionally, publish Job Information before Compensation Information. Up to five custom fields can be published if marked as `Reportable`.
	- **Initiate Publishing**: Navigate to *Complete Compensation Cycle* → *Publish Data*. Choose to publish records from all completed forms, selected worksheets, or selected employees. You can also publish to custom MDF objects.
	- **Monitor Publishing Jobs**: Track status in *Monitor Compensation Jobs*.
	- **Generate Employee Central Publish Report**: Use this report to identify overall issues or individual users with problems for troubleshooting.
2. **Generate Reports and Statements**
	- **Run Standard Reports**:
		- **Rollup Reports**: Provides a summary of compensation data and budget information, allowing drill-down into individual worksheets. Enable via RBP and XML tag `<comp-include-report>`.
		- **Aggregate Exports**: Export all compensation data for payroll or external HRIS. Cannot be customized.
		- **Summary Tab**: Overview of figures on Salary, Bonus, Stock tabs.
		- **YouCalc Widgets**: Graphical representation of key data in the Metrics section of worksheets. Customizable.
	- **Utilize Report Center Reports**: OmniVerse Energy Ltd. can create their own reports using a user-friendly builder tool.
		- **Report Table (Ad Hoc Reports)**: Create custom reports (Single, Multi, Cross Domain).
		- **Report Canvas (Online Report Designer)**: Build free-form reports with tables or charts.
		- **Tiles and Dashboards**: Build new analytic tiles and combine them into dashboards.
		- **Insights**: Enable contextual information panels on Compensation Inbox and Worksheets.
	- **Use Executive Review**:
		- View all employees from multiple worksheets on one page, regardless of route map inclusion.
		- **Permissions**: Grant read/edit, mass action, and export permissions.
		- **Filters**: Define population scope (`Individual View`, `Team View`, `Other Filters`) and further narrow down entries. Advanced filters can be shared.
		- **Mass Action**: Facilitate large-scale changes to recommendations (e.g., adjust all lump sums to meet budget). Respects guidelines and budget hard stops.
	- **Audit Tool Reports**:
		- Track who is making changes and what changes are made (before/after values) for worksheets, compensation profiles, and Executive Review.
		- **Enable in production environment**: Requires specific RBP and activation steps in *Manage Audit Configuration*.
	- **Generate Compensation Statements**:
		- **Add Statement Templates**: Use standard templates from SuccessStore or create custom ones.
		- **Edit Templates**: Customize company logo, title, body, add conditional text sections for dynamic content based on worksheet values (e.g., ratings). Custom statements are typically separate projects for advanced needs.
		- **Set and Assign Permissions**: At the plan level, or supersede RBP.
		- **Associate and Assign Templates**: Associate the plan with one or more statement templates. Use Combined Statement Template for multiple plans. Assign a default template.
		- **Create Dynamic Statement Groups**: Assign employees to appropriate reward templates (e.g., by country).
		- **Generate Statements**: Select by personal statement template, employee name, or list of usernames.
		- **Suppress Statements (Optional)**: Prevent generation for select employees based on custom string columns (e.g., no pay change).
		- **Download and Print Statements**: Bulk or individually, by administrators, planners, or employees via People Profile.
		- **Generate Statement Notifications**: Send system-generated emails to employees.
		- **Reward Statement Generation Report**: Generate a CSV report to identify employees with/without statements.
		- **Recall Statements**: If needed, recall statements (newly generated ones overwrite previous).
		- **Display on People Profile**: Configure statements to be visible on the People Profile for employee access.
		- **Compensation Profile**: Configure history periods to display employee demographic data, compensation history, salary positioning, and recommendations.
This comprehensive sequence will help OmniVerse Energy Ltd. successfully implement the SAP SuccessFactors Compensation module, ensuring all aspects from initial setup to reporting are covered.


---

## Source and maintenance notes
- Source journal captured from Notion on 2026-10-14.
- The original sequence and illustrative client name have been retained; analysis and gate recommendations above are an added implementation lens.
- Before production use, validate each release-sensitive detail against the current SAP SuccessFactors Compensation documentation and the customer's configuration workbook.
