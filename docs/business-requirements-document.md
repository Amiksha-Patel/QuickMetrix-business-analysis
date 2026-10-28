## 1. Business Problem Statement

Organisations receive customer interactions and brand mentions across multiple digital channels, including social media platforms. Monitoring these interactions manually through individual native platforms is time-consuming and inefficient, as teams must navigate between platforms, open individual posts or comments, and check mentions and tags to identify relevant conversations.

This fragmented approach makes it difficult to maintain a consolidated view of customer interactions, track sentiment trends, manage responses efficiently, monitor ticket status, and generate comprehensive reports.

QuickMetrix V1.0 aims to address these challenges by providing a centralised platform to monitor and manage customer interactions and brand mentions across multiple digital channels, supporting streamlined workflows, sentiment analysis, ticket tracking, and consolidated reporting.

## 2. Business Objectives

The objectives of QuickMetrix V1.0 are to:

1. **Centralise Monitoring:** Provide a unified view of customer interactions and brand mentions across multiple digital channels.
2. **Improve Operational Efficiency:** Reduce the need for ORM analysts to navigate individual native platforms to monitor posts, comments, mentions, and tags.
3. **Support Sentiment Analysis:** Enable users to identify and track customer sentiment to better understand audience perceptions.
4. **Streamline Interaction Management:** Allow authorised users to create tickets manually, assign them to agents, update ticket statuses, and track interactions through resolution.
5. **Improve Response Management:** Support consistent customer communication through multi-channel responses and reusable canned responses.
6. **Enable Consolidated Reporting:** Provide centralised reports and analytics to help teams monitor interaction volumes, sentiment trends, and operational performance.
7. **Strengthen Monitoring and Escalation:** Provide notifications, alerts, and escalation workflows to help teams identify and manage important interactions.

## 3. Project Scope

### 3.1 In Scope — V1.0

The QuickMetrix V1.0 case study includes the following capabilities:

- User login, role-based access, password reset, and profile management
- Platform user administration
- Unified inbox with a default view of the most recent week
- Interaction filtering, advanced search, and bulk actions
- Sentiment and tag management
- Manual ticket creation, assignment, status updates, and escalation
- Notifications, alerts, and ticket audit trails
- Multi-channel customer responses and canned responses
- Reporting, analytics, and scheduled report delivery
- Publishing workflows and content calendar
- Crisis management and a real-time command centre

**Ticket management clarification:** Authorised users create tickets, assign them to agents, and update statuses manually. Automated ticket creation and AI-based ticket assignment are excluded from V1.0.

### 3.2 Out of Scope — V1.0

The following capabilities are excluded from the V1.0 scope:

- AI chatbot functionality
- CRM enhancements and CRM-based customer segmentation
- Native mobile application development
- Influencer management enhancements
- Third-party integration enhancements planned for V2.0
- Help Center enhancements planned for V2.0

These capabilities may be considered as part of the proposed V2.0 roadmap.

### 3.3 Scope Boundary

V1.0 focuses on centralised interaction monitoring, manual ticket management, customer response workflows, sentiment tracking, and consolidated reporting. The proposed V2.0 enhancements will be documented separately and are not considered delivered functionality.

## 4. Stakeholder Identification

| Stakeholder | Role and Responsibility |
|---|---|
| Project Sponsor | Provides business direction, approves key project decisions, and ensures alignment with business objectives. |
| Project Manager | Coordinates project activities, timelines, resources, risks, and stakeholder communication. |
| ORM Analyst | Monitors customer interactions and brand mentions, analyses sentiment, manages tickets, and prepares reports. |
| ORM Team Lead / Manager | Oversees ORM operations, monitors team performance, manages escalations, and reviews reporting outputs. |
| Customer Care Agent | Handles assigned tickets and responds to customer interactions through supported channels. |
| Platform Administrator | Manages user accounts, roles, permissions, and platform configuration. |
| Business Analyst | Elicits, analyses, documents, and validates business requirements and coordinates with stakeholders to clarify expectations. |
| Development Team | Uses approved requirements to design, configure, and develop the planned functionality. |
| QA / Testing Team | Verifies that the solution meets documented requirements and identifies defects during testing. |

**Note:** These stakeholders represent the proposed project structure for this portfolio case study. Their inclusion does not imply that the project was implemented in a live production environment.

## 5. Business Requirements

