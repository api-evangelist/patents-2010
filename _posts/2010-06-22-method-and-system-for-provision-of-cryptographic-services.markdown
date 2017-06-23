---

title: Method and system for provision of cryptographic services
abstract: An encryption service system comprises an API for receiving requests from one or more calling applications. Each request comprises information identifying the operations to be performed on data to be processed and information identifying the origin and target of the data. The encryption service system further comprises a cryptographic server for processing the requests and determining, for each request, an encryption policy to be applied.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09530011&OS=09530011&RS=09530011
owner: Barclays Bank PLC
number: 09530011
owner_city: London
owner_country: GB
publication_date: 20100622
---
The present application is a U.S. National Stage of International Application No. PCT GB2010 051034 filed 22 Jun. 2010 which claims priority to Great Britain Patent Application No. 0910765.7 filed 22 Jun. 2009 the contents of which are hereby incorporated by reference in their entirety.

The present invention relates to a cryptographic service system and in particular to a centralised cryptographic service system.

The provision of efficient and effective cryptography relies on close integration of application program interfaces APIs cryptographic service providers CSPs and key management.

However implementations of hardware based cryptography normally required bespoke vendor APIs to support applications. Key management functionality is also normally vendor specific. Accordingly it is not unusual for a large enterprise or organization to have an encryption system that utilises several separate key management systems that do not interoperate without manual key management operations taking place.

It is worth noting that a number of standards de facto and Standards Bodies have been developed but they deal with specific instances of cryptography business sectors or products. Some of these standards are listed in Table 1 below.

With any of the APIs listed in Table 1 there is a problem of vendor implementation and vendor lock in coupled with reluctance of vendors to build solutions that support high levels of integration between other vendor s products and services. This gives rise to the following issues 

It is possible for applications to adopt certain standards e.g. cryptographic token interface standard PKCS 11 to try to de couple vendor specific Application API implementations.

However key management and cryptographic control mechanisms that are required to provide confidentiality integrity and authentication to data within applications are currently embedded in the application which makes changes and alterations difficult and costly to implement. Therefore even if the application API is decoupled in the case of PKCS 11 there is still a reliance on the vendor s implementation and key management solution.

Also wholesale adoption of general encryption APIs such as PKCS 11 do not allow for deployment of application specific cryptographic mechanisms e.g. for the banking sector PIN block translation card verification value CVV generation etc.

Another primary concern is the control over the usage of the cryptographic function. The cryptographic function should be available to entitled users only. If it is not possible to distinguish between an attacker and an entitled user then the strongest cryptographic algorithm is rendered useless. Additionally the scenario in which the cryptographic function can be used by an entitled user needs to be controlled. For example it may be possible that two users Alice and Bob are both entitled users of the cryptographic functionality but the security model may require that Alice can only encrypt data to Bob and Bob can only decrypt data from Alice. Without additional controls it would be possible for both Alice and Bob to perform both encryption and decryption on data in either direction due to the nature of symmetric algorithms.

Accordingly it is desirable to provide a flexible approach to defining the cryptographic access and control mechanisms required by applications to protect sensitive key material and data.

According to one aspect of the present invention there is provided an encryption service system. The encryption service system comprises an API for receiving requests from one or more calling applications. Each request comprises information identifying the functions e.g. encryption decryption signature verification MACing etc. to be performed on data to be processed and information identifying the origin and target of the data. The encryption service system further comprises a cryptographic server for processing the requests and determining for each request an encryption policy to be applied.

According to another aspect of the present invention there is provided a method of providing encryption service. The method comprises a step of receiving via an API requests from one or more calling applications each request comprising information identifying the functions e.g. encryption decryption signature verification MACing etc. to be performed on data to be processed and information identifying the origin and target of the data. The method further comprises processing at a cryptographic server the requests and determining at the cryptographic server for each request an encryption policy to be applied.

In order to provide a vendor agnostic cryptographic mechanism a holistic solution that covers all the aspects of the use of cryptography in a layered approach shown in is proposed. The use of a layered approach with defined interfaces allows a system to be developed that can accommodate change. Some of the layers are concrete implementations of services while others are interface specifications and architectures.

