---
layout: fullpage
title: Minimun Viable Architecture Phases
permalink: /minimumviableapiarchitecturemvaa/mvaa-phases/
parenturl: /minimumviableapiarchitecturemvaa/
---

<table>
<tbody>
<tr>
  <th>APIOps&reg; Cycle</th>
  <th>Prototyping</th>
  <th>Building Just Enough</th>
  <th>Scaling</th>
</tr>
<tr>
  <th colspan="1">API Canvas (as input to MVA)</th>
  <td markdown="1">
  1.  Who are the first API -consuming users? Do they or their platform have special requirements?
  2.  What is their key pain, what problem does this API solve?
  3.  What data or logic they absolutely must have to publish their service?
  4.  How can the API -consumers be contacted for feedback on the designs?
  </td>
  <td markdown="1">
  1.  What platform are the API consuming clients building their services to? Where is it physically located? What special requirements does it have e.g. JSON as data format, can use headers, can use all http -headers, authentication).
  2.  What are the systems providing data or logic as backend to this API? With what technology are they built? Where is it physically located? What special requirements does it have (data formats, authentication, interface specification, load restrictions).
  </td>
  <td markdown="1">
  1.  Are there multiple API Consumers starting to use the API?
  2.  Is the business model changing dramatically? For example price for using the API is going down or API is becoming otherwise much more popular?
  </td>
</tr>
<tr>
  <th colspan="1">MVA</th>
  <td markdown="1">
  1.  Concentrate on information architecture and interface design.
  2.  Add only the endpoints and fields you absolutely are sure that they are needed for the first consumers. If there is no clear answer if something should be added, leave it out. It's better for versioning, no one will start using it and depending on it and changes are kept to minimum later.
  3.  Design with the API Audit criterias in mind, using style guide as your guide line.
  </td>
  <td markdown="1">
  1.  Stick to familiar architecture, when risks are small designs don't have to be heavy and perfect.
  2.  For example backend for an API can still be even a static file and some APIs or backend integrations can be replaced with an email.
  3.  Meet customer need in a few hours or days, not in months.
  4.  Do NOT think about scaling.
  </td>
  <td markdown="1">
  1.  Any peak times coming in near future?
  2.  Are the non-functional requirements changing, for example allowed amount of down-time? Response times? New users from far away?
  3.  Growing concurrency brings new bottlenecks to the architecture, load test first and monitor existing production, design improvements after that.
  4.  Growing amount of APIs need more teams and team members.
  5.  API management needs to have more fine-grained user roles and separation.
  6.  APIs and microservices need more decoupled modules which can be scaled and developed independently.
  7.  API design and information architecture needs to be designed from scalability point of view, for example different customer segments or customers from different countries or privacy legislation areas to different APIs.
  8.  Think about separation not centralization all through, even in databases and Identity management, authorization and access management.
  9.  Start with load balancer and 1 run-time node, this way more nodes can be added easily.
  10.  Consider when and how to do caching, failsafes etc. but don't implement them before they are actually needed, just know you can.
  </td>
</tr>
<tr>
  <th colspan="1">Build</th>
  <td markdown="1">
  1.  **No coding required.**
  2.  OpenAPI specification only, with data schemas, a few example requests and responses.
  3.  if API management exists already then design and publish OpenAPI specification using that. **Tip: create example JSON requests and responses first, you can generate a schema from the examples automatically. Examples are much more clear to many stakeholders than a very correctly created schema.**
  4.  If needed then OpenAPI specification using mocking service, no actual code required, but result is runnable.
  </td>
  <td markdown="1">
  1.  Build modifyible and replacable modules, they are protected with API managment and API interfaces so you should be able to replace them easily.
  2.  Because the OpenAPI specification and examples exists, every team member or even other teams can do their own piece of the whole (UI, database design, coding) with the shared specification without extra waiting time.
  3.  Set up Continuous Delivery (many times a day).
  4.  Do load testing, but keep in mind this doesn't have to handle peaks or "theoretical future load".
  </td>
  <td markdown="1">
  1.  Make sure you have covered all critical areas with proper tests before optimizing any code or changing configurations for scaling.
  2.  Build modifyible and replacable modules, protected with API managment and API interfaces.
  3.  Because the OpenAPI specification and examples exists, every team member or even other teams can do their own piece of the whole (UI, database design, coding) with the shared specification without extra waiting time.
  4.  Set up Continuous Delivery (many times a day).
  5.  Automate load testing.
  6.  Check auto-scaling possibilities for all components but check also costs
  </td>
