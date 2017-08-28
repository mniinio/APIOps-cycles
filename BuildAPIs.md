---
title: Build APIs
permalink: /buildapis/
---

API Architecture centers around individual microservices that provide value via APIs with a JSON payload. APIs in most simplest form expose what systems do and therefore are highly valuable business assets. Compared to SOA Web Service Integration style, RestAPIs are centered around business entities exposed as resources that are identified via URIs and can be manipulated via standardized Create, Read, Update and Delete (CRUD) methods.

APIs can be divided to **public, private and partner** APIs based on their usage.

* **Private APIs** are allowed to be used only by own applications. They contain attributes and data which is business critical and confidential.
* **Partner APIs** are available for third party organizations upon approval of partnership terms and conditions. Partner APIs may contain partner specific or customer data which is not available for general public. Partner is liable for the use of the data according to terms and conditions. Partner maybe required to restrict the access of their end-users to the data. F.eg. Partner may access detailed price and purchase data of all stores, but each retailer using partner’s application can only access data of their own store.
* **Public APIs** can be used by anyone without specific approval. APIs can still be authenticated with client id and secret to enforce rate limits and some general terms of use may apply.

## Before starting to build APIs

API Design makes sure your APIs succesful. If the design principles are set in the initial stage, the quality can be quaranteed and the API are easy to implement, easy to use and developer friendly.

*   [API Canvas](../apicanvas) - APIs business requirements, API consumers, services needing to be built and the existing services available as API canvas?
*   [Minimum Viable API Architecture (MVAA)](../minimumviableapiarchitecturemvaa) - non-functional and functional requirements should have been gathered using the design templates?
*   Also check the [API Audit](../apiaudit) and [API design style guide](apidesignstyleguide) for guidelines on implementation
*   Design application architecture based on the environment where the API -backends are build. Estimate runtime costs at this point.
*   Setup automatical deployments, test-automation and API publishing pipelines (this requires own guide when environment and API management platform has been selected)