| Requirement ID | Business Requirement | Business Rationale | Priority |
|---|---|---|---|
| BR-01 | The system shall provide a centralised inbox for customer interactions and brand mentions from supported digital channels. | Reduce the need to monitor each native platform separately. | Must Have |
| BR-02 | The system shall allow users to filter and search interactions using available criteria. | Help ORM analysts locate relevant conversations efficiently. | Must Have |
| BR-03 | The system shall support sentiment identification and tagging of interactions. | Help teams understand customer perceptions and identify sentiment trends. | Must Have |
| BR-04 | The system shall allow authorised users to create tickets manually, assign them to agents, and update ticket statuses. | Establish a consistent process for tracking customer interactions. | Must Have |
| BR-05 | The system shall support ticket escalation, notifications, and alerts. | Help teams identify and manage interactions that require attention. | Must Have |
| BR-06 | The system shall support customer responses across configured communication channels. | Enable ORM teams to manage customer communication through the platform. | Must Have |
| BR-07 | The system shall provide reusable canned responses. | Improve consistency and efficiency when handling recurring queries. | Should Have |
| BR-08 | The system shall provide consolidated reports and analytics on interactions and sentiment trends. | Support operational monitoring and business decision-making. | Must Have |
| BR-09 | The system shall support scheduled report delivery. | Reduce manual effort in recurring reporting activities. | Should Have |
| BR-10 | The system shall support publishing workflows and a content calendar. | Help teams plan and manage social media publishing activities. | Should Have |
| BR-11 | The system shall provide crisis monitoring through a centralised command centre. | Help teams monitor potentially critical brand interactions. | Should Have |
| BR-12 | The system shall support role-based access and platform user administration. | Ensure users access functionality according to their responsibilities. | Must Have |
| BR-13 | The system shall maintain ticket activity records and audit trails. | Support traceability of ticket updates and actions. | Should Have |

**Note:** These are proposed business-level requirements for the portfolio case study. Detailed functional requirements, acceptance criteria, and validation scenarios will be documented separately in subsequent artefacts.

## 6. Assumptions and Constraints

### 6.1 Assumptions

- The organisation has access to the digital channels supported by the QuickMetrix platform.
- Customer interactions and brand mentions can be retrieved from supported channels through configured integrations or platform connections.
- ORM analysts and authorised users will manually create tickets, assign them to agents, and update ticket statuses.
- Sentiment identification and tagging capabilities will be available to support interaction analysis.
- Users will receive access according to their assigned roles and permissions.
- Business users will participate in requirements validation and user acceptance testing.
- Reporting outputs will depend on the availability and quality of interaction data.

### 6.2 Constraints

- V1.0 functionality is limited to the approved project scope documented in this case study.
- Access to digital-channel data depends on the permissions, APIs, and limitations of the respective platforms.
- Automated ticket creation and AI-based ticket assignment are excluded from V1.0.
- AI chatbot functionality, CRM-based customer segmentation, and other planned enhancements are reserved for the proposed V2.0 scope.
- Native mobile application development is excluded from V1.0.
- The case study does not claim actual production deployment, measured business benefits, or verified implementation outcomes.

## 7. Business Success Criteria

QuickMetrix V1.0 will be considered successful when the following criteria are met during solution validation:

1. **Centralised Monitoring:** Users can view interactions and brand mentions from configured, supported digital channels in a unified inbox.
2. **Efficient Interaction Retrieval:** Users can filter and search interactions using the available search criteria.
3. **Sentiment and Tag Visibility:** Users can identify sentiment and apply or review tags to support interaction analysis.
4. **Traceable Ticket Management:** Authorised users can manually create tickets, assign them to agents, update statuses, and review ticket activity.
5. **Effective Escalation:** Notifications, alerts, and escalation workflows operate according to the documented requirements.
6. **Consistent Customer Communication:** Users can respond through supported channels and access reusable canned responses.
7. **Consolidated Reporting:** Users can generate reports that summarise relevant interaction data and sentiment trends.
8. **Controlled Access:** User roles and permissions restrict access according to defined responsibilities.
9. **Publishing and Crisis Monitoring:** Users can access the planned publishing workflows, content calendar, and crisis monitoring capabilities included in V1.0.

**Validation approach:** These criteria will be evaluated through requirements reviews, functional testing, and user acceptance testing (UAT). Quantitative performance targets should be defined separately where required.

**Portfolio disclaimer:** These are proposed success criteria. They do not represent verified results from a live production implementation.
