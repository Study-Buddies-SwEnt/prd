# Non-Functional Requirements

## Security, privacy, and data retention policies
We document the non-functional requirements that the MVP must satisfy to
make it viable.

Our application will collect some personal data such as :
    - First and Last name (if the user don't use a username)
    - email adresse (necessary for the sign in)
    - pictures 
    - conversations (direct messages and group conversation)
    - locations
    - affiliated university (depending on the group name)
    - friends networks (we could link the user to his friends/contact)
Other personal information could also be entered in the application via the messages, or other features (to do list, calendar,...). 

We must therefore establish clear security, privacy and data retention policies concerning those.

## Security and Trust

For **security** purpose, we should assure that none of the stored data is at risk of leakage, as per the Swiss Federal Act on Data Protection (FADP) which stipulates the protection of ["the personality and fundamental rights of natural persons whose personal data is processed"] (https://www.fedlex.admin.ch/eli/cc/2022/491/en). Art.8 of this law states that *"The controller and the processor shall guarantee a level of data security appropriate to the risk by taking suitable technical and organizational measures"*. 

To ensure any potential leakage would not pose too much risk, we should encrypt sensitive data like pictures, conversations, names, and more such that no one, not even the developers, can have access to those data.
Concerning the app developers, we should also ensure that no API keys or similar sensible data are visible in the code online (for example on Github).

Accounts are linked using Google services. Since the user will access these through the application's interface, we must ensure we do not store any credentials on the backend (such as passwords or refresh tokens).

We will also implement proper sanitization of user inputs to avoid injection attacks for example.

## Privacy Considerations

Most data on the app is stored on the database, we must therefore ensure proper access rights management through the implementation of permissions within the database for example. 

We might implement some form of Mandatory Access Control within our organization, to ensure developers don't have access to unnecessary data. The Chinese Wall concept, part of the BIBA model, applied to the different user data category we deal with (like pictures on one end and conversations on the other), should ensure developers don't interfere with any particular user privacy more than necessary for correct accomplishment of their task, and that the data is only ever treated anonymously. 

We should ensure no data from camera, microphone, location or other live-usage channels get stored in the backend as it would serve no purpose and pose a risk to the user's privacy.

## Data retention

Our app could be quite demanding in terms of resources. Thus, we should only store relevant data. The data related to offline features (calendar, todo list,..) are designed to be stored locally on the phone. Other online features should be stored on the database. For now it seems that we have to store all online data as they could always be used by the user at some point.

We want to ensure that the user rights are respected and secured. Meaning that sensible information shouldn't be available by anyone else other than the user themselves. Also we should ensure that  users can only access their own information and information of groups they belong to.

Concerning the app deciding power, we could think of a kind of democratic policy to vote for important decisions. This could be done by creating a decisive circle composed of people representing different aspects of the app, such as the developers, the marketers, the investors and the users. Another option could also be to send surveys to the users to make them express their opinion when decisions are made.

## Privacy Features

We need to implement privacy features for the following captors of our app :  
- contact list
- camera
- microphone   
- location
Protocols must be put in place in order to ensure privacy and protection of the users when those features are in use. 

## Adoptions, Scalability and Availability

**Adoption** The app must have different customization options to allow the user to adjust his experience on the app. For example, the user should have the possibility to disable notifications and pop ups to remove digital distraction.

**Scalability** : The app needs to be able to withstand the high traffic expected during revision and exam periods. Solutions would be put in place to accommodate peak usage periods and they must ensure service continuity to offer the best experience.

**Availability**: Mechanisms must be put in place to ensure constant delivery of services through the app even when system failures occur.. Diverse recovery plans and protocols (such as database backups, regular API checkups, etc) are needed to guarantee a fail proof experience for our users.

## Traffic 
Patterns that follow the rhythm of students' routine (for example afternoons and nights during the normal class week and day for the revision period). However, it’s hard to set up any major traffic patterns as study routines are widely different between people and regions.

We expect a bursty traffic period during revision and exam period as our app could be especially useful during these moments.