The key management component layer provides a single integrated and automated key management solution allowing the provision of key material to the cryptographic service providers. The key management component is an automated hardware agnostic standards based key management infrastructure and is capable of 

The Cryptographic Providers layer is based on a stable managed and configurable set of hardware and software components. The cryptographic providers layers is hardware vendor agnostic and provides 

The Utilities and Libraries layer provides a consistent and secure approach to the implementation of cryptographic mechanisms. The utilities and libraries layer comprises tested integration code such as JVM software packages modules that enforce comply with required standards and best practice and modules that provide required cryptographic functions e.g. Secure PIN printing Chip and PIN scripting.

The Design Patterns layer provides applications with a known and quantifiable security model covering authentication authorisation schema to include tokens smart cards etc protection of data at rest data in transit etc and key management Key Lifecycle the migration of data during key change etc. .

The Application Middleware layer interfaces via a defined API to a cryptographic service provider such that an API caller e.g. an application is able to use a range of credentials to authenticate to the cryptographic service provider and does not need to specify the key material label used to perform the required cryptographic function. The Application Middleware layer supports 

Utilising the layered structure the embodiment deploys a centralised cryptographic service system to provide users with consistent user security.

By employing a high level API that separates the calling applications and any details of the encryption mechanism such as key management and cryptographic providers the centralised cryptographic service system allows calling applications to request a cryptographic function by using a simple sentence construct with information regarding the origin the target and what needs to be done with the data. The specific encryption policy that needs to be applied can be determined by the cryptographic provider layer under the API.

By defining the key management and cryptographic controls within a policy that is then implemented and enforced by a separate entity external to the application the embodiment allows the policy to be applied on a per cryptographic call basis. This allows a fine grained flexible control system to be deployed without the need to alter application code or require the wholesale migration of encrypted data from one key or mechanism algorithm to another.

If the determined policy specifies that the data is managed then the encrypted data block or cryptogram contains the information required to decrypt the data for example the encryption key identity and cryptographic mechanism are wrapped with all the data processed in order to de couple the key management and cryptographic controls from the application. By including the key management and cryptographic mechanisms within the cipher text the embodiment allows any alteration to the key management and cryptographic mechanisms to be implemented in the next API call without requiring a change to the application. By binding the key identifier and cryptographic mechanism to the cipher text the application can recover the clear text without the application knowing the key mechanism or cryptographic mechanism used to protect the data.

If the determined policy specifies that the data is unmanaged then the cryptogram contains only the encrypted data and does not include sufficient information to decrypt the data. The receiving application will need to have prior knowledge of how the data was encrypted or the information on how to perform the decryption operation will be included in the policy for that application. As an example the policy would need to specify an explicit key and cryptographic mechanism to use as opposed to using the metadata that would be contained in a managed data construct. The use of unmanaged data allows the exchange of data with systems that do not implement a managed approach.

The use of policy based cryptography can also be extended to a Key Server KS . The KS supports distribution of asymmetric symmetric key material as defined by a key usage policy to disparate endpoints based on strong authentication of the API caller e.g. an application and enrolment of a Cryptographic Server CS . By supporting strong authentication of the application and CS key material can be distributed to third parties should the need arise.

Since calling of the low level cryptographic APIs is decoupled from the API it is possible to use a variety of hardware and software products from different vendors as well as increasing the utilisation of the existing devices. By managing the low level cryptographic services in this way a cryptographic service may be provided which can be supplied on a per use basis i.e. a crypto on demand service .

One or more users e.g. applications may call a CS via an API to request cryptographic services. The CS upon receiving the call checks the users identity e.g. ID token . If the CS is satisfied that the users identity is valid it then processes the request s by determining the appropriate encryption policy and requesting the appropriate cryptographic service provider s CSP to perform the specific cryptographic services requested. When processing the requests the CS may request appropriate keys from the Key Server KS .

The users may be connected to the CS over a network such as a local area network LAN a wide area network WAN or the Internet. The CS may be connected to the KS over a network such as a local area network LAN a wide area network WAN or the Internet.

