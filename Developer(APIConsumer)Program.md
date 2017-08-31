---
title: Developer Experience
permalink: /developerapiconsumerprogram/
---

Developer experience is a lot like customer experience. It can have a big impact on the end-customer experience of the API-using application as well. Depending on maturity level there are different aspects to developer experience.

Developer experience is linked to both business, product and technical features but also marketing and communications

Developer Portal

*   find the API
*   getting access to it
*   knowing what it can be used for
*   understanding specifications
*   compatibility of features to needs, does using the API save time and effort or bring some advantage that wouldn't be possible without using it
*   suitability of formats, endpoints and authentication
*   non-functional requirements: latency, reliability, security and error handling of the API to suit the needs of a particular application.
*   being able to give geedback , knowing about changes, the image and brand of the company offering the API
*   cost of using it

Developer experience design starts when the API is designed with [API Canvas](../apicanvas) and there are special API consumer related requirements gathered in the architecture phase, see [Collecting architecture requirements](../minimumviableapiarchitecturemvaa/collectingarchitecturerequirements/).

The table below lists typical developer experience affecting resources, tools and processes.

## Developer onboarding topic

* Portal UI design (Company specific, based on branding and content creation guidelines)
* Content and communication guidelines
  * All API documentation should be generated from API Product and OpenAPI documents and masters should be stored and edited using version control, not directly to API management/portal.
  * Content, language, what information is shared, which channels and formats used, etc.
  * (Company specific, based on branding and content creation guidelines)

* Identity management
  * for API Consuming applications and developers
  * for human users using the applications, which use the APIs
  * API Publishing developers Company users (employees, subcontractors) as API publishing developers
* Securing API backends and passing authorization from API consumer via API management to API backend
* Giving access to APIs requiring approval
  * API visibility and access is controlled via API Products.
    * Developers need to have access to view specific API product in order to subscribe to actually using it
  * Developer subscribes to APIs
    * self-service or
    * self-service with approval workflow
* Terms and conditions for using our APIs
* Monetization (API pricing and payments handling)
* Marketing communication (ads, swag, press releases...)
* Customer stories (testimonials, interviews etc.)
* Release notes / change logs
* Presentations and demos
* SDKs (libraries, API client templates...)
* Plugins and ready made integrations
* Feedback and feature suggestions
