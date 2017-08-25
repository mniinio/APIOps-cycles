---
title: Developer Program
permalink: /developerapiconsumerprogram/
---

Developer experience is a lot like customer experience. It can have a big impact on the end-customer experience of the API-using application as well. Depending on maturity level there are different aspects to developer experience.

Developer experience is linked to both business, product and technical features but also marketing and communications

*   about finding the API
*   getting access to it
*   knowing what it can be used for
*   understanding specifications
*   compatibility of features to needs, does using the API save time and effort or bring some advantage that wouldn't be possible without using it
*   suitability of formats, endpoints and authentication
*   non-functional requirements: latency, reliability, security and error handling of the API to suit the needs of a particular application.
*   being able to give geedback , knowing about changes, the image and brand of the company offering the API
*   cost of using it

Developer experience design starts when the API is designed with <ac:link><ri:page ri:content-title="1\. API Canvas"></ri:page></ac:link>and there are special API consumer related requirements gathered in the architecture phase, see <ac:link><ri:page ri:content-title="Collecting architecture requirements"></ri:page></ac:link>.

The table below lists typical developer experience affecting resources, tools and processes.

## Developer onboarding topic

* Portal UI design (Company specific, based on branding and content creation guidelines)
  * [<u>Azure API management guide</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-modify-content-layout)
  * [IBM API Connect - Customizing the API Connect Developer Portal](https://developer.ibm.com/apiconnect/2017/07/19/customizing-api-connect-developer-portal/)
  
* Content and communication guidelines
  * All API documentation should be generated from API Product and OpenAPI documents and masters should be stored and edited using version control, not directly to API management/portal.
  * Content, language, what information is shared, which channels and formats used, etc.
  * (Company specific, based on branding and content creation guidelines)

* Identity management
  * API Consuming developers
    * Company users (employees, partners, customers) as API consuming developers ([<u>Azure AD</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-aad)), [<u>Azure AD groups</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-aad#how-to-add-an-external-azure-active-directory-group) can be used for user groups
    * Individual persons (consumers) as API consuming developers ([<u>Azure AD B2C</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-aad-b2c))
    * Using other identity and authentication providers for API consuming developers ([<u>Delegated authentication</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-setup-delegation)) 

* API Publishing developers
  * Company users (employees, subcontractors) as API publishing developers ([<u>Azure AD</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-aad)), [<u>Azure AD groups</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-aad#how-to-add-an-external-azure-active-directory-group) can be used for user groups

* Securing API backends and passing authorization from API consumer via API management to API backend
  * Microsoft Azure and AD As OAuth 2.0 provider

* Giving access to APIs requiring approval
  * API visibility and access is controlled via API Products.
    * Developers need to have access to view specific API product in order to subscribe to actually using it: [<u>Making API Product visible to developers</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-add-products#a-namemake-visible-amake-a-product-visible-to-developers).
  * Developer subscribes to APIs
    * self-service in Developer portal or
    * [<u>subscription can be added in Publisher portal</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-product-with-rules#a-namesubscribe-account-ato-subscribe-a-developer-account-to-the-product) by administrator.
  * Workflow for handling each individual developer subscription
    * when [<u>publishing an API product</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-add-products#a-nameadd-description-aadd-descriptive-information-to-a-product), set the "Require subscription approval" enabled

* Terms and conditions for using our APIs
  * Based on [<u>template</u>](https://wiki.digia.com/display/INTEGRATION/Valmet+API+Strategy+DRAFT) and legal department requirements before allowing external developers to use APIs
  * Requiring users to view and accept terms and conditions when signing up to the developer portal or when subscribing to a specific API can be done by editing / linking content to the [<u>page templates</u>](https://docs.microsoft.com/en-us/azure/api-management/api-management-developer-portal-templates) or to each APIs product description 

* Monetization (API pricing and payments handling)
  * [How to monetize APIs with Azure API Management](https://blogs.msdn.microsoft.com/apimanagement/2016/06/30/how-to-monetize-apis-with-azure-api-management/)
  * [IBM API Connect - Getting started with monetization](https://developer.ibm.com/apiconnect/2017/07/10/getting-started-monetization-apic-v5072/)  

* Marketing communication (ads, swag, press releases...)
  * Customer stories (testimonials, interviews etc.)

* Release notes / change logs
  * In all maturity levels. In Maturity level 3 and 4 release notes need to be made public and major release information needs to be pushed to developer community as there can be breaking changes.
  * Update each APIs release notes to APIs own page (either as part of CI process or manually) 

* Presentations and demos

* SDKs (libraries, API client templates...)
  * Depending on API consumer group specific requirements

* Plugins and ready made integrations
  * Possibly to [Azure Apps](https://azure.microsoft.com/en-us/services/app-service/)

* Feedback and feature suggestions
  * Email address and/or JIRA project for collecting internal and external feature suggestions? Possibly a feedback widget / form / email address in the developer portal
