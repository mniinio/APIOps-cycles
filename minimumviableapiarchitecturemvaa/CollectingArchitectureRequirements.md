---
title: Collecting Architecture Requirements
permalink: /minimumviableapiarchitecturemvaa/collectingarchitecturerequirements/
parenturl: /minimumviableapiarchitecturemvaa/
---

We’ll take 5 views on architecture development making sure we

*   come to handle all relevant layers of architecture
*   we only design and implement those pieces which we really need and only when we absolutely have to
*   all architecture decisions are based on business requirements
*   architecture considers privacy and security aspects as well as physical and geopolitical locations
*   approach uses solid well known architecture design principles (TOGAF) but in the leanest possible way. We concentrate only on one API product at a time using lean Minimum Viable Architecture approach

If you are an enthusiastic TOGAF user and wonder how this document and approach relates to it:

*   This approach is more holistic combined to TOGAF ADM which treats business, systems and technology architecture as separate phases.
*   We'll concentrate on typical API-related requirements, so they can be communicated to the "builders" of the solution.
*   In the build phase we'll measure and test against those requirements. The actual result of the build phase is guided by our API-centered used of the Minimum Viable Architecture approach.
*   Goal: Clear requirements and working validatable prototypes or software over excessive planning and design documents.

## Before continuing, check these

1.  API Canvas and API Value Proposition Canvas have been filled properly
2.  We know the scope of the design. Specifically, that we know "what API" are we collecting requirements for. The "API" in this case, is the interface and services which full fill the value proposition in the API Canvas. Concentrate on those features which are missing. All existing services fulfilling the value proposition should have been defined in the "Key resources" section in the API Canvas.
3.  Look at the Minimum Viable Architecture method. Check what phase is the API in? Are we planning a prototype, designing a “just enough” architecture or scaling up? 

## Business impact identification

This phase tries to find the potential risks related to the usage of the API. Focus is on impact of those risks, so architecture can be designed to mitigate (or ignore) them.

This phase corresponds to the risk matrix filling in a project plan. Focus is in concrete issues which are typical for APIs. These are issues which are often overlooked before production use.

Why they are often overlooked? Because the relevance of these issues varies and depends on the impact to business. Priority and methods of mitigating are business area and API dependent.

### How to use the Business Impact -template?

Interview

*   customer service, account manager, partner manager
*   business (process) owners
*   project manager
*   service manager to understand the real impact and possibilities to mitigate.

Risk areas in the template:

*   API availability
*   API security and privacy
*   problems in API data

The goal here is to find the impact, not necessarily the exact solution for mitigation. Mention any clear and existing work arounds. These are for example having default values, using manual process or just living with the situation temporarily. The actual mitigation plan can be done just before starting the building phase. Purpose of this template is to remind the team to design, implement and test these requirements.

Additionally, more traditional risks can and should be considered. These are related to

*   schedule
*   profitability, cost
*   technical resources (for example other APIs or services this API depends on and their schedule and roadmap)
*   People and skills. How familiar is the functionality, existing solutions and technology and platforms used

These risks should be also evaluated and mitigated as part of the project or service planning.

## Capacity

Goal is to understand how much traffic will hit the API during it's first weeks and how fast are we anticipating that the traffic will grow. The idea is to use the Minimum Viable Architecture approach so we design and build only as robust architecture as we need right now so we can optimize the work, schedule, complexity and cost. But we also need to know what the current understanding of the speed of needing to scale up is, so we can measure, analyze and decide when more planning and re-designing the architecture is possibly needed.

### How to use the Capacity template?

Draw the scale and estimated amounts vs. calendar time to the template, using business measures such as number of orders coming in or number of customers created, updated or search:

*   New orders in a month
*   Day
*   Minute
*   Second

The reason for using business measures and not API request amounts is that at this stage it's quite impossible to estimate the amount of requests as processed order may require multiple API requests depending on the design. Also it's much more understandable for business users to estimate the actual business transactions or calculate it from their systems. This way it's possible to estimate also bandwith and storage needs later in the process, as there is a possibility to understand how big amount of data is involved in each order and multiply at least by x 3 to get the amount of data transferred in the requests.

If there is an existing solution, ask about any visitor statistics about it. This may be useful as a base line for future usage. Ask about any plans to do big campaigns, launches or changes to the process, business model, amount of users or application architecture of the future API Consumers which could cause much more or less traffic than before.

