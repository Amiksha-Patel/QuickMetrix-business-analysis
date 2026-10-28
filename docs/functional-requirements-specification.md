# Functional Requirements Specification (FRS) — QuickMetrix V1.0

## Document Information

| Attribute | Details |
|---|---|
| Project Name | QuickMetrix |
| Project ID | QM-2026-001 |
| Document Version | 1.0 |
| Document Status | Portfolio Case Study — Draft |
| Project Methodology | Waterfall |
| Prepared By | Amiksha Patel |
| Related Document | Business Requirements Document (BRD) — QuickMetrix V1.0 |

## 1. Purpose

This Functional Requirements Specification (FRS) defines the expected system behaviour and functional capabilities of QuickMetrix V1.0 based on the business requirements documented in the BRD.

It describes how users will interact with the platform to monitor customer interactions and brand mentions, manage tickets, respond to customers, analyse sentiment, and generate reports.

The FRS will provide a reference for solution design, development, functional testing, and User Acceptance Testing (UAT).

## 2. Scope of This Document

This document covers the functional behaviour planned for QuickMetrix V1.0, including:

- User authentication and access management
- Unified inbox and interaction search
- Sentiment and tag management
- Manual ticket management and escalation
- Notifications and audit trails
- Multi-channel customer responses and canned responses
- Reporting and scheduled reports
- Publishing workflows and content calendar
- Crisis monitoring and command centre

AI chatbot functionality, CRM-based customer segmentation, and other proposed V2.0 enhancements are excluded from this FRS.

**Portfolio disclaimer:** This document describes proposed functionality for a Business Analysis portfolio case study. It does not claim that these requirements were implemented in a live production environment.

## 3. Functional Requirements

### 3.1 User Authentication and Login

#### FR-001: User Login

**Requirement Description:** The system shall allow registered users to log in using their valid credentials.

**Preconditions:**
- The user account exists in the system.
- The user account is active.

**Trigger:** The user opens the login page and submits their credentials.

**Expected System Behaviour:**
1. The system shall display fields for the user's registered email address or configured username and password.
2. The system shall validate the submitted credentials.
3. If the credentials are valid, the system shall authenticate the user and provide access according to the user's assigned role and permissions.
4. If the credentials are invalid, the system shall display an appropriate error message without granting access.
5. The system shall not reveal whether a particular account exists through an overly specific login error message.

**Postconditions:**
- Successful login grants the user access to authorised platform functionality.
- Failed login leaves the user unauthenticated.

**Priority:** Must Have

**Related Business Requirement:** BR-12 — Role-based access and platform user administration.

**Acceptance Criteria:**
- AC-01: Given an active registered user enters valid credentials, when the user submits the login form, then the system authenticates the user and grants access according to assigned permissions.
- AC-02: Given a user enters an incorrect password, when the user submits the login form, then the system denies access and displays an appropriate error message.
- AC-03: Given a user submits incomplete required login fields, when the form is submitted, then the system prompts the user to complete the required fields.
- AC-04: Given an inactive account attempts to log in, when the credentials are submitted, then the system denies access.
- AC-05: Given authentication fails, then the system does not grant access to protected platform functionality.

### FR-002: Password Reset

**Requirement Description:** The system shall allow registered users to initiate a password reset when they cannot remember their current password.

**Preconditions:**
- The user has an account registered with the system.
- The user can access the registered email address or the configured password recovery method.

**Trigger:** The user selects the *Forgot Password* option on the login page.

**Expected System Behaviour:**
1. The system shall provide a password recovery option on the login page.
2. The system shall allow the user to submit the registered email address or other configured account identifier.
3. The system shall initiate the password recovery process using the configured verification method.
4. The system shall provide an appropriate confirmation message after the request is submitted without unnecessarily revealing whether an account exists.
5. The system shall allow the user to set a new password after successful verification.
6. The system shall validate the new password against the configured password policy.
7. The system shall confirm when the password reset is completed successfully.

**Postconditions:**
- After a successful reset, the user can log in using the new password.
- If verification fails or the reset process is incomplete, the password remains unchanged.

**Priority:** Must Have

**Related Business Requirement:** BR-12 — Role-based access and platform user administration.

**Acceptance Criteria:**
- AC-01: Given a user is on the login page, when they select *Forgot Password*, then the system displays the password recovery process.
- AC-02: Given a user submits a recovery request, then the system displays a confirmation message without unnecessarily disclosing account existence.
- AC-03: Given a user completes the required verification, when they enter a valid new password, then the system updates the password.
- AC-04: Given a user enters a password that does not meet the configured policy, then the system rejects it and explains the password requirements.
- AC-05: Given a password reset is completed successfully, when the user logs in with the new password, then the system grants access if the account is active.

### FR-003: User Profile Management

**Requirement Description:** The system shall allow authenticated users to view their profile information and update permitted profile fields.

**Preconditions:**
- The user has successfully logged in.
- The user has an active account.

**Trigger:** The user opens the profile section from the platform.

