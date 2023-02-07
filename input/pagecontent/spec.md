### Overview
This specification page details the technical requirements and behavior of this implementation for an integration between a RTLS and another system. 

### Tracking Tag Location Update
This event type is used to send notifications from the RTLS, informing other systems of an updated location associated with one of the tracking tags. The specific requirements for what constitutes an "updated location" is out of the scope of this IG, and is left to the implementing RTLS to define.

#### Subscription Notification Model
Location updates shall conform to subscription notification model, in which the RTLS server defines a "Location Update" event type using the rtlsSubscriptionTopic resource that a client (e.g. a EHR system) can subscribe to. Clients or non-RTLS systems subscribe to the pre-defined Location Update topic using the rtlsSubscription resource which establishes proactive event notifications from the RTLS server to the subscriber. Once a subscription is created, any RTLS event that matches the specified location update rtlsSubscriptionTopic and corresponds to a tracking tag that the subscriber system has indicated interest in (see activation/deactivation), shall result in a notification to be sent to the subscriber via FHIR messaging.

#### Related Resource Profiles
1. rtlsSubscriptionTopic
2. rtlsSubscription
3. rtlsMessageBundle
4. rtlsSubscriptionStatus
5. rtlsDevice
6. rtlsLocation

### Tracking Tag Activation
This event type is used to indicate to the RTLS that a subscribed non-RTLS system wants to receive updates for a specific tracking tag's location. It is assumed that an active rtlsSubscription resource corresponding to the rtlsSubscriptionTopic that the non-RTLS system is interested in already exists and was communicated.

#### FHIR Messaging Model
Tag activation messages shall utilize the FHIR messaging model.

#### Related Resource Profiles
1. rtlsMessageBundle
2. rtlsMessageHeader
3. rtlsDevice

### Tracking Tag Deactivation
This event type is used to indicate to the RTLS that a subscribed non-RTLS system no longer wants to receive updates for a specific tracking tag's location. It is assumed that an active rtlsSubscription resource corresponding to the rtlsSubscriptionTopic that the non-RTLS system is interested in already exists and was communicated.

#### FHIR Messaging Model
Tag deactivation messages shall utilize the FHIR messaging model.

#### Related Resource Profiles
1. rtlsMessageBundle
2. rtlsMessageHeader
3. rtlsDevice

And an icon: ![resource](icon-resource.png)