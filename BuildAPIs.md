---
title: Build APIs

permalink: /buildapis/
---

API Architecture centers around individual microservices that provide value via APIs with a JSON payload. APIs in most simplest form expose what systems do and therefore are highly valuable business assets. Compared to SOA Web Service Integration style, RestAPIs are centered around business entities exposed as resources that are identified via URIs and can be manipulated via standardized Create, Read, Update and Delete (CRUD) methods.

## Before starting to build APIs

API Design makes sure your APIs succesful. If the design principles are set in the initial stage, the quality can be quaranteed and the API are easy to implement, easy to use and developer friendly.

*   [API Canvas](apicanvas.md) - APIs business requirements, API consumers, services needing to be built and the existing services available as API canvas?
*   [Minimum Viable API Architecture (MVAA)](MinimumViableAPIArchitecture-MVAA.md) - non-functional and funcational requirements should have been gathered using the design templates?
*   Also check the [API Audit](apiaudit.md) and [API design style guide](APIDesignStyleGuide.md) for guidelines on implementation
*   Design application architecture based on the environment where the API -backends are build. Estimate runtime costs at this point.
*   Setup automatical deployments, test-automation and API publishing pipelines (this requires own guide when environment and API management platform has been selected)
