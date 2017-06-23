---

title: Apparatus and method for providing remote medical services via an API and an open IPTV platform apparatus
abstract: An Open Internet Protocol Television (IPTV) platform is provided. By providing remote medical services to users in the Open IPTV environment using a remote medical service providing apparatus including: an application programming interface (API) calling unit to call, when receiving a request for receiving a remote medical service from a counselor's terminal, an API of an Open Internet Protocol Television (IPTV) platform; and a service provider to provide the remote medical service to a user through the API, it is possible to provide remote medical service operators with environments where they can develop and share various remote medical to services and content.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08830297&OS=08830297&RS=08830297
owner: Electronics and Telecommunications Research Institute
number: 08830297
owner_city: Daejeon
owner_country: KR
publication_date: 20100908
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean Patent Application No. 10 2009 0127287 filed on Dec. 18 2009 the entire disclosure of which is incorporated herein by reference for all purposes.

The following description relates to an Open Internet Protocol Television IPTV platform and more particularly to a technique for providing various application services in an Open IPTV platform environment.

In general Internet Protocol Television IPTV technology provides broadcasting services Video on Demand VoD services and interactive television services over the wired Internet by combining communication technology with broadcasting technology. The IPTV technology is evolving to accommodate various content and applications on the Internet using open interfaces.

Recently concerns on a remote medical service for providing medical information and medical services to users living at remote sites are increasing. The remote medical service provides medical information and doctors professional advice to users living a long distance away. The remote medical service is a comprehensive concept including medical treatment medical administration medical education video telephony between doctors and patients etc. which are carried out at a remote site.

An example of such remote medical treatment is to allow a user to transmit his or her blood pressure or glucose level from home to a medical institution through the Internet or a cable TV network and receive the results of medical examinations from the medical institution.

The following description relates to a technique for providing various remote medical services in an Open Internet Protocol Television IPTV environment.

In one general aspect there is provided a remote medical service providing apparatus including an application programming interface API calling unit to call when receiving a request for receiving a remote medical service from a counselor s terminal an API of an Open Internet Protocol Television IPTV platform and a service provider to provide the remote medical service to a user through the API.

Therefore remote medical services are provided in the Open IPTV platform environment thereby providing remote medical service operators with environments where they can develop and share various remote medical services and content. Accordingly limitations of existing remote medical services and existing content development environments may be overcome.

Also since an IPTV which is a user friendly interface is used when a remote medical service user consults with a counselor in real time the utilization range of service interfaces may extend.

In addition the utilization scheme of remote medical related application programming interfaces APIs and enablers that have already been built or will be built in the future is proposed to reduce costs for development of new remote medical services that can be proposed as new business models.

Other features and aspects will be apparent from the following detailed description the drawings and the claims.

Throughout the drawings and the detailed description unless otherwise described the same drawing reference numerals will be understood to refer to the same elements features and structures. The relative size and depiction of these elements may be exaggerated for clarity illustration and convenience.

The following description is provided to assist the reader in gaining a comprehensive understanding of the methods apparatuses and or systems described herein. Accordingly various changes modifications and equivalents of the methods apparatuses and or systems described herein will be suggested to those of ordinary skill in the art. Also descriptions of well known functions and constructions may be omitted for increased clarity and conciseness.

Referring to the remote medical service providing system includes a user s terminal a counselor s terminal a biometric signal measuring apparatus a remote medical service providing apparatus an Open Internet Protocol Television IPTV platform apparatus and a media server .

The user s terminal may be an IPTV setup box. The biometric signal measuring apparatus measures a user s biometric signals and transmits the results of the measurement to the user s terminal . The biometric signal measuring apparatus includes technical configurations such as body weight scales a sphygmomanometer or the like to measure height to weight blood pressure or heart rate.

Also the counselor s terminal may be a wired or wireless telephone or a terminal having video telephony functionality. The media server may be a video on demand VoD providing apparatus. According to an example the media server stores exercise video data. The media server extracts corresponding exercise video data in response to a service call from the Open IPTV platform apparatus and transmits the exercise video data to the Open IPTV platform apparatus .

A service user measures his or her biometric information such as a weight blood pressure or the like using the biometric signal measuring apparatus and transmits the measurement data to the remote medical service providing apparatus .

The remote medical service providing apparatus compares the measurement data with a pre stored reference value and analyzes the result of the comparison. Then when the result of the analysis indicates that the measurement data is within a normal range the remote medical service providing apparatus transmits a message informing of a normal status to the user s terminal . On the other hand if the result of the analysis indicates that the measurement data is not within the normal range the remote medical service providing apparatus calls the counselor s terminal .