Further implementation details of several aspects of the centralised cryptographic service mechanism will be discussed below.

An application is required to logon to each instance of a CS it wishes to communicate with for example by supplying appropriate credentials. The CS calculates and returns an ID token. The API client appends the returned ID token to an ID token chain which is required to be passed in with each Client API call. Upon receiving a call the CS checks the ID token chain for an instance of a token it generated. If a valid token is found then the command is processed otherwise the call is rejected.

An example of pre fetch is the fetch of a symmetric key to MAC data before onward transmission of the data.

The keys that are loaded as part of pre fetch are grouped and flagged by the ID Token. When the ID token is deleted the keys are removed from the local key store.

The unique ID is an indicator that is used to identify the application. This unique ID may be used by the policy engine within the CS to determine the rights afforded to the application.

The credentials are used to prove ownership of the unique ID for the application. The credentials provided may contain an indicator identifying the credential type being supplied. The credentials may be any of the following by way of non limiting example 

This is the Token Chain to which the CS appends its ID token on successful authentication of the calling application.

The call request may be wrapped using various access protocols Simple Object Access Protocol SOAP for example. The request preferably includes a data authentication mechanism and is preferably sent via a confidential link e.g. HTTPS. The command is 

The additional data items include credentials to support the application ID specified in the origin field and optionally any additional data to support a pre fetch request. The content of the call includes 

The Pre fetch is a subset of the functionality of the DO API call see section 1.2 . The pre fetch drives the key resolution but not the actual cryptographic function.

Note that if the key definition does not support caching then the key will not be cached and the application will be informed accordingly via response return codes.

On successful authentication by the CS of the credentials supplied by the calling Client API an ID token is issued to the Client API.

The ID token needs to be presented with every call made to the CS. The client is required to logon to each CS with which it wishes to communicate. Each CS returns a valid token that is appended to the client ID Token chain.

The ID token contains a reference to the ID and any policy controlling defining the application an attribute of the calling Client API machine serial number etc an expiry date time for the token a mechanism to prevent replay of the token and the issuing CS ID.

The data elements above are encrypted using a key unique to the server. This key is delivered in the Base Key Set. The ID token additionally contains a mechanism that allows the server to cryptographically validate tokens issued by it e.g. HMAC and additional fields e.g. pre fetch key list .

The CS returns to the API an output data block generated in response to the call request which is passed to the calling application.

The API should be as simple as possible for the application programmer to implement. It may be close to natural language. Ideally it should allow the cryptographic control required by the design to be expressed in the API.

The client API marshals API commands and transmits them to the central cryptographic server CS. API command confidentiality and integrity is protected using secure sockets layer SSL TLS.

DO operation FROM origin TO target WITH additional data items Some possible arguments are listed in Table 3 below together with the resultant output data. The Origin is the intended sender s of the output data while the Target is the intended recipient s of the output data.

If the API call made is via an API abstraction this abstraction is responsible for rendering the calling command down to a single string. A typical string form is 

The API abstraction may maintain state for instance to automatically include command capabilities retrieved from the logon command or to automatically fill in other inputs based on contextual or stored information.

The string input is passed to a command dispatcher which is a single command addition to the Portal API to support passing of data to the command engine. The Portal command marshalling then does the final conversion to a network transmission suitable representation and transmits the data to the server via an SSL TLS link.

In order to reduce exposure due to theft of ID tokens an expiry parameter is included within the structure of each ID Token. When the server is presented with an expired token it rejects the request.

To allow processing to continue beyond the lifetime of the token a re authentication mechanism is required. Due to the requirement for an ID token be presented with each Client API call a Client API wishing to request cryptographic service is obliged to perform a logon to obtain a new ID Token. This inevitably creates a delay in processing which would be exacerbated if multiple instances of the Client API were in operation. Therefore the Client API is required to monitor the expiry period of the ID Token and request a renewal of the token within a pre defined window e.g. 10 min of expiry. The re authentication requires the Client to present the credentials and the current ID token. If the user credentials are still valid and the ID token is within its renewal period then the client will be passed an updated token i.e. the expiry period will be reset .