Try to get some tangible measures, for example how many orders are coming in each month? Are there any peak days or times when lots of customers, customer service or some other group of users would be much more active than normally? Are the API Consuming services "open for business" every day, all day?

If no one has data about how much traffic there is in a minute or second, try to use the monthly data to calculate maximum peak in minute and second. These measures are important for setting rate limits to APIs and API consumers so one API consumer can't easily overload the whole system. It's also important for planning capacity for API gateway, firewalls and other network components and estimating impact on backend systems.

## Where are the data and systems located related to this API?

In this stage, the goal is to discover

*   integration architecture requirements
*   legal and geopolitical requirements and considerations

### How to use the "Locations of Data and Systems" -template?

Identify the related systems and data sources from the API Canvas "Key resources" and "Key partners" sections.

1.  Interview the process owners and/or the owners of the current systems, information architect or solution architects who know the domain and the related systems.
2.  Fill in to the template names of systems to the correct location in the "map". 
    1.  I.e. if the CRM system is related to the APIs in the API Canvas and it's located in local network, write it in the left bottom box. 
    2.  If the CRM system is providing APIs, for example for searching customers and creating and updating them, then mark it in the "Provider" box.
    3.  If it is consuming APIs from other systems, mark the names of those APIs or those systems to the "Consumer" box.
3.  Put applications which are accessible by partners to the "Partner network" boxes. Partners in this context mean customers, vendors, subcontractors, anyone with an agreement and access, typically via VPN, IP restrictions or specific partner user account but only to certain systems or parts of the network.
4.  If some systems are accessible only from a certain country (country-specific organization or actually restricted by location) mark them to "Country-specific network" and also note which country or geopolitical area they can be accessed from e.g. Finland, EU, EEC).
5.  Put systems and data which can be accessed from anywhere in the world and in public internet to the "Different locations globally". It's important to know if this means that the systems are located in multiple locations, if the same data and services need to be read fast from different locations or if different locations have and can have different systems and data, even data models.
6.  If there are multiple systems or if the situation is otherwise very complex, use multiple templates or better yet, write a short description and possibly a network diagram of the situation
7.  Check you have also marked the API Consuming applications in their correct places, at least those someone already knows about but also those in the near future. It's almost always safe to assume there will be users accessing the API from at least public internet and company networks.

### What are legal and geopolitical requirements?

Knowing where data and systems exist and where they can be accessed from is important to know specially for data handling.

There are lots of privacy and other requirements related to specific countries or geopolitical areas.

For example Finnish social security number should not be seen or used outside European union area and data related to Russian citizen needs to be mastered inside Russian borders. Similar legislation exists also in other countries. There may also be trade or national security requirements related to routing, storing or handling data in certain areas.

## API Consumer requirements

