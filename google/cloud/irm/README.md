# Stackdriver Incident Response & Management API

## Metadata

*   API tracking bug: http://b/118138921
*   API service name: irm.googleapis.com
*   API package name: incident_response_management.service.v1alpha1
*   API type: public
*   Project codename: n/a
*   Team site: go/irm
*   Team alias: irm-team@google.com
*   PM: andrekelly@
*   TL: trevorh@

## Overview

The Stackdriver Incident Response & Management API allows users of Stackdriver
to retrieve their alerts, group them into incidents, retrieve and modify
existing incidents, and manage user roles. It also provides access to
functionality related to the IMAG process such as escalating an incident and
performing handoffs at the end of an oncall shift.

## Engineering

### Design

#### Sample use cases

TODO: Describe a few basic scenarios that developers will be able to accomplish
using this API.

<!-- These scenarios should be very easy for developers to accomplish. Even if the API offers numerous advanced features, the simple things should be simple. -->
<!-- Replace this example with your own text. Add as many examples as you wish. -->

Example:

User creates a recipe which combines the following low level calls:

1.  Create a cloud network;
2.  Create a cloud SQL database and attach it to the network;
3.  Create a virtual machine and connect it to the same network.

#### Code examples

TODO: Write examples of client code for the basic scenarios described above.

<!-- Make sure the code samples are up-to-date. Feel free to implement the examples in multiple different programming languages, preferably the languages you expect the majority of your customers to use. -->

TIP: Use [code blocks](http://go/g3doc-markdown#code-blocks) or fetch [live
snippets](http://go/g3doc-live-snippets) directly from Piper.

#### Conceptual models

TODO: Define all concepts used in the API.

<!-- Refer back to the overview section to
ensure that the key concepts mentioned there are also clearly defined. -->

### Usage

**What platforms and clients will this API be called from?**

Platform     | Yes/No | Notes/qualifications
------------ | ------ | --------------------
Browser      | ?      | -
Desktop      | ?      | -
GAE/GCE/GKE  | ?      | -
Mobile       | ?      | -
Server       | ?      | -
[add other]  | ?      | -

**What SLA do you offer to your customers? What is the impact of any outage? How
sensitive are you to latency?**

<!-- Answer here -->

**Do you have usage restrictions for your API (e.g., attribution requirements,
forbidden uses, quota limits, etc.)?**

<!-- Answer here -->

**What teams are responsible for maintaining this API going forward? Who is
carrying a pager?**

<!-- Answer here -->

## Product

<!-- Only required for non-private (public | partner | restricted) APIs -->

TIP: Have your product manager fill out this section

### Terms of service

**Do you plan on using the [API uToS](https://developers.google.com/terms/) for
this API? Another existing ToS ([Cloud](https://cloud.google.com/terms/),
[Geo](https://developers.google.com/maps/terms),
[YouTube](https://developers.google.com/youtube/terms),
[Ads](https://developers.google.com/adwords/api/docs/terms))? If not...why
not?**

<!-- Answer here -->

### Abuse risks

**In what ways might this API be abused? What is the cost of this abuse? Does
this product expose strategic data or IP to parties outside of Google?**

<!-- Answer here -->

### Privacy and security

**Whose data is served by this API (e.g. end users, developers, Google,
partners)?**

<!-- Answer here -->

### Obligations / deprecation

**What contractual obligations does this API carry (refer [deprecation
policy](https://docs.google.com/a/google.com/document/d/1liSUZC9w1xUXsUVnXzwbwTVjFbIVBvN5kxUW0Sbf7Nk/edit?usp=sharing))?**

<!-- Answer here -->