In order to support a clean shutdown the application is required to issue a logoff command to all the servers that it has communicated with in order to clear any cached keys from the CS local key store.

As each server processes the received logoff request it removes its ID token from the ID token chain passed by the Client API and returns the modified ID token chain.

Based on the parameters defined in the Client API call Type Origin Target it is possible for the CS to check whether the Client API is authorised to perform the requested function. The format of the command is 

Where ambiguity exists the Data type may be used to finalize key selection. Since the API requires strong data typing the data type can be identified. For example if the data is identified as a PIN block and the function is a decryption function the function would not be authorized. However if the data is identified as encrypted data a decryption function would be authorized.

If the Client API is authorised to perform the function it is requesting it should be possible for calls that operate on clear text data to map a key request to the Client API based on the parameters defined in the client API call Function Origin Target .

For API calls that operate on cipher text the key label can be extracted and validated against the rule see Section 3 Data Structures . The format of the command is 

The Client API requests cipher text to be constructed from clear text or a verification object to be created. The key label specified in the rule is used to form the GET Key request to the KS.

For requests that de construct cipher text back to plaintext or verify a verification object the Key Unique Identifier key UID needs to be parsed to obtain the Key Label before the rule can be validated. On successful validation the key UID is used to form the GET Key request.

In order to simplify the Client API additional processing rules are defined to complete the required parameters for a cryptographic call. The format of the command is 

The CS supports authentication modules which interact via a standard API with the CS and are integrated with it. The CS does not store any user credentials itself. Preferably each user uses no more than one authentication method at a time that is for each distinct user name there is exactly one authentication module instance to which the authentication request is always routed.

The authentication modules answer requests to authenticate the identity of a user and return a yes no answer together with limited data about that user when available. A typical authentication module is a simple wrapper that implements a remote calling protocol to a fully fledged authentication system.

The authentication module API may support multi message authentication particularly challenge and response rather than just username and password. However in a simple implementation only username and password are needed.

For stateful authentication methods such as SMS messages or matrix cards it is the responsibility of the authentication system not the CS to maintain state. The authentication module cannot offload state to the CS.

User names supplied to the authentication modules by the CS contain a prefix that specifies the authentication module that is to validate the user. User names can be structured to allow selection of multiple different instances of the same authentication module. For instance there might be two Active Directories accessed using LDAP DIR1 and LDAP DIR2 as prefixes.

It is the responsibility of each authentication module to map the input user name from the CS e.g. LDAP DIR1 HomerSimpson to the precise string name that makes sense in their authentication system.

It is possible to use the authentication capability of the CS in several ways for maintaining a long term relationship between a user and the CS.

The authentication system supports three authentication methods Local Authentication Active Directory LDAP and Remote Authentication Dial In User Service RADIUS .

A local authentication module can be implemented to authenticate users by hashing their password and comparing it with a file of userIDs password hashes stored on disk. This module may be used by applications that do not take on individual user identity calling the CS for cryptographic services. Preferably the hashes are heavily salted to protect against dictionary attacks. The hash algorithm may be selected so that there is no existing rainbow table easily available. Ideally the user pass storage file is mildly obfuscated on disk.

An LDAP authentication module can be implemented to allow standard password authentication of users to be made for example via Active Directory. This module can log on to an active directory using an authentication service user ID and from there it can be granted access to make repeated verification requests against different users. The Active Directory can look up these users in an LDAP which is part of the Active Directory service. The Active Directory authentication module can retrieve a list of groups of which the specified user is a member and return this as a result of the authentication.

Operators accessing an operator interface need to authenticate to the server using smartcards containing private keys. The back end system that authenticates these should use the same API as the other authentication modules use to verify the logon from each user. Operators may also authenticate to the server using smartcard authentication via the client API although this is not essential.

The CS implements a simple token system that generates a ticket or token after a successful logon which must be resubmitted for each additional command that requires authorisation. The tokens are MACed with a credentials key which is stored in software by the CS and on disk in a mildly obfuscated file.

Once a token has been verified it can be cached to reduce time taken to verify it. When a token is issued by a CS it is automatically registered in the cache.