Interviewing API consumers and finding their specific requirements concentrates on finding those requirements which are against common best practices (see API style guide), standards and commonly accepted security and privacy requirements set by OWASP, see [https://www.owasp.org/index.php/REST_Security_Cheat_Sheet](https://www.owasp.org/index.php/REST_Security_Cheat_Sheet) .

## Response times and latency

What is the maximum amount of time the API consumer can wait for a response to any request? What is the expected response time for API so they can keep their customers using their system?

### Technical background

*   Estimating response time requirements is a combination of capacity, network locations and API consumer requirements.
*   Some API consumers are more sensitive to response times and there is more latency if the systems are far away from each other and there are multiple systems involved.
*   Also if there is a huge amount of traffic and the requests and responses are big and take lots of processing, the response times are going to be longer.

## Identity, authorization and access management

Is there a need to identify users? What are the common identifiers between the API Consumer and the API (email, customer number, social  security number)? How are the API consumer's end-users authenticated?

Identity management, authorization and access management are important for securing APIs, but also related to the applications consuming and providing the APIs. Sensitive information should always use token and session based access, as the API-keys are usually never changed and are handled in plain language without any encryption, so someone can get access to them.

### Technical background

*   Best approach for securing APIs containing sensitive information and requiring user-level access management is to use OpenID Connect –capable authentication with JWT-tokens and claims.
*   This requires agreeing on how the applications get the token, how is identity of end-users managed etc.
*   Sometimes API consuming clients have limitations on what types of authentication methods they can use.
*   Most consumers can use API-keys in headers, but some can only input URI-parameters. These types of consumers should not be allowed access to sensitive information at all, as the URI-parameters are logged during all points and are easily "sniffed".

## Data formats

Which data formats the API consumers prefer and can easily process?

### Technical background

*   For example mobile applications usually prefer JSON and very light-weight requests and responses.
*   Older or for example Java-based server applications might still prefer XML because the systems may have in-built handling for it. XML according to specific schema is also still the preferred choice of many financial systems, due to e-invoice and business transactions standards.
*   Some marketing applications might be able to handle JSON or XML, but typically their capabilities are quite limited in terms of passing queries, headers or using anything else than GET HTTP-method. These systems, for example web advertisement banner -systems may even prefer an already filtered static file in JSON, XML or CSV without any authentication and automatically refreshed periodically. 
*   Whether the API provider should serve the data in specific format or the API consumer should do the transformation depends on technical capabilities as well as business reasons, for example how badly we want the API consumers to use our API.

## Making requests

Does the API consumer have some technical limiatations when calling the API?

### Technical background

*   Some consumers may have specific requirements for HTTP-verbs they can use, for example some can't use PUT or DELETE, some can't even use POST.
*   If there are many long parameters needed for GET i.e. searching or filtering data this might become a problem, too because of limitations on how big URLs are supported.
*   Most API consumers don't support GET-requests with request bodies as that is not specified in the RFC 2616 standard. Because of URL-length limitations also endpoints and nesting them need to be kept short.
*   Headers may not be supported at all, or there is only support for some (usually standard) headers, see list [https://en.wikipedia.org/wiki/List_of_HTTP_header_fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields). This affects authentication possibilities but also passing currency or other non-standard headers.

## Handling responses

What kind of responses the API Consumer is able to handle from the API?

Technical background:

*   API Consumers may require some specific HTTP response codes for specific situations.
*   Sometimes API Consumers need to receive 200 OK even for created objects instead of 201, because they can only handle one success code. Also 4XX-codes may cause issues, instead of using 400 Bad request.
*   Depending on the API consumers architecture, 3XX codes can be totally unknown and for example even queued responses need a plain 200 response. It's still better to require standard response codes and error codes in general.
*   These API consumer specific requirements must be documented and resolved somehow, too, depending on the importance of a specific API consumer. There can be workarounds: gateway script in the API gateway to provide special codes for specific API consumers or API can provide special codes if  request has some special header or query parameter.

## Localization and data standards

Are there any specific requirements about language, currencies, codes, API specific error codes, error messages and time stamps?

### Technical background

*   Localization and globalization data should be implemented according to ISO and other standards (see <ac:link><ri:page ri:content-title="API design style guide"><ac:plain-text-link-body></ac:plain-text-link-body></ri:page></ac:link>) but API consumer specific handling should be considered on top of standard implementation if it's a priority.
*   Industry specific standards and API consumers ability to follow them should be checked, too.

## Securing the data during transit and storage: Encryption

Check if API consumers will be able to handle TLS (i.e. HTTPS)? If API handles sensitive encrypted data, verify if API consumers can handle the algorithms? 

### Technical background

*   Using encryption in the query parameters, headers or body is good practice when sensitive information is concerned. This may be a problem to some API consumers, at least it requires understanding of limitations.
*   Most API Consumers can handle HMAC SHA 256 with or without base64 encoding and possibly even RSA (public-private key), but this should be checked.
*   As a minimum, to protect both credentials and the content, all API connections should be done with TLS (i.e HTTPS instead of HTTP) using official or at least mutually authenticated certificates. If this is a problem to an API consumer, they should be served only limited static read-only resources via a content delivery network (CDN) so they don't cause any security or capacity issues. This is a typical approach for example for serving pictures or other public digital assets in API-compatible way.

## List scenarios

Scenarios in the context of Behaviour Driven Development mean a simple but complete workflow and it's different variations (scenarios). In the context of APIs, we are interested in the scenarios which should be handled with single request and response or single "push event".

For example placing an order in a webstore could be broken down to scenarios:

*Scenario 1: normal order, process until payment*
```cucumber
                Given customer has entered his contact details, products, quanitities
                And customer has selected payment method
                And customer has chosen order confirmation method
                When customer submits order
                Then order is saved to ERP as preliminary order
                And customer is directed to payment provider
```
*Scenario 2: normal order, payment has been processed*
```cucumber
                Given customer has submitted order
                And customer has paid order in payment providers service
                And customer has returned correctly to web store
                Then order is saved to ERP as paid, waiting for delivery
                And customer receives order confirmation with selected method
```
