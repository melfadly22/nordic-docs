# Health Data Connector -> Configuration
  - [Workflows](#workflows)
  - [Connections and Auth](#connections-and-auth)
  - [Payload Processing](#payload-processing)
  - [Chaining APIs](#chaining-apis)
  - [Event Driven](#event-driven)

## Workflows
Chain processes together in order to generate a complete output and deliver the output to various storage and operational services. Workflows typically consist of multiple web service requests that build a custom data payload (or business object), which is then transmitted to an operational service that requires the data. Operational services are typically the existing software our clients seek to integrate healthcare data into. Workflows can also store data to a database along the way or as a final outcome

  - A workflow is typically event-driven, meaning it is triggered via one of the following concepts

    - On a scheduled basis
    - Via receipt of an API call or Service Bus message to the integration service requesting workflow execution
    - Upon receipt of inbound data such as an HL7 message or a SMART launch execution

  - A workflow typically has a “return payload”, which defines the data to be transmitted downstream. This payload contains the details required for downstream business processes.

  - Workflows can also result in outbound data transmission to a 3rd party allowing, for example, data writes to a 3rd party, or outbound HL7 messaging.

## Connections and Auth

The Connector is capable of connecting to an EHR instance via a registered application with that EHR. Configurable fields allow you to input the required data from the registered application, such as a client ID, and utilize that for the authentication and API calls.

  - The Connector supports any EHR that provides data via web services such as FHIR, custom web services, and MLLP communications such as HL7 v2.

## Payload Processing

Data retrieved from a request or event is parsed into a standard model and extractable via a Payload configuration.

  - For example a Date of Birth could be extracted from a FHIR Patient resource and provided back to the Workflow. This Date of Birth field could then be used downstream for another API request or provided back to the business service as part of a custom business object.

## Chaining APIs

Data retrieved from an API request is parsed into a machine-readable object and provided back to the Workflow, which makes available all data to downstream processes and orchestrates those processes.

## Event Driven

The application will operate without user intervention based on received events. For example:

  - If a SMART on FHIR launch occurs the application can retrieve additional FHIR APIs, parse the data, log the user in to a client-owned Identity Management service, and finalize the user’s redirect location (the website they will see) based on the parsed data and/or login process. This allows a dynamic SMART launch that works seamlessly for multiple user types.

  - If an HL7 v2 message is received the system can parse the data for patient information and make additional API calls to supplement a “complete” data payload (as defined by the client). This payload is then delivered to a downstream service or database for later use.