Each token contains the following data Username Time of Logon Lifespan of token Groups of which user is a member.

The CS checks the tokens provided with each command. The check includes at least cryptographic integrity and expiry of the token date.

The produced Cipher Data structures are preferably self defining i.e. managed such that they contain all the necessary information to allow the correct reciprocal operation to be performed. For example the command

DO encrypt FROM Application A TO Application B WITH clear text data returns an object which contained the following information 

DO decrypt FROM Application A TO Application B WITH cipher text data the cipher data contains the required information to determine the key required and the algorithms and mechanisms e.g. padding to be used to produce the corresponding clear text.

Key labels may be used to define the explicit instance of the Key to be used i.e. the current active instance and the cryptographic algorithm to be used.

A key UID is used to identify a unique instance of a key built using the metadata associated with a Key Label. The Key UID may be formed by appending the Key Label used to define the key to a string to insure that the instance is unique. A delimiter value may be used to separate the key label portion from the remainder of the string.

The CS is able to request keys from the Key Server KS . In return the CS may receive an encrypted key and associated metadata where the key can be enciphered in a form that can be handled by the receiving HSM.

The CS receives information about which key is required from the API call and from this it produces a KeyLocator containing all the information required to look up the correct key. The KeyLocator is passed to the KS which resolves it to a key.

The CS is not concerned with the resolution process. The KS then returns a KeyObject which contains the key data itself and all the required metadata. Within this KeyObject the key itself is returned in encrypted form encrypted under a Key Encryption Key KEK that is provided in the metadata but also may already be held by the HSM.

The KS is able to return via the API two sorts of keys keys encrypted under KEKs which need to be unwrapped and keys encrypted as HSM ready tokens which can be passed straight to an HSM.

All of the data structures specified for the key management interface have proper version information.

The CS can open multiple simultaneous connections to the KS in order to parallelise key requests. A single CS may have at least 10 requests running in parallel at any time possibly many more under high load.

The KeyLocator consists of an unordered set of attribute value pairs where all values are strings. The API between the CS and the KS may be encoded in XML. The USER FUNCTION and BASEFUNCTION fields are always present. However depending on the command there may or may not be FROM TO UID and ROLE fields. The fields are listed in Table 6 below.

Annex II lists several worked examples of key locators shown in both pseudo code and in XML notation together with the commands that produced them and the resulting key objects.

The commands for Key Management Requests are illustrated in . The commands include commands for requests from KS to CS and commands for requests from CS to KS.

Based on the parameters defined in the GET API call Key label Key UID the KS either determines the valid key instance to be used or returns the explicit key requested.

The GET API call is passed to the KS where it can be used to retrieve a specific instance of Key Metadata. The Key Metadata is used to define 

This command defines the explicit instance of the Key to be used i.e. the current active instance and the cryptographic algorithm to be used. This information is returned in the response.

The GET API call is passed to the KS where it can be used to retrieve a specific instance of a Key based on the key s Unique ID. The Key Instance has defined within it 

Based on the parameters defined in the PUT API call Key label Key UID the KS either determines the valid key metadata instance to be used or returns an error.

The PUT API call is passed to the KS where it is used to add a key instance based on a specific instance of Key Metadata. The Key Metadata is used to define 

Key segregation is maintained from the highest level of the key hierarchy i.e. under a separate set of Storage Master Keys.

The underlying HSMs provide cryptographic key typing which ensures keys used for different purposes are stored separately. Depending on the HSM architecture there may or may not be a hierarchy e.g. no hierarchy is present on a PKCS 11 HSM but there is on a Thales HSM8000 but either way there is strong key separation. The CS does not provide this functionality directly. Separation is ensured by the underlying HSMs.

Key separation is provided by the underlying HSM and the CS has to be reliant on the HSM functionality available. Where separate storage master keys are available e.g. HSM8000 has 16 keypairs these are used. In other circumstances separation is maintained but using mechanisms such as key variants.

The CS can use policy management to segregate keys and therefore keys intended for one domain cannot be used for the other but the primary protection mechanism is to ensure that both live and test KEKs are not loaded into the same HSM at the same time.

