# Non-Functional Requirements

## Security, privacy, and data retention policies
We document the non-functional requirements that the MVP must satisfy to
make it viable.

Our applicatin will collect some personal data such as :
    - First and Last name (if the user don't use a nickname)
    - email adresse (necessary for the signIn)
    - pictures 
    - conversations (direct messages and group conversation)
    - locations
    - affilated university (depending on the group name)
    - friends networks (we could link the user to his friends/contact)
Other personal information could also be entered in the application via the messages, or other features (to do list, calendar,...). 

We must therefore establish clear security, privacy and adata retention policies concerning those.

## Security and Trust

For **security** purpose, we should assure that none of the stored data is at risk of leakage, as per the swiss Federal Act on Data Proectection (FADP) which stipulate the protection of ["the personality and fundamental rights of natural persons whose personal data is processed"] (https://www.fedlex.admin.ch/eli/cc/2022/491/en). Art.8 of this law states that *"The controller and the processor shall guarantee a level of data security appropriate to the risk by taking suitable technical and organisational measures"*. 

To ensure any potential leakage would not pose too much risk, we should encrypt sensible data like pictures, conversations, names, and more.
Concerning the app developers, we should also ensure that no API keys or similar sensible data are visible in the code online (for example in git).

Accounts are linked to Google services, since the user will access these through
the application's interface, we must ensure we do not store any
credentials on the backend (such as passwords or refresh tokens).

We will also implement proper sanitazion of user inputs.

## Privacy Considerations

Most data on the app are stored in the database, we must therefore ensure proper access rights managment through the implementation of permissions within the database for example. 

We might implement some form of Mandatory Access Control within our organization, to ensure developpers dont have access to unecessary data. The Chinese Wall concept, part of the BIBA model, applied to the different user data category we deal with (like pictures on one end and conversations on the other), should ensure developpers dont interfer with any particular user privacy more than necessary for correct accomplishment of their task, and that the data is only ever treated anonymously.

We should ensure no data from camera, microphone, or other live-usage channels get stored in the backend as it would serve no purpose and pose a risk to the user's privacy.

*What are your internal policies?*

- Ensure user can only access its own information and information of groups they belong to
- Democratic policy : groups use a voting system to approuve or disprouve on big decisions

*Which privacy features do you need from the phone?*

- Access to contact list, camera, microphone, location among others

## Adoptions, Scalability and Availability

*What kind of traffic patterns do you expect to see?*

- Stable traffic usually, maybe more at night

*Are there known periods of bursty traffic that the MVP must be designed to support?*

- Periods of revisions for exams 