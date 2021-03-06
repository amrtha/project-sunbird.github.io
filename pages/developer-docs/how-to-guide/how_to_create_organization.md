---
type: landing
directory: developer-docs/how-to-guide
title: Create Organization
page_title: Create Organization
description: creating a new organization in sunbird instance
keywords: create organization, new organization in sunbird, organization, create
published: true
allowSearch: true
---
## Scenario

A company, XYZ Corp, is a global conglomerate with over ten thousand employees, spread across 5 locations. Employee training and enablement is one of the core values of the organization. To ensure that employees are regularly trained and upskilled, XYZ Corp has decided to use Sunbird for its learning and training solution. To give employees access to the learning platform, the organization's administrator needs to create an organization. 

Sunbird identifies every tenant organization uniquely through a channel. When creating an organization, in addition, to organization details, Organization ID must be assigned. The organization ID has to be associated with an organization and a channel. For example, John is a manager in XYZ corporation, who can create, review and take courses. He is also an administrator in the system, in which capacity he can add users and assign permissions to them. 

### Prerequisites

1.An initialized server instance of Sunbird. Initialization includes creating an org admin user (through Keycloak), creating a channel and associating a first organization with the channel.

For details, refer to:

* [Server Installation](http://www.sunbird.org/developer-docs/installation/server_installation/)

* [Channel APIs](http://www.sunbird.org/apis/framework/#tag/Channel-APIs)

* [First organization](http://www.sunbird.org/developer-docs/initialization) associated with channel ID

2.The API Key for access and basic authentication

3.An API client to make API calls. For example use Postman refer [Using Postman] (http://www.sunbird.org/apis/framework/#tag/usingpostman)

4.Access to the [Create Organization API](http://www.sunbird.org/apis/userapi/#tag/Orgs-APIs)

### Taskflow

The sequence of tasks the organization administrator follows to create users include:

1.Specify values for the following parameters in the request body of the API 

An organization can be created in a Sunbird instance using ORG API, it can be further associated with a user and channel, refer [Mapping User to Organization](www.sunbird.org). 
Following is an example of request body for creating a user, the sample values provided in the request body are indicative:

**Request Body**

<pre>
"request":{
      "orgName":"ORG JP_1",
      "description":"Dev Default Org",
      "imgUrl":"N/A",
      "channel":"channel -12571w1sja",
      "preferredLanguage":"English",
      "homeUrl":"N/A",
      "orgCode":"orgCode123sd",
      "isRootOrg":true,
      "provider":"1231rwsadk",
      "externalId":"exts12w7k",
          "address":{
          "city":"Bangalore",
          "state":"KA",
          "country":"INDIA",
          "zipCode":"566666"
      }
</pre> 

**Response Body**

<pre>
 "responseCode": "OK",
 "result": {
       "organisationId": "012567820191629312269",
       "response": "SUCCESS"
    }
</pre>

2.Save the created organization ID

3.An organization is created in Sunbird

### Concepts Covered

**Users**: The individual who can sign in and access the Sunbird portal to perform a set of action that is assigned by the system administrator.

**Organization**: Organizations can be an institute or a body of individuals. 

**Channel**: Unique identification number associated with the user or an organization

**Root Organization**: All users and sub-organization in an organisation are associated through the rootOrg

**System Administrator**: A user who manages end-to-end system from creating an organization, administrators for the organizations, members within the organization, and assign roles to the members


### Additional Topics

[Creating first organization](http://www.sunbird.org/developer-docs/initialization)

[Creating user](http://www.sunbird.org/developer-docs/how-to-guide/how_to_create_user)

[Map users to different business units within the organisation](http://www.sunbird.org/developer-docs/how-to-guide/hohow_to_create_org_add_user)