### Overview
This specification page details the technical requirements and behavior of this implementation for an integration between an RTLS and another system. 

### Enroll Tag
This event type is used to indicate to the RTLS that a non-RTLS system wants to receive updates for a specific tag's location. 

#### FHIR Messaging Model
Enroll Tag messages shall utilize the FHIR messaging model.

#### Related Resource Profiles
1. rtlsMessageBundle
2. rtlsMessageHeader
3. rtlsDevice

### Unenroll Tag
This event type is used to indicate to the RTLS that a non-RTLS system no longer wants to receive updates for a specific tag's location. 

#### FHIR Messaging Model
Unenroll Tag messages shall utilize the FHIR messaging model.

#### Related Resource Profiles
1. rtlsMessageBundle
2. rtlsMessageHeader
3. rtlsDevice

### Tag Location Update
This event type is used to send notifications from the RTLS, informing other systems of an updated location associated with one of the tags. The specific requirements for what constitutes an "updated location" is out of the scope of this IG, and is left to the implementing RTLS to define.

#### Related Resource Profiles
1. rtlsMessageBundle
2. rtlsMessageHeader
3. rtlsDevice
4. rtlsLocation