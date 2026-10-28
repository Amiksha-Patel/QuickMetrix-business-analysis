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