The counselor selects a counseling service menu through the counselor s terminal and the remote medical service providing apparatus calls a counseling Application Programming Interface API of the Open IPTV platform apparatus .

Then when the counselor requests the remote medical service providing apparatus to send the measurement data of the service user with whom the counselor is in consultation the remote medical service providing apparatus calls an information providing API of the Open IPTV platform apparatus . Then the Open IPTV platform apparatus activates an information providing enabler to operate the information providing API thus providing a consultation environment where both the counselor and service user can see the measurement data.

In addition when the counselor requests the remote medical service providing apparatus to recommend an exercise VoD for the service user with whom the counselor is in consultation the remote medical service providing apparatus calls a media API of the Open IPTV platform apparatus . At this time the Open IPTV platform apparatus activates a media enabler to operate an API for exercise related VoD

The counselor may select an exercise suitable for treatment of the service user and explain the exercise while viewing an exercise media simultaneously with the service user.

In detail the remote medical service providing apparatus includes an API calling unit a service provider and a measurement information storage .

The API calling unit calls a corresponding API of an application gate which is provided by the Open IPTV platform apparatus according to a service type activated by the service provider .

The measurement information storage stores measurement information on the user s biometric signal which is received from the user s terminal and has been measured by the biometric signal measuring apparatus .

The service provider includes a measurement information manager a consultation connector an information provider and a media provider .

The measurement information manager receives measurement information on a user s biometric signal that has been measured by the biometric signal measuring apparatus from the user s terminal . The user measures his or her weight blood pressure or the like using the biometric signal measuring apparatus and transmits the measurement data to the remote medical service providing apparatus through the user s terminal . The measurement information manager databases the measurement data on the user s biometric signal stores it in the measurement information storage and then manages it.

Then the measurement information manager compares the measurement data with a reference value and analyzes the result of the comparison. If the result of the analysis indicates that the measurement data is within a normal range the measurement information manager transmits a message informing of a normal status to the user s terminal . The user checks that his or her heath is at a normal status through the user s terminal and may request the remote medical service providing apparatus to provide a remote medical service.

Meanwhile if the measurement information manager determines that the measurement data is not within the normal range the consultation connector automatically calls the counselor s terminal . For example the consultation connector provides information about the user whose measurement data is not within the normal range. Then when the counselor selects a call setup menu to consult with the user whose measurement data is not within the normal range the consultation connector calls a call setup API function that is provided by the Open IPTV platform apparatus in order to provide a consultation service.

When receiving a shared view service request from the counselor s terminal the information provider calls the information providing API corresponding to the shared view service in the Open IPTV platform apparatus wherein the shared view service means providing a certain service or data to two or more terminals at the same time in order for users of the terminals to view the service or data at the same time.

When receiving an exercise media service request from the counselor s terminal the media provider calls the media API of the Open IPTV platform apparatus .

In order to operate the call setup API called by the consultation connector of the remote medical service providing apparatus the application gateway activates a call setup enabler associated with the call setup API to perform a call setup for consultation.

The call enabler which has received the call setup request connects sessions to both the counselor s terminal and user s terminal thereby performing a call setup to allow video telephony between the counselor s terminal and the user s terminal .

In order to operate the information providing API execution of the shared view service for measurement data of biometric signals is required to the information providing enabler associated with the information providing API .

Then the information providing enabler extracts measurement data on the user from the measurement information storage of the remote medical service providing apparatus and transmits the measurement information simultaneously to both the counselor s terminal and user s terminal . Then the counselor s terminal and user s terminal display the measurement data about the user through viewers so that the counselor and user can simultaneously examine the measurement data while talking over the telephone.

When the counselor requests another kind of measurement data the information providing enabler extracts the requested kind of measurement data from the measurement information storage of the remote medical service providing apparatus and transmits the extracted data to both the counselor s terminal and the user s terminal .

Then in order to operate the media API the media enabler for providing an exercise VoD service is activated.

The media enabler transmits information on exercise VoD content requested by the Jo counselor to the media server which stores exercise VoD. The media server detects a location at which the corresponding exercise VoD content is stored and transmits the location information of the exercise VoD content to the media enabler . Then the media enabler transmits the received location information of the exercise VoD content to both the counselor s terminal and user s terminal .

Successively the counselor s terminal and user s terminal access the media server based on the location information of the exercise VoD media content to request the media server to send exercise VoD streams or to receive the exercise VoD content from the media server .

Also when the counselor additionally selects other exercise VoD content the media enabler may transmit information on a location at which the additionally requested exercise VoD content is stored to both the counselor s terminal and user s terminal so that the counselor s terminal and user s terminal can simultaneously display the additionally requested exercise VoD content.

