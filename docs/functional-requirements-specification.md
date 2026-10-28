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

### FR-006: Interaction Filtering and Advanced Search

**Requirement Description:** The system shall allow authorised users to search and filter interactions in the unified inbox using available search criteria.

**Preconditions:**
- The user has successfully logged in.
- The user has permission to access the unified inbox.
- Interaction records are available in the system.

**Trigger:** The user enters a search term or selects one or more filters in the unified inbox.

**Expected System Behaviour:**
1. The system shall allow users to search interactions using supported keywords or text fields.
2. The system shall allow users to filter interactions by available criteria, such as source channel, date range, sentiment, tags, and ticket status where applicable.
3. The system shall allow users to combine multiple supported filters.
4. The system shall display interactions that match the entered search criteria and selected filters.
5. The system shall allow users to clear applied filters and return to the default inbox view.
6. The system shall display an appropriate message when no interactions match the search or filter criteria.
7. The system shall apply search and filtering only to interaction data the user is authorised to access.

**Postconditions:**
- The inbox displays interactions matching the user's search and filter selections.
- Clearing the filters restores the default inbox view.

**Priority:** Must Have

**Related Business Requirement:** BR-02 — Interaction filtering and search.

**Acceptance Criteria:**
- AC-01: Given interactions are available, when a user enters a supported keyword, then the system displays matching interactions.
- AC-02: Given interactions have channel, date, sentiment, or tag information, when a user applies a supported filter, then the system displays interactions matching that filter.
- AC-03: Given multiple filters are supported, when a user applies more than one filter, then the system displays interactions matching the combined criteria.
- AC-04: Given filters have been applied, when the user clears them, then the system restores the default inbox view.
- AC-05: Given no interactions match the selected search or filters, when the search is executed, then the system displays an appropriate empty-state message.

### FR-007: Sentiment and Tag Management

**Requirement Description:** The system shall allow authorised users to view and manage sentiment labels and tags associated with interactions.

**Preconditions:**
- The user has successfully logged in.
- The user has permission to access the relevant interactions.
- Interaction records are available in the system.

**Trigger:** The user opens an interaction or chooses to review or update its sentiment label or tags.

**Expected System Behaviour:**
1. The system shall display the sentiment label and tags associated with an interaction, where available.
2. The system shall allow authorised users to update the sentiment label of an interaction.
3. The system shall allow authorised users to add or remove tags from an interaction.
4. The system shall display the updated sentiment label and tags after the changes are saved.
5. The system shall validate user permissions before allowing changes.
6. The system shall display an appropriate message if an update cannot be saved.
7. The system shall retain the existing values if an update fails.

**Postconditions:**
- The interaction displays the saved sentiment label and tags.
- Unsuccessful updates do not overwrite the existing saved values.

**Priority:** Must Have

**Related Business Requirement:** BR-03 — Sentiment and tag management.

**Acceptance Criteria:**
- AC-01: Given an interaction has a sentiment label, when an authorised user opens it, then the system displays the available sentiment label.
- AC-02: Given an authorised user has permission to update sentiment, when the user selects and saves a new sentiment label, then the system displays the updated label.
- AC-03: Given an authorised user has permission to manage tags, when the user adds a valid tag, then the system associates the tag with the interaction.
- AC-04: Given an interaction has existing tags, when an authorised user removes a tag and saves the change, then the removed tag is no longer associated with the interaction.
- AC-05: Given an update fails, when the system processes the change, then it displays an appropriate message and retains the previously saved values.

### FR-008: Manual Ticket Creation

**Requirement Description:** The system shall allow authorised users to manually create a ticket from an available customer interaction or brand mention.

**Preconditions:**
- The user has successfully logged in.
- The user has permission to create tickets.
- An eligible interaction is available, or the user has access to the manual ticket creation function.

**Trigger:** The user selects an interaction and chooses to create a ticket, or initiates ticket creation through the available interface.

**Expected System Behaviour:**
1. The system shall allow authorised users to initiate ticket creation manually.
2. The system shall allow users to associate a ticket with an existing interaction, where applicable.
3. The system shall capture the required ticket information, such as subject or summary, description, source channel, and relevant interaction details where available.
4. The system shall validate mandatory fields before saving the ticket.
5. The system shall generate a unique ticket reference upon successful creation.
6. The system shall assign the ticket an initial status according to the configured workflow.
7. The system shall display a confirmation message and the newly created ticket details after successful creation.
8. The system shall display an appropriate validation or error message if the ticket cannot be created.
9. Ticket creation shall be initiated by an authorised user; automatic ticket creation is outside the scope of V1.0.

**Postconditions:**
- A successfully created ticket is stored with a unique reference and initial status.
- The ticket is associated with the selected interaction when applicable.

**Priority:** Must Have

**Related Business Requirement:** BR-04 — Manual ticket creation and management.

**Acceptance Criteria:**
- AC-01: Given an authorised user has access to an eligible interaction, when the user initiates ticket creation, then the system opens the ticket creation interface.
- AC-02: Given mandatory ticket fields are incomplete, when the user attempts to save the ticket, then the system identifies the missing required information.
- AC-03: Given all mandatory fields contain valid information, when the user saves the ticket, then the system creates the ticket and generates a unique reference.
- AC-04: Given a ticket is created successfully, when the system confirms the creation, then the ticket displays its initial configured status.
- AC-05: Given a ticket is created from an existing interaction, when the ticket is saved, then the system maintains the association between the ticket and that interaction.