**Expected System Behaviour:**
1. The system shall display the authenticated user's available profile information.
2. The system shall allow the user to edit permitted fields, such as display name and contact details, where configured.
3. The system shall validate updated information before saving changes.
4. The system shall save valid changes and display a confirmation message.
5. The system shall display an appropriate error message if the update fails.
6. The system shall prevent users from changing restricted fields, roles, or permissions through their own profile.
7. The system shall retain existing information when an update fails.

**Postconditions:**
- Valid profile changes are saved and displayed to the user.
- Unauthorised changes are rejected.

**Priority:** Must Have

**Related Business Requirement:** BR-12 — Role-based access and platform user administration.

**Acceptance Criteria:**
- AC-01: Given an authenticated user opens their profile, when the profile loads, then the system displays the user's available profile information.
- AC-02: Given a user edits a permitted field with valid information, when they save the changes, then the system stores and displays the updated information.
- AC-03: Given a user enters invalid information, when they attempt to save, then the system rejects the invalid data and displays an appropriate message.
- AC-04: Given a user attempts to change a restricted field or their own role, then the system prevents the unauthorised change.
- AC-05: Given a profile update fails, then the system retains the previously saved information.

### FR-004: Platform User Administration

**Requirement Description:** The system shall allow authorised administrators to create, view, update, activate, and deactivate platform user accounts according to their assigned permissions.

**Preconditions:**
- The administrator has successfully logged in.
- The administrator has the required user-management permissions.

**Trigger:** The administrator opens the user administration section.

**Expected System Behaviour:**
1. The system shall display a list of platform user accounts with available details, such as name, username or email, assigned role, and account status.
2. The system shall allow authorised administrators to create new user accounts by entering the required information.
3. The system shall validate mandatory fields and prevent duplicate accounts based on configured unique identifiers.
4. The system shall allow administrators to update permitted user details and assigned roles.
5. The system shall allow administrators to activate or deactivate user accounts.
6. The system shall prevent unauthorised users from accessing user administration functions.
7. The system shall display a confirmation message after a successful operation and an appropriate error message if an operation fails.
8. The system shall record relevant user-administration actions in the audit trail, where audit logging is configured.

**Postconditions:**
- Successful changes are reflected in the relevant user account.
- Unsuccessful operations do not result in unintended account changes.

**Priority:** Must Have

**Related Business Requirement:** BR-12 — Role-based access and platform user administration.

**Acceptance Criteria:**
- AC-01: Given an authorised administrator opens user administration, when the page loads, then the system displays the available user accounts.
- AC-02: Given an administrator enters valid information for a new user, when they submit the form, then the system creates the account.
- AC-03: Given mandatory information is missing or a unique identifier already exists, when the administrator submits the form, then the system rejects the request and identifies the validation issue.
- AC-04: Given an administrator updates permitted user details or roles, when the changes are saved successfully, then the system displays the updated information.
- AC-05: Given an administrator deactivates an account, when the operation succeeds, then the account status changes and the user cannot log in while the account remains inactive.

### FR-005: Unified Inbox

**Requirement Description:** The system shall display customer interactions and brand mentions retrieved from configured, supported digital channels in a centralised inbox.

**Preconditions:**
- The user has successfully logged in.
- The user has permission to access the unified inbox.
- The relevant digital channels are configured and accessible.

**Trigger:** The user opens the unified inbox.

**Expected System Behaviour:**
1. The system shall display interactions retrieved from configured, supported digital channels in a consolidated view.
2. The system shall display available interaction details, such as message or post content, source channel, author, timestamp, and associated brand, where the source data provides these fields.
3. The system shall display the most recent week's interactions by default.
4. The system shall allow users to view available interaction details without navigating to each native platform individually.
5. The system shall provide access to interaction filtering and search capabilities defined in the relevant requirements.
6. The system shall indicate when no interactions match the selected view or filters.
7. The system shall display an appropriate message when interaction data cannot be retrieved from a configured channel.
8. The system shall restrict access to inbox data according to the user's assigned permissions.

**Postconditions:**
- The user can view available interactions in a centralised inbox.
- The displayed interactions reflect the data retrieved from configured channels and the selected view.

**Priority:** Must Have

**Related Business Requirements:** BR-01 — Centralised inbox; BR-02 — Interaction filtering and search.

**Acceptance Criteria:**
- AC-01: Given a user has inbox access and configured channels are available, when the user opens the inbox, then the system displays retrieved interactions from those channels in one view.
- AC-02: Given interactions are available from the most recent week, when the user opens the inbox without changing the default view, then the system displays interactions from that period.
- AC-03: Given interaction records contain source details, when the records are displayed, then the system shows the available channel, author, timestamp, and content information.
- AC-04: Given no interactions match the selected view, when the inbox loads, then the system displays an appropriate empty-state message.
- AC-05: Given a configured channel cannot provide interaction data, when the inbox attempts to retrieve that data, then the system communicates the retrieval issue without misrepresenting unavailable data as successfully retrieved.