The CS stores a unique key for each crypto engine HSMs or SSMs within the KS. The unique key may be used to perform a cryptographic function i.e. a hash or key verification value KCV on a verifiable unique identification string of the CSP e.g. Serial Number for HSMs Hash of Code for SSMs . The unique key for each crypto engine can be distributed to the KS. The KS can verify the unique key for each crypto engine to complete enrolment.

Key export shall be performed under dual control as a minimum to external entities. A key export feature may not be necessary in the CS as the KS to which it interfaces may have this functionality as standard and within the KS UI is the best place for it.

The CS is responsible for distributing keys as requested by the KS but the KS takes ultimate responsibility for the destination of KEKs as they are manually loaded confirmed into the devices. In normal operation a unique KEK is used for each CSP and it is not possible to move KEKs from CSP to CSP.

The first step in the key distribution process is the registration of an end point Crypto Engine. This is followed by the distribution of a base key set to allow Cryptographic Engine to process keys supplied with cryptographic function requests. The key distribution supports multiple instances to allow segregation at the base key level.

The CS uses hashes of key tokens internally as a unique ID for that key and can also maintain KCVs or public key hashes as appropriate.

A cryptographically secure mechanism to identify HSMs during enrolment is provided and the CS mediates the exchange of keys between the KS and the introduced HSM. There can then be a direct manual confirmation step where custodians visit the HSM console and KS UI and confirm the cryptographic material. A unique key is set up between the KS and each CSP in every case.

In the case of HSMs supporting public key crypto the CS forwards the public key to the KS the operator UI displays the hash and the hash is checked out of band.

In the case of symmetric only HSMs the entire exchange is out of band for the CS. The operator UI supports dual control for modification of critical settings and undertaking key loading HSM enrolment activities. Note however that security exposure can only arise from enrolling the wrong HSM to the KS and not to the CS as the KS is the one who must trust the KEK .

The process that a Crypto engine under goes for induction into the CS KS is called Crypto engine enrolment. Enrolment of a Crypto engine or CSP shall require at least dual operator control. i.e. cryptographic administrators.

Hardware Crypto Engine Enrolment includes enrolment of RSA capable devices hardware and enrolment of symmetric only devices hardware .

Software Crypto Engine Enrolment also includes enrolment of RSA capable devices software and enrolment of symmetric only devices software . Software crypto engines can be enrolled in the same way as normal HSMs.

As illustrated in once the Crypto Engine Unique Key is registered to the KS it is used to generate via key derivation two Domain KEKs for Live and Test. The derivation data is distributed back to the Crypto engine under Crypto Engine Unique Key to allow the Live and Test domain keys to be recreated on the Crypto Engine.

Under each generated domain KEK the wrapping keys for the live and test domain are wrapped and distributed to the Crypto Engine. Once this has been completed the HSM is ready to accept work from the command builder.

Once a Crypto engine device has been enrolled into the KS then a set of base keys needs to be distributed to the Crypto engine in order to allow it to receive key material to support cryptographic API calls. The KS is able to request that a specific instance of a base key can be changed. The base keys are distributed under the unique device key that was registered when the Crypto engine was enrolled. A key policing mechanism is utilised to provide key segregation.

Each Crypto engine is required to implement a key protection mechanism to protect the Base key set. Hardware Crypto engines use the physical protection mechanism of the device. Software Crypto engines use obfuscation techniques to protect the base key set. Note that a hardware device is not necessarily required to support the deployment of software Crypto engines. A possible modification is to have software Crypto engines detect the presence of a hardware Crypto engine and declare an affiliation to a hardware device this would complicate the Crypto engine loading and registration process.

The keys to be distributed include Token Key Policy rule verification keys Audit MACing keys Domain wrapping keys under the each domain there is a set of KEKs to support the different cryptographic functions e.g. Enc Dec MAC Ver etc.

The KS has the ability to request that a specific instance of a base key can be changed. In order to eliminate any disruption to the CS baseline keys use the concept of an old current and new key. This requires that there is a pre distribution of the new baseline keys before the key activation period. The use of this method allows for variances in CS clocks. The method includes 

