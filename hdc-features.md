# Health Data Connector -> Features
  - [HL7 v2](#hl7-v2)
  - [Modular Add-ons](#modular-add-ons)
  - [HL7 v2](#hl7-v2)
  - [RESTful API Workflows](#restful-api-workflows)
  - [SMART on FHIR](#smart-on-fhir)

## HL7 v2

Receive and process HL7 v2 messages sent via HTTPS from your healthcare partners. A configuration-based approach allows you to define what data to consume from the message and Workflows allow you to perform additional actions based on the contents, such as to complete FHIR API requests and to store and transmit the parsed payload

- Capable of support for all message types
- Configurable message parsing based on message sender
- ACK responses with appropriate success and error indicators
- mTLS capable

## Modular Add-ons

The Healthcare Connector is built to support modular concepts overlaying the above data interoperability features. For example, a monitoring dashboard could be deployed to provide detailed analysis of the application’s utilization and traffic, or a Bulk FHIR module could be deployed to allow retrieval and parsing of bulk FHIR data.

## RESTful API Workflows
### (including FHIR)

Perform authorization with an authorization server and subsequent complex queries based on supported events. API requests can share data from result to subsequent request, allowing complex logical request progressions.

- Supports all FHIR resource types as well as custom RESTful APIs. Custom APIs require some additional configuration in order to parse the API response.
- Perform a patient lookup query then additional FHIR API requests if a patient is found
- Share data between requests to obtain better data. For example you could retrieve an identifier or the start and end date from an Encounter for use in a request for charges during the encounter
- Basic and oAuth Authentication available

## SMART on FHIR 

### Integration

You can automate [SMART on FHIR launches](http://www.hl7.org/fhir/smart-app-launch/) through standard management of the authentication handshake with robust error handling and logging. Once the SMART launch completes the software is able to perform additional actions such as:

- Integrating directly with Okta/Auth0, Active Directory, custom databases, or other services to authenticate and log in the user who initiated the SMART launch
- Retrieve specific FHIR resources automatically and parse them into a consistent format
- Redirect the user, (as part of the SMART launch redirect series), to a specific webpage using results from  API queries executed during the launch. For example you could show a unique web page based on the coverage status or medical history of a client
- Provide received data to the “final” redirect location as query parameters on the URL. This feature allows our clients to pre-populate a form using data retrieved during a workflow.
