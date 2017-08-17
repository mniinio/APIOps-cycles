---
title: API Audit
---

This check list is intended to be used as design guideline together with the [API design style guide](APIDesignStyleGuide) but also after implementation. It ensures the API meets best practice criteria for usability and security and can be published via API management to the API consumers.

Any "No" answers must have an explanation in the comment field. Those implementations should be fixed as soon as possible or as a minimum should be peer-reviewed carefully to validate the reason.

OWASP -security criteria refers to the [OWASP security cheat sheet](https://www.owasp.org/index.php/REST_Security_Cheat_Sheet).

<table>

<tbody>

<tr>

<th>Topic</th>

<th>Description</th>

<th colspan="1">OWASP Criteria?</th>

<th>Result (yes/no)</th>

<th colspan="1">Comment</th>

</tr>

<tr>

<td markdown="1">API management</td>

<td markdown="1">Has a version of the API already been published via API management?</td>

</tr>

<tr>

<td markdown="1">Is it visible in a Developer Portal?</td>

</tr>

<tr>

<td markdown="1">Have any users already subscribed to the API?</td>

</tr>

<tr>

<td markdown="1">Are there rate limits enforced to the API consumers when using the API?</td>

<td markdown="1">yes</td>

</tr>

<tr>

<td markdown="1">Is it possible for the API consumers to use the API without going via the API gateway governed by the API management?</td>

</tr>

<tr>

<td markdown="1">API specification</td>

<td markdown="1">Is there a standard specification file available about the API?</td>

</tr>

<tr>

<td markdown="1">Is specification supported by the API management platform? (Open API is supported by most, RAML and apis.json are supported by some)</td>

</tr>

<tr>

<td markdown="1">Is the specification maintained automatically when changes are done to the API implementation?</td>

</tr>

<tr>

<td markdown="1">Is the specification validated against the specification standard?</td>

</tr>

<tr>

<td markdown="1">Does the specification contain schemas for the requests and responses?</td>

</tr>

<tr>

<td markdown="1">Does the specification contain examples in standard format for the requests and responses? (API management platforms and other tools can process the examples automatically and show them in documentation or used them for request mocking to help developer learn the API)</td>

</tr>

<tr>

<td markdown="1">Are the schemas and examples validated against schema (for example JSON schema)?</td>

</tr>

<tr>

<td>Protocol</td>

<td markdown="1">HTTPS (in special cases HTTP might be acceptable, write explanation in comment)? (If no, then this audit doesn't fit)</td>

</tr>

<tr>

<td>URIs</td>

<td markdown="1">Is the domain name sensible for this API: is the API published under the organizations official domain?</td>

</tr>

<tr>

<td markdown="1">Is the visible domain which the API consumers see when using the API shared with other APIs? </td>

</tr>

<tr>

<td markdown="1">Endpoints are named after resources, in plural? Example /projects</td>

</tr>

<tr>

<td markdown="1">Endpoints are max 2-resources deep? Example /projects/123/tasks/345</td>

</tr>

<tr>

<td markdown="1">Other naming styles in style guide have been applied?</td>

</tr>

<tr>

<td markdown="1">API has versioning?</td>

</tr>

<tr>

<td markdown="1">

Versioning strategy is best for the selected API management platform and for the primary API consumers? Major version is in URI (only if API management platform doesn't support versioning based on client subscription)

</td>

</tr>

<tr>

<td>Processing</td>

<td markdown="1">Stateless processing?</td>

</tr>

<tr>

<td markdown="1">Any types of processing requiring special checking or handling: asynchronous, events, subscribe-model?</td>

</tr>

<tr>

<td>HTTP-verbs</td>

<td markdown="1">GET is used only for searching and viewing resources</td>

</tr>

<tr>

<td markdown="1">GET -requests don't have request bodies</td>

</tr>

<tr>

<td markdown="1">GET requests with longest endpoint-hierarchy and multiple query parameters with long values don't exceed 2000 of URI length? (Some older clients and browsers may have this type of limit, although it is not official limit and newer clients can handle it well)</td>

</tr>

<tr>

<td markdown="1">POST is used for creating and updating data?</td>

</tr>

<tr>

<td markdown="1">

POST is used only in standard ways.

(Non-standard ways would mean it is used for submitting long search parameters, as alternative to PUT or as alternative to GET.These should be suppported only if important API consumers have specific problems dealing with the standard verbs.)

</td>

</tr>

<tr>

<td markdown="1">PUT is used to create or replace entire resource?</td>

</tr>

<tr>

<td markdown="1">DELETE is used only to remove a resource?</td>

</tr>

<tr>

<td markdown="1">Whitelisting: POST, PUT and DELETE are only available for resources which API consumer is allowed to manipulate?</td>

<td markdown="1">yes</td>

</tr>

<tr>

<td markdown="1">HTTP -status codes</td>

<td markdown="1">

404 wrong url

</td>

</tr>

<tr>

<td markdown="1">400 bad request from the client, for example a required query parameter was missing</td>

</tr>

<tr>

<td markdown="1">400 -responses have additional information of the specific error (for example missing required attribute)</td>

</tr>

<tr>

<td markdown="1">401 -response is used when API consumer is using wrong credentials</td>

<td markdown="1">yes</td>

</tr>

<tr>

<td colspan="1">403 using endpoint which is valid but not accessible by the requesting API consumer or trying to use operation they are not allowed to do</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">500 -response when there is an internal processing problem which API consumer can not fix by changing the request</td>

</tr>

<tr>

<td colspan="1">500 -responses have application specific error code but not a very clear plain message about exact error (stacktrace or error text) which could expose internal implementation to API consumer</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td>

GET: 200 OK and items -array as empty array

</td>

</tr>

<tr>

<td>GET: 204 empty response, nothing in the body, but request is successful.</td>

</tr>

<tr>

<td>

POST: 200 OK for updates or submits without creating new resources

</td>

</tr>

<tr>

<td>

POST, PUT: 201 Created for creating new reasource

</td>

</tr>

<tr>

<td colspan="1">201 -response is combined with the identifier of the created resource</td>

</tr>

<tr>

<td>DELETE: 204 OK when removing resource was successful</td>

</tr>

<tr>

<td>Localization</td>

<td>Date- and time formats in UTC with timezone (ISO standard)?</td>

</tr>

<tr>

<td>Language and country codes used with ISO -standard codes?</td>

</tr>

<tr>

<td>Other standard codes applied?</td>

</tr>

<tr>

<td>Geocordinates in ISO standard if used?  </td>

</tr>

<tr>

<td colspan="1">Payload localization supported or localized values accessible with API?</td>

</tr>

<tr>

<td colspan="1">Error message localization supported?</td>

</tr>

<tr>

<td colspan="1">Additional security</td>

<td colspan="1">All endpoints are protected by at least a client specifc API key even if they are publically available (anti-farming)?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">OpenID connect and JWT supported (session based authentication)?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Protect against [CFRS](https://en.wikipedia.org/wiki/Cross-site_request_forgery)? (allow API management developer portal as origin to allow developers to try out the API via the portal user interface)? See [https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet) for details.</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Secured direct object references, i.e. no sensitive information like bank account numbers, social security numbers, person names etc. in URL as resource names or query parameters?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Inputs are validated?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Inputs are validated automatically by the coding framework used?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Outputs are escaped?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Outputs are escaped automatically by the coding framework used?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Need for encrypting data has been evalueted before implementation? (country-specific privacy and other legal requirements and business confidential requirements)</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Encryption of data in transit and data in storage has been implemented according to the evaluated need?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Need to detect message integrity has been evaluated before implementation (typically using signed and encrypted JWT -tokens as authentication and integrity ensurance)?</td>

<td colspan="1">yes</td>

</tr>

<tr>

<td colspan="1">Message integrity has been implemented according to the evaluated need?</td>

<td colspan="1">yes</td>

</tr>

</tbody>

</table>
