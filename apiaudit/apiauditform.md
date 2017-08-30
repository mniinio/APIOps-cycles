---
layout: fullpage
title: API Audit form
permalink: /apiaudit/apiauditform/
parenturl: /apiaudit/
---

Any "No" answers must have an explanation in the comment field. Those implementations should be fixed as soon as possible or as a minimum should be peer-reviewed carefully to validate the reason. OWASP -security criteria refers to the [OWASP security cheat sheet](https://www.owasp.org/index.php/REST_Security_Cheat_Sheet).


<table>
<tbody>
<tr>
<th>Topic</th>
<th>Description</th>
<th colspan="1">OWASP Criteria?</th>
<th>Result (yes/no)</th>
<th colspan="1">Comment</th></tr>
<tr>
<td colspan="1">API management</td>
<td colspan="1">Has&nbsp;a version of the&nbsp;API&nbsp;already&nbsp;been published via API management?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Is it visible in a Developer Portal?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Have any users already subscribed to the API?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Are there rate limits enforced to the API consumers when using the API?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Is it possible for the API consumers to use the API without going via the API gateway governed by the API management?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">API specification</td>
<td colspan="1">Is there a standard specification file available about the API?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Is specification supported by the API management platform? (Open API is supported by most, RAML and apis.json&nbsp;are supported by some)</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Is the specification maintained automatically when changes are done to the API implementation?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Is the specification validated against the specification standard?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Does the specification contain schemas for the requests and responses?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Does the specification contain examples in standard format&nbsp;for the requests and responses? (API management platforms and other tools&nbsp;can process the examples automatically and show them in documentation or used them for request mocking to help developer learn the API)</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Are the schemas and examples validated against schema (for example JSON schema)?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>Protocol</td>
<td>HTTPS (in special cases HTTP might be acceptable, write explanation in comment)? (If no, then this audit doesn't fit)</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>URIs</td>
<td>Is the domain name sensible for this API: is the API published under the organizations official domain?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Is the&nbsp;visible domain which the API consumers see when using the API&nbsp;shared with other&nbsp;APIs?&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Endpoints are&nbsp;named after resources, in plural? Example&nbsp;/projects</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>Endpoints are&nbsp;max 2-resources deep? Example&nbsp;/projects/123/tasks/345</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Other naming styles in style guide have been applied?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">API has versioning?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">
<p>Versioning strategy is&nbsp;best for the selected API management platform and for the primary API consumers? Major version is in URI (only if API management platform doesn't support versioning based on client subscription)</p></td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>Processing</td>
<td>Stateless processing?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>Any types of processing requiring special checking or handling: asynchronous, events, subscribe-model?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>HTTP-verbs</td>
<td>GET is used only for searching and viewing resources</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">GET -requests don't have request bodies</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">GET requests with longest endpoint-hierarchy and&nbsp;multiple query parameters with long values don't exceed&nbsp;2000 of URI length? (Some older clients and browsers may have this type of limit, although it is not official limit and newer clients can handle it well)</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>POST is used for creating and updating data?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">
<p>POST is used only in standard ways.</p>
<p><span>(Non-standard ways would mean it is used for submitting long search parameters, as alternative to PUT or as alternative to GET.These should&nbsp;be suppported&nbsp;only if important API consumers have specific problems dealing with the standard verbs.)</span></p></td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>PUT is used to create or replace entire resource?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>DELETE is used only to remove a resource?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Whitelisting: POST, PUT and DELETE are only available for resources which API consumer is allowed to manipulate?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>HTTP -status codes</td>
<td>
<p>404 wrong url</p></td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">400 bad request from the client, for example a required query parameter was missing</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">400 -responses have additional information of the specific error (for example missing required attribute)</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">401 -response is used when API consumer is using wrong credentials</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">403 using endpoint which is valid but not accessible by the requesting API consumer or trying to use operation they are not allowed to do</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">500 -response when there is an internal processing problem which API consumer can not fix by changing the request</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">500 -responses have&nbsp;application specific&nbsp;error code but not a very clear plain message about exact error (stacktrace or error text) which could expose internal implementation to API consumer</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>
<p>GET: 200 OK and items -array as empty array</p></td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>GET: 204&nbsp;empty response, nothing in the body, but request is successful.</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>
<p>POST: 200 OK for updates or submits without creating new resources</p></td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>
<p>POST, PUT: 201&nbsp;Created for creating new reasource</p></td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">201 -response is combined with the identifier of the created resource</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>DELETE: 204 OK when removing resource was successful</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>Localization</td>
<td>Date- and time formats in UTC with timezone (ISO standard)?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>Language and country codes used with ISO -standard codes?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>Other standard codes applied?</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td>&nbsp;</td>
<td>Geocordinates in ISO standard if used? &nbsp;</td>
<td colspan="1">&nbsp;</td>
<td>&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Payload localization supported or localized values accessible with API?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Error message localization supported?</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">Additional security</td>
<td colspan="1">All endpoints are protected by at least a client specifc API key even if they are publically available (anti-farming)?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">OpenID connect and JWT supported (session based authentication)?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Protect against <a href="https://en.wikipedia.org/wiki/Cross-site_request_forgery">CFRS</a>? (allow API management developer portal as origin to allow developers to try out the API via the portal user interface)? See <a href="https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet">https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet</a> for details.</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Secured direct object references, i.e. no sensitive information like bank account numbers, social security numbers, person names etc. in URL as resource names or query parameters?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Inputs are&nbsp;validated?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Inputs are validated automatically by the coding framework used?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Outputs are&nbsp;escaped?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Outputs are escaped automatically by the coding framework used?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Need for encrypting data has been evalueted before implementation? (country-specific&nbsp;privacy and other legal requirements&nbsp;and business confidential requirements)</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Encryption of data in transit and data in storage has been implemented according to the evaluated need?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Need to detect message integrity has been evaluated before implementation (typically using signed and encrypted JWT -tokens as authentication and integrity ensurance)?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr>
<tr>
<td colspan="1">&nbsp;</td>
<td colspan="1">Message integrity has been implemented according to the evaluated need?</td>
<td colspan="1">yes</td>
<td colspan="1">&nbsp;</td>
<td colspan="1">&nbsp;</td></tr></tbody></table>