First referring to a user measures his or her biometric signal such as weight blood pressure or the like. The measurement data of the user s biometric signal is transmitted to a remote medical service providing apparatus. In other words the remote medical service providing apparatus receives measurement data of a user s biometric signal from a user s terminal operation .

The remote medical service providing apparatus databases stores and manages measurement data of subscribers biometric signals. The remote medical service providing apparatus compares the measurement data with a reference value operation .

Successively it is determined whether the measurement data is within a normal range based on the result of the comparison operation . When it is determined that the measurement data is within the normal range the remote medical service providing apparatus transmits a message informing of a normal status to the user s terminal operation .

Accordingly the user may check his or her health status through the user s terminal and request remote medical service according to the checked result operation . When the user requests remote medical service the remote medical service providing apparatus may transmit user menu information to the user s terminal which is for example an IPTV set top box. The user menu is configured in a form to allow a user to select a desired remote medical service and select analysis data on at least one piece of his or her biometric data. The user may select at least one information item such as blood pressure and body fat from the user menu and the remote medical service providing apparatus provides information corresponding to the information item selected by the user to the user s terminal operation .

Meanwhile when the measurement data is not within the normal range referring to the remote medical service providing apparatus automatically calls a counselor s terminal operation . If the counselor selects a call setup menu to consult with the user operation the remote medical service providing apparatus calls a call setup API provided by an Open IPTV platform apparatus in order to provide a consultation service operation . In order to execute the call setup API an application gateway in the Open IPTV platform apparatus activates a call setup enabler associated with the call setup API and requests the call setup enabler to perform a call setup for consultation operation .

The call setup enabler that has received the call setup request connects sessions to both the counselor s terminal and user s terminal operation thereby performing a call setup to allow video telephony between the counselor s terminal and the user s terminal operation .

The counselor monitors the user s measurement data through a menu that is provided by the remote medical service providing apparatus to select a counseling service item. Referring to the counselor may select a shared view service as necessary while talking with the user over the telephone in order to explain the user s measurement data operation . When receiving a shared view service request from the counselor s terminal the remote medical service providing apparatus calls an information providing API corresponding to the shared view service in the Open IPTV platform apparatus operation . The application gateway of the Open IPTV platform apparatus requests in order to operate the information providing API an information providing enabler associated with the information providing API to execute the shared view service operation .

The information providing enabler extracts the user s measurement data from measurement information storage of the remote medical service providing apparatus operation and then transmits the extracted measurement data to both the counselor s terminal and user s terminal operation . The counselor s terminal and user s terminal display the user s measurement data through viewers. Accordingly the counselor and user can simultaneously examine the measurement data on the user while talking over the telephone.

Thereafter when the counselor requests another kind of measurement data operation the information providing enabler extracts the corresponding kind of measurement data from the measurement data storage of the remote medical service providing apparatus and transmits the extracted data to both the counselor s terminal and user s terminal operation .

Thereafter when the counselor recommends an exercise needed for the user based on the user s measurement data the counselor may select an exercise media service through the counselor s terminal. The exercise media service is used to more efficiently provide medical consultation by providing a media file relating to an exercise needed for a user based on measurement information on the user s biometric signal.

Referring to when receiving an exercise media service request operation the remote medical service providing apparatus calls a media API of the Open IPTV platform apparatus operation . Then in order to execute the called media API the remote medical service providing apparatus activates a media enabler for providing an exercise VoD service operation .

Then the media enabler transmits information on exercise VoD content requested by the counselor to the media server which stores exercise VoD. The media server detects a location at which the corresponding exercise VoD content is stored and transmits the location information to the media enabler operation . The media enabler transmits the location information of the exercise VoD content to both the counselor s terminal and user s terminal operation .

The counselor s terminal and user s terminal access the media server based on the location information of the exercise VoD media content to request the media server to send exercise VoD streams or to receive the exercise VoD content from the media server.

Accordingly the counselor may explain an efficient exercise method to the user while viewing exercise VoD content suitable for the user simultaneously with the user operation .

Also when the counselor additionally selects other exercise VoD content operation the media enabler may transmit information on a location at which the additionally requested exercise VoD content is stored to both the counselor s terminal and user s terminal so that the counselor s terminal and user s terminal simultaneously display the additionally requested exercise VoD content operations and .

Meanwhile the remote medical service providing method described above may be recorded as a computer program. The program may be stored in a computer readable recording medium and implemented by being read and executed by a computer. The computer readable recording medium may include a magnetic recording medium an optical recording medium or the like.

A number of examples have been described above. Nevertheless it will be understood that various modifications may be made. For example suitable results may be achieved if the described techniques are performed in a different order and or if components in a described system architecture device or circuit are combined in a different manner and or replaced or supplemented by other components or their equivalents. Accordingly other implementations are within the scope of the following claims.