</tr>
<tr>
  <th colspan="1">API Audit</th>
  <td markdown="1">
  Validate the prototype with [API Audit](../apiaudit).
  </td>
  <td markdown="1">
  Validate the prototype with [API Audit](../apiaudit).
  </td>
  <td markdown="1">
  Validate the prototype with [API Audit](../apiaudit).
  </td>
</tr>
<tr>
  <th colspan="1">API Lifecycle</th>
  <td markdown="1">
  1.  OpenAPI specification including schemas can be published in API management and seen and tried out by future API -consumers easily.
  2.  Publishing in API management manually is quick in this stage and ensures from first days that the specification is suitable for API management tool.
  </td>
  <td markdown="1">
  Setup API management publishing in the Continuous integration tool chain.
  </td>
  <td markdown="1">
  Setup proper deployment orchestration since scaling usually causes multiple parallel environments. Make it possible to run test environment with parallel loads, rewrite tests if needed so they don't clash.
  </td>
</tr>
<tr>
  <th colspan="1">Developer Experience</th>
  <td markdown="1">
  1.  Ask feedback from UI-developers, partners, customers, backend system administrators, API developers, business people.
  2.  At this stage fixing is really fast and easy.
  </td>
  <td markdown="1">  
  1.  Ask feedback from UI-developers, partners, customers, backend system administrators, API developers, business people.
  2.  Try to make API- interface as stable as possible according to the OpenAPI specification.
  3.  Actual service implementation can be less pretty and less modular and not built for scaling, but you should be able to replace bigger pieces with smaller pieces or other implementation later at leats by re-writing the code.
  </td>
  <td markdown="1">
  Response times should be lower after scaling or at least as good as before.
  </td>
</tr>
<tr>
  <th colspan="1">Measure</th>
  <td markdown="1">
  1.  Measuring is mostly qualitative at this stage (happy / not happy stakeholders).
  2.  Processing time in UIs/clients using the API can be measured, it can have major effect in the design.
  3.  Work estimates and costs for implementing the API can be made more accurately.
  </td>
  <td markdown="1">
  1.  Get an API management tool with basic configurations and other analytics in place. Goal is to make sure you have detailed analytics on how the APIs are being used, what errors happen, and who is really using it. It's important to be able to learn, improve and diagnose errors quickly.
  2.  Setup dashboards and analytics and share data (even if just with links to dashboards) with your API -consumers and your backend system admins so that it's easy to see where the problems are, if any.
  </td>
  <td markdown="1">
  1.  Keep an eye on response times, amount of errors (also client side 4xx) due to any problems with scaling.
  2.  Add Search Engine Optimization (SEO) capabilities to developer portal to see who visits and how many start using the APIs.
  3.  Track API usage per API consumer segment according to your metrics: requests, revenue, feedback, incidents...
  </td>
</tr>
<tr>
  <th colspan="1">Learn</th>
  <td markdown="1">
  1.  Prototype API can be used as backend for client development, with no coding done yet for the API itself, ask feedback actively and participate in UI/client design sessions if possible.
  2.  Stay in the prototype phase until you are sure all those few attributes and endpoints have as standard names and values as possible, but only those few fields and endpoints which were crucial.
  3.  **Fix the design according to feedback until about 80% of people around you are happy about it, then move on to "Just Enough" -phase.**
  </td>
  <td markdown="1">
  Talk to the different stakeholders, participate in UI / client / backend service meetings and look at analytics to see what new features are needed, what improvements should be made. Take them to the API Canvas and start new round (continue to Prototyping -phase, Just Enough phase or Scaling -phase depending on the learnings).
  For example
  *   If developers have lots of questions about what attributes should be used, or there are errors (typically 500 errors) because some attributes should always be used together or some values are not accepted by the backend, but it's not possible to know from the documenation. <span>Go back to prototype phase and consider adding JSON schemas, documentation and/or simplifying endpoints. If the API specification and JSON schemas are covering the problem cases, the API gateway should be able to give back 400 Bad request before the request goes to backend.</span>
  *   <span>If there are lots of 400 errors, look at them closely. It's typically either a recurring problem with API consumers code due to bug or misunderstanding the API documentation. It might be also an indication of possibility to improve the API design to cover those cases that now fail.</span>
  *   Lots of 401 errors tell you that someone is either hacking their way to the API, but more commonly they don't understand the instructions for authentication or there is something wrong with the gateway. Note that if OpenId Connect is being used, there will always be 401 errors when the token expires.
  *   Are the APIs meeting the need? What do real API consumers have to say? Are they some potential API consumers who are not yet using the API? Why not?
  </td>
  <td markdown="1">
  Adjust your metrics to see new registrations by developers and how the amount of requests grows per API consumer segment.
  </td>
</tr>
</tbody>
</table>
