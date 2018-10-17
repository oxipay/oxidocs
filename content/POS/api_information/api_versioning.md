---
title: "API Versioning"
menuTitle: "API Versioning"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<h3>API Versioning</h3>

We implement URL based versioning, as this tends to be the easiest scheme for clients to consume (i.e. because the API is directly part of the URL and no special headers are needed).

The API version is included into the URL as follows: <code>https://pos.{{< domain >}}/soap/<font style="background-color: yellow;">v1</font>/Service.svc?wsdl</code> (for SOAP) and <code>https://pos.{{< domain >}}/webapi/<font style="background-color: yellow;">v1</font>/operation</code> (for HTTP).<br/>

**Note**: There is no "fallback" behaviour if the version number is excluded from the URL (i.e. 404 "Not Found" response will be returned if no version is given as part of the URL). This decision was made to avoid confusion over which version of the API is being executed.

<h3>Versions</h3>

Version | Description | Publish date
-----------|-----------|-----------
v1 | Initial version | 01/08/2017