The KS distributes Keys under what it believes to be the current KEK. If the CS signals key not found then the KS will try under the new KEK if it has been generated if the CS still signals key not found then the KS will try under the old KEK if the CS still signals key not found this will trigger a key roll over using the current key.

The system utilizes a logging infrastructure to maintain logs that may enable postprocessing by various systems to achieve one or more of the following functions.

Audit information is protected via signature against alteration. Audit information is in a standard format. The information to be collected include 

The Audit MI component interfaces to an existing audit service. The server has the ability to cache audit records if the Audit MI service is unavailable and the logs cannot be uploaded. The audit records incorporate cryptographic mechanisms to prevent alteration of a record audit file and deletion re sequence of audit records.

The policy engine contains the policy rule set that defines the behaviour of the server. The policy engine allows the server to control which users get access to which keys. Without the policy engine it would not be possible to have multiple different applications using the CS safely at the same time. The policy engine also allows the server to control centrally what specific crypto settings are used per transaction. This means applications can have a knowledgeable central authority choose crypto algorithms for them. The policy engine further allows the server to control how keys are used for instance making them encrypt only if for instance the key is for archival. This improves security.

The policy engine receives a copy of the string representation of each command together with the current identity of the caller from the CS via an interface. The policy engine evaluates whether the caller is entitled to make the requested call and returns the selected cryptographic parameters e.g. key length if appropriate.

Policies are pushed to the engine updates to the internal policy engine only take place after the new polices have been validated. Polices are stored encrypted in a protected Policy Store in the server store when not in memory. Policies are persisted by the server and cryptographically signed e.g. using a digital signature to prevent alteration. Policies can be updated using an operator user interface. A new policy being uploaded is validated by checking of a digital signature and by dual control approval. The checking of the digital signature ensures that the policy has been approved and the dual control assures that an old policy file is not being loaded.

The Principle interface for hardware based modules are implemented via PKCS 11 these are also called HSM type A . For specialist applications requirements other vendor specific interfaces to HSMs are supported e.g. SEE code these are also called HSM type B .

The Principle interface for software based modules are implemented via PKCS 11 these are also called SSM type A . For specialist applications requirements other vendor specific interfaces to HSMs are supported e.g. SEE code these are also called SSM type B .

The server may support load balancing. However if the vendor installation supports load balancing then this is used in preference.

Keys can be retrieved from a remote KS and stored within a local key store. This local key store is utilised to hold keys frequently used by the Client API in order to reduce the overhead of a key fetch per request. Keys can also be written to a remote KS. The local Key Store may be queried by the remote KS.

Keys can be retrieved from a remote key store and cached in the local key store. Cache of keys on the server may be triggered by a request made during the registration of the Client API. Keys that are cached into the key store as the result of a part of a pre fetch call are flagged with the ID Token of the caller. When the Logoff command is called keys associated with the passed ID Token are flushed from the local Key store.

In order to facilitate a Client API failing to issue a logoff command keys written to the local key store may have an expiry time after which they will be flushed. If the key is required again a new copy must be fetched.

Keys from the KS are transmitted and stored within PKCS 11 wrappers. Keys may be wrapped under a set of KEKs defined by key function etc e.g. encrypt decrypt MAC HASH Sign and Verify.

The interface to the Key store is responsible for handling Key requests to the KS. This is discussed in detail in section 4 Key Management Requests .

The command builder is the processing heart of the server. Its core function of the command builder is to draw together all the information needed to actually run the corresponding command on the HSM. The specific functions supported by command builder are 

The command builder can send a copy of the augments to the API command to the policy engine together with contextual information such as the user name and the policy engine can return a yes no result that is enforced by the Command Builder within the CS.

The command builder augments the command with key retrieval requests that are satisfied when the command flows through the queue to the key locator stage. The key locator then tries to find the key in the cache and if it cannot find the key in the cache contacts the KS.

The CS does not need to maintain any credential lists for entities interacting with the server. It can pass the credentials used for verification of the application and the operator identification to an external authentication authority. The engine can pass the authentication request via a credential server. The interfaces to be supported are 

