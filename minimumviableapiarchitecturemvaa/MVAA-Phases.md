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

</tbody>
</table>
