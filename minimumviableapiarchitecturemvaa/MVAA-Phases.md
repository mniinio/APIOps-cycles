---
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

</tbody>
</table>
