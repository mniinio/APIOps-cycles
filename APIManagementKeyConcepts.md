---
title: API Management Key concepts
slug: APIManagementKeyConcepts
---

## Value proposition

Value proposition describes the value to be delivered by using a specific product or product range. APIs are products and just like in all products, users will need a good reason (=value proposition) to decide to use it (=conversion).

*   How API Product in question solves problems or improves situation
*   What specific benefits there is to use this specifc API instead of other integration methods?
*   Why external partners or customers should use our API in stead of competitors'? (think about this if you are offering the API to external parties)

## API Product manager (or product owner)

Traditional product managers are commercially and analytically oriented persons who rely on tools like market research and user studies, and works with sales, marketing, and other stakeholders to create a product that will sell. In Agile development, product owner has typically less commercial responsibilities but is still a customer / stakeholder advocate and prioritizes items in the backlog according to the value they bring to the the customers.

The technical nature of APIs as products requires API Product owners to translate the value proposition into technical capabilities and the technical capabilities into business terms.

Customers of API Product owners are software and technology developers, but also business developers of customers and partners. API Product owner needs to understand the specific nature and needs of these user groups. They also need to translate these as capabilities that his own team of backend developers understand and can actually build.

One major task of API Product Manager is to explain and mitigate the risks and values of opening their company's data and value propositions to the world as a platform and also figure out how to build customer value from networks of other companies and their API using or offering products.

API Product managers require great communication, business and technical skills.

## Application service manager

CRM application serves as an (indirect or direct) backend for specific APIs. Any changes to the CRM or any service breaks may effect the APIs depending on it and the API consuming applications. Any needs to add or make changes to the dependent APIs may require changes in the application serving as a backend. If requirements come from other teams or external partners and customers, funding and priority must be negotiated. Service manager needs to do release plans, change requests and service break down notifications minding the APIs and API consumers. Requirements depend on architecture and dependency of the API layer.

## Information architect

Responsible for designing how requirements need to be split into independent APIs, endpoints and attributes and how to negotiate requirements between payload sizes, privacy and confidentiality requirements, local legal requirements and business processes. In charge of making sure the naming standards and values are valid also outside the company data architecture and naming conventions. Ideally creates guidelines for API publishing developers and conducts reviews.

## Developer segments

Developers are our API consumers, but also your potential paying customers, sales channel, outsourcing partners or innovation partners. Each segment has their own reasons why we are interested in them and they are interested in us, as well as their own unique needs, behaviors and logic.

Typical developer segments regarding APIs are

*   Business developers (selling and or developing new business models, products and services, which use our APIs)
*   Software developers (software applications, which use APIs)
*   Technology developers (devices, which use APIs)

It may be useful to split the segments even more, to internal developers and external developers or according to the product or platform segment or their interface expectation or their knowledge and skills about our company, our products or using APIs in general.

## User groups

Depending on API management product, there may be different names for specific default user groups and usually all management products allow creating company specific user groups.

Usually users related to APIs are divided into these high level groups

*   Guest users or unauthenticated users, who can see available APIs but can not make API calls
*   API consuming developers
*   API publishing developers
*   API management platform administrators (users who can administrate network settings, API publishing user accounts, overall security settings etc).

In big companies these user groups need to almost always be separated into smaller user groups, as not all consumers are allowed to use all APIs (private or partner APIs) and not all teams of API providing developers can even see, know or administrate all APIs.

API management product specific information and guidelines about roles

*   [<u>Microsoft Azure API management</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-create-groups)
*   <u>[IBM API Connect - User roles](https://www.ibm.com/support/knowledgecenter/en/SSMNED_5.0.0/com.ibm.apic.overview.doc/overview_apimgmt_users.html)</u> and [Recommended roles for API Initiative](https://developer.ibm.com/apiconnect/2017/05/19/recommended-roles-api-initiative/)
