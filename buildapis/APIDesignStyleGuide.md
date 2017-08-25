---
title: API Design Style Guide
permalink: /buildapis/apidesignstyleguide/
parenturl: /apidesignstyleguide/
---

## Format of API specification

Use the most recent [OpenAPI](https://www.openapis.org/) version supported by the API management platform for describing your API. [OpenAPI Specification (wikipedia)](https://en.wikipedia.org/wiki/OpenAPI_Specification) originally known as the Swagger Specification, is a specification for machine-readable interface files for describing, producing, consuming, and visualizing RESTful Web services.

Information about supported versions

*   [IBM API Connect](https://www.ibm.com/support/knowledgecenter/SSFS6T/com.ibm.apic.apionprem.doc/create_api_swagger.html)
*   [Azure API management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started#a-namecreate-api-aimport-an-api) - see also [restrictions and known issues](https://docs.microsoft.com/en-us/azure/api-management/api-management-api-import-restrictions)
*   [AWS API Gateway](http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-export-api.html)

Use examples-attribute with JSON schemas (validated) to provide automatically generated documentation and smart mock data to help use the API.

## Naming standards

*   All URI parts including resource names are written in small letters.
*   Use only camelCase in all attribute (field) names.
*   Do not use special characters in URI or in attribute names.
*   Use English only in OpenAPI specification.
*   Use common legally used or industry specific (not company specific) words about resources and attributes. Refer to ISO standards as primary source, then use WTO, EU or other trade area specific vocabularies, [http://schema.org/](http://schema.org/) or industry specific vocabularies for naming. As last resort refer to company specific vocabularies before inventing your own.
*   Avoid using general names like "type", "status" etc. without specifying what type, what status or better yet, avoiding those words all together.
*   Use ISO standard or other generally used (see above) values for attribute values such as languages, country names etc. Avoid using magic numbers as values or provide also the human language alternative, preferrably according to the Accept-Language header in the request.

## Localization support

Accept-Language header should be used to support localized strings and possible localized logic. All time stamps should be in ISO format which contains timezone information. All dates and clock times with no specific timezone information associated should be informed in UTC +0.

All money values should be informed in specific currency and currency information should be contained in a custom x-companyname-currency header (in both request and response). Currency values should default to some provider or consumer based base currency if no specific currency has been requested.

## Privacy & Security

Private or confidendial data should not be passed in URI, Query or header parameters as they are logged and cached. Security constraints are defined in API Product level, but privacy and security should be thought of when spliting requirements to APIS and endpoints, as security schemes are easier to implement on API level than endpoint level or by reflecting authorization in the allowed operations or response payloads.

## URI Components

### Version

Each API consumer needs to know which version of the API they are using and to be able to subscribe and use the version they need.

In some API management systems, the version does not need to be in the URI nor in the header because each API product has it's own version and each API consuming client application is only able to use 1 version of the API at a time. If same client would use multiple versions of the same API at a time, they need to do different subscriptions. This versioning strategy works with all clients and is suited for caching and HATEOAS.

Versioning in - [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-faq#how-do-i-use-api-versioning-in-api-management)

**When version number is used it should always be in the URI**, since not all clients (for example marketing tools) can set headers and using version number as a query parameter might cause slowness as query parameters are not cached. Also most API management platforms require that the URIs are unique if multiple versions of the same API are deployed at the same time.

The URI should include `/vN` with the major version (`N`) as a prefix. Having the letter v in front of the number is important to separate the version number from a resource identifier.

#### URI Template

    /v{version}/

##### Example

    /v1/

### Namespaces

In any URI, the first noun (which may be singular or plural, depending on the situation) should be considered a “namespace”. Namespaces should reflect the customer's perspective on how the product works, not necessarily the company's hierarchy.

Namespace separates different logical APIs from each other, which is usefull if you have lots of APIs with different purposes and they may end up using same resource or operation names.

Namespaces in different API management solutions:

*   **IBM API Connect** uses organizations, catalogues and spaces to organize publishing of APIs. These are usefull when there are multiple teams in charge of different APIs. Organization and catalogue form the name space of the API and those are always added automatically **before** version number or anything defined in the OpenAPI document basepath value or path-variable of each operation. 
*   **Azure API management** requires you to define a URI template when adding a new operation or by setting it for all operations in the OpenAPI document basepath value (**required**).

#### URI Template

    /{namespace}/{version}

#### Example

    /hardware/v1/

### Resource References

Try to use only one resource level, absolutely avoid using more than two levels to keep the urls short to allow room for using variables.

#### URI Template

    /{namespace}/{version}/{resource}/{resource-id}/{sub-resource}/{sub-resource-id}

## Collection Resources

Resource endpoints should follow at least View and [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) (Create, Read, Update, Delete) operations. These should be handled by using the same URI but using different HTTP verbs (POST/GET/PUT/PATCH/DELETE, more details about each verb in ( [https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) ) ).

Use nouns in plural as resource names e.g. `/products`.

<table>

<thead>

<tr>

<th style="text-align: left;">Verb</th>

<th style="text-align: left;">Usage</th>

<th style="text-align: left;">Notes</th>

</tr>

</thead>

<tr>

<td>GET</td>

<td>Read</td>

<td markdown="1"> 
Standard use does not include a request body for GET -requests. Most standard based tools and coding libraries do not support having a body. Some older systems can't make GET -requests at all (only POST). Search queries with lots of search filters may end up having too long URLs (what is too long depends on the application limits, such as browsers).
</td>

</tr>

<tr>

<td>POST</td>

<td>Create</td>

<td markdown="1">
Supported by most (but not all) API consumers. Can be used as alternative for all other verbs if you need to support old or exotic clients or run out of URL length with GETs.
</td>

</tr>

<tr>

<td>PUT</td>

<td>Create</td>

<td markdown="1">
Theory says this should only be used when client gives the resource identifier, usually e.g. file with a client given unique name. Use with care, as all clients do not support PUT. Support those clients by implementing POST and not requiring identifier so new resource will be created and identifier returned to the client in the response body
</td>

</tr>

<tr>

<td>PUT</td>

<td>Update</td>

<td markdown="1">
Only for entire resource update, not partial, see above
</td>

</tr>

<tr>

<td>PATCH</td>

<td>Update</td>

<td markdown="1">
Used with [JSON Patch](https://tools.ietf.org/html/rfc6902) message format. Use with care, as all clients do not support PATCH. Support those clients by implementing POST which can handle partial inputs, otherwise uses normal POST request body
</td>

</tr>

<tr>

<td>DELETE</td>

<td>Delete</td>

<td markdown="1">
Do not implement for collections if not absolutely sure to avoid accidental removal of multiple resources. DELETE has no request body, so identifiers can only be passed in the url. Should be repeatable with positive response.
</td>

</tr>

</table>

### Collection Resource

A list of all of the given resources, including any related metadata. Array of resources should be in the `items` field to help handle other fields than the actual resources being returned in the response.

Plan for security and provide a list of only those resources which the requesting party is allowed to see.

If the resource response is really big, provide possibility to include only those fields which the client requires. Also do add only those fields in the response, which you are absolutely sure are needed. It's easier to add more later when needed than to remove which would be a breaking change.

#### Filtering

##### Paging

Pages of results should be referred to consistently by the query parameters `page` and `pageSize`, where `pageSize` refers to the amount of results per request, and `page` refers to the requested page.

Fields like `totalItems` and `totalPages` help provide context to paged results. Use same fields with all resources to be consistant.

##### Hypermedia links

Hypermedia links are high value in navigating paged resource collections, as `page`/`pageSize` query parameters can be maintained while navigating pages of results.

Links should be provided with rels of `next`, `previous`, `first`, `last` wherever appropriate.

##### Time selection

`startTime` or `{propertyName}After`, `endTime` or `{propertyName}Before` query parameters should be provided if time selection is needed. All time values in the parameters and in the data must be in the ISO format including timezone.

##### Sorting

`sortBy` and `sortOrder` can be provided to allow for collection results to be sorted. `sortBy` should be a field in the individual resources, and `sortOrder` should be `asc` or `desc`.

#### URI Template

    GET /{namespace}/{version}/{resource}

#### Example Request

    GET /hardware/v1/products

#### HTTP Status

*   200 OK and items -array as empty array
*   204 Collection is empty, nothing in the body, but request is successful.
*   404 Wrong url
*   400 Bad request from the client, for example a required query parameter was missing

### Read Single Resource

A single resource, typically derived from the parent collection of resources (often more detailed than the collection resource items).

All identifiers for sensitive data should be non-sequential, and preferably non-numeric. In scenarios where this data might be used as a subordinate to other data, immutable string identifiers should be utilized for easier readability and debugging (i.e. "nameOfValue" vs 1421321).

#### URI Template

    GET /{namespace}/{version}/{resource}/{resource-id}

#### Example Request

    GET /hardware/v1/products/6438313255314

#### HTTP Status

*   200 OK if data is found
*   404 Not found if resource with provided identifier is not found (the same error code might mean also that client entered the URI otherwise incorrectly)
*   400 Bad request if client provided identifier but it is of wrong data type, contains blacklisted characters or is length is not correct