The operators can interface to the CS via a browser session over transport layer security TLS . The operator interface supports strong two factor authentication. The main functions of the operator interface include 

Sessions are maintained for operator logon. Session timeout might not be required so that operators can be logged on indefinitely. The operator UI does not replace or supersede any of the HSM provided tools e.g. the security world management tools for nCipher HSMs.

The operator needs to have the ability to start and stop the CS. He also needs to have the ability to control access to the server by each calling API in such a manner that the server can be started in a quiesced state to allow configuration changes to be performed or be set into a quiesced state which allows the current applications to complete but does not accept new connections. This has the effect of draining the work from the server.

Role based access is implemented to segregate the operational tasks that can be performed on the CS. The roles include 

The access to view the audit records is controlled by the operator s profile. The administrator and operator have the ability to view the audit trail and if required initiate a flush of the audit records to the audit server. The audit role is only allowed to view the audit log.

The operator interface supports remote addition configuration and deletion of cryptographic engine s associated with the CS.

The entities described herein such as the CS KS API CSP and calling applications may be implemented by computer systems such as computer system as shown in . Embodiments of the present invention may be implemented as programmable code for execution by such computer systems . After reading this description it will become apparent to a person skilled in the art how to implement the invention using other computer systems and or computer architectures.

Computer system includes one or more processors such as processor . Processor may be any type of processor including but not limited to a special purpose or a general purpose digital signal processor. Processor is connected to a communication infrastructure for example a bus or network . Various software implementations are described in terms of this exemplary computer system. After reading this description it will become apparent to a person skilled in the art how to implement the invention using other computer systems and or computer architectures.

Computer system also includes a main memory preferably random access memory RAM and may also include a secondary memory . Secondary memory may include for example a hard disk drive and or a removable storage drive representing a floppy disk drive a magnetic tape drive an optical disk drive etc. Removable storage drive reads from and or writes to a removable storage unit in a well known manner. Removable storage unit represents a floppy disk magnetic tape optical disk etc. which is read by and written to by removable storage drive . As will be appreciated removable storage unit includes a computer usable storage medium having stored therein computer software and or data.

In alternative implementations secondary memory may include other similar means for allowing computer programs or other instructions to be loaded into computer system . Such means may include for example a removable storage unit and an interface . Examples of such means may include a program cartridge and cartridge interface such as that previously found in video game devices a removable memory chip such as an EPROM or PROM or flash memory and associated socket and other removable storage units and interfaces which allow software and data to be transferred from removable storage unit to computer system . Alternatively the program may be executed and or the data accessed from the removable storage unit using the processor of the computer system .

Computer system may also include a communication interface . Communication interface allows software and data to be transferred between computer system and external devices. Examples of communication interface may include a modem a network interface such as an Ethernet card a communication port a Personal Computer Memory Card International Association PCMCIA slot and card etc. Software and data transferred via communication interface are in the form of signals which may be electronic electromagnetic optical or other signals capable of being received by communication interface . These signals are provided to communication interface via a communication path . Communication path carries signals and may be implemented using wire or cable fibre optics a phone line a wireless link a cellular phone link a radio frequency link or any other suitable communication channel. For instance communication path may be implemented using a combination of channels.

The terms computer program medium and computer usable medium are used generally to refer to media such as removable storage drive a hard disk installed in hard disk drive and signals . These computer program products are means for providing software to computer system . However these terms may also include signals such as electrical optical or electromagnetic signals that embody the computer program disclosed herein.

Computer programs also called computer control logic are stored in main memory and or secondary memory . Computer programs may also be received via communication interface . Such computer programs when executed enable computer system to implement embodiments of the present invention as discussed herein. Accordingly such computer programs represent controllers of computer system . Where the embodiment is implemented using software the software may be stored in a computer program product and loaded into computer system using removable storage drive hard disk drive or communication interface to provide some examples.

Alternative embodiments may be implemented as control logic in hardware firmware or software or any combination thereof.

Alternative embodiments may be envisaged which nevertheless fall within the scope of the following claims.

