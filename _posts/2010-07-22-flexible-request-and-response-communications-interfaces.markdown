---

title: Flexible request and response communications interfaces
abstract: Methods and systems for database storage allowing subscriber entities to create specialized interfaces for storing different classes of information based on subscribed-defined categories and parameters, allowing for efficient search and retrieval of the information by users using the subscriber-defined categories and parameters. The present technology allows users, such as suppliers, administrators, and others, to add inventory to a database through an interface, search for inventory via an interface, and view results of inventory searches. Inventory requests may be processed using local and remote data stores.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08239365&OS=08239365&RS=08239365
owner: 
number: 08239365
owner_city: 
owner_country: 
publication_date: 20100722
---
This application is a continuation and claims the priority benefit of U.S. patent application Ser. No. 11 833 867 filed Aug. 3 2007 now U.S. Pat. No. 7 788 250 and entitled Flexible Request and Response Communications Interfaces which claims the priority benefit of U.S. provisional patent application No. 60 821 516 filed Aug. 4 2006 and entitled Flexible Request Response Communications Interfaces. The disclosure of each of the aforementioned applications is incorporated by reference.

This invention relates to storage of items in a database and in particular to storage with user defined item categories and parameters to allow for extensible customized searching and retrieval.

The Internet is a vast pool of information and data that when manageable is a very useful resource. However data accessible via the Internet is stored following different standards file types and layouts thus finding relevant data is often difficult.

In searching for data and information on the Internet or on any network users have two choices first one may use a keyword search that matches the user provided search terms to the terms present in a document. For example one may enter a set of laptop specifications and results returned would hopefully include laptops for sale but may also include reviews of laptops or forum posts looking for laptops with those specifications.

Alternatively one may use a specially designed interface that searches a particular website or database or other resource for specialized information. For example if one were to visit a laptop website and fill in fields for memory size weight and hard drive capacity laptops fitting those criteria would be returned as results. However such specialized interfaces are only available on specialized websites and for certain products.

Thus in general the quality of search results is negatively proportional to the amount and variety of data that can be searched.

Disclosed are methods and systems for database storage allowing subscriber entities to create custom specialized interfaces for storing different classes of information based on subscribed defined categories and parameters allowing for efficient search and retrieval of the information by users using the subscriber defined categories and parameters.

In one aspect a method for defining an interface comprises sending an interface to a supplier for defining a new request type based on a set of attributes and a set of parameters receiving from the supplier a set of attribute values for the set of attributes and a set of parameter names and parameter data type values for the set of parameters creating a request type in a database based on the set of attribute values and associating the set of parameter names and parameter data types with the request type receiving from the supplier a supplier link for communicating with the supplier and associating the supplier link with the newly created request type thereby allowing the database to be searched for the supplier according to the request type and the set of parameter names and parameter data types and allowing communication with the supplier via the supplier link for the request type.

In another aspect a method for processing a search request comprises receiving from a user a set of search terms indicating a category and a set of parameter values associated with the category retrieving from a database a request type satisfying the search terms wherein the request type indicates one or more supplier links sending the search terms to one or more suppliers as indicated by the one or more supplier links receiving a set of results from the one or more suppliers in response to the search terms and sending the set of results to the user. Further aspects of the present invention are described herein.

In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of the invention. It will be apparent however to one skilled in the art that the invention can be practiced without these specific details.

Reference in this specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the invention. The appearances of the phrase in one embodiment in various places in the specification are not necessarily all referring to the same embodiment nor are separate or alternative embodiments mutually exclusive of other embodiments. Moreover various features are described which may be exhibited by some embodiments and not by others. Similarly various requirements are described which may be requirements for some embodiments but not other embodiments.

Disclosed is a system for allowing the creation of user defined request types and for allowing entities to communicate with the system using such request types. The system allows users to create specialized custom interfaces for different classes of information. The system utilizes a database to store information and respond to queries and in particular allows searching based on subscriber defined categories and parameters.

One or more users and subscribers hereafter also referred to as suppliers communicate with the system hereinafter also referred to as host via a network . A user may or may not be a subscriber . Via an interface the host receives and responds to messages hereinafter also known as requests from users and subscribers . Request types and how the system processes them are determined by the request s parameters as described below.

A subscriber interacts with a host via an interface. The interface may be a website an application programming interface API a program or any other means by which a subscriber may transmit data to and from the host over the network .

The system allows subscribers to add items to the system for storage and allows users to interact with the system for example to search the system for items of interest. A subscriber may be a product vendor service provider or anyone offering an item. As understood herein an item may be a product service website information source or anything else a supplier may provide.

The system allows subscribers to define categories and parameters describing the item being listed. Optionally supplier functions can be specified as well indicating a relationship of the supplier to the item being listed. One advantage of allowing individual subscribers to define categories and associated parameters is the spreading of the effort of creating a large collection of categories and parameters for structuring the items stored in the system . Another advantage of having individual subscribers define and or extend categories and associated parameters is that it eliminates or substantially reduces the need for a developer or designer to a priori generate a large number of different categories as well as a large number of parameters for further describing the different categories in order to structure or organize the items stored in the system .

For example for a request type indicating a category Automobile and a supplier function Seller the request parameters may be Make Model Year Color and a response parameter may be Price . However for a category of Automobile and supplier function Rental Service the request parameters may be From date To date Vehicle Class and response parameters may include Availability and Rate. 

At step or after specifying a category the subscriber specifies a supplier function. A supplier function indicates a relationship between the item and the subscriber. Some examples of supplier functions for the category Automobile are Seller Painter and Towing Service. 

In one embodiment the specified supplier function is preexisting. The interface may comprise a pull down menu a field a list or another method of specifying the preexisting supplier functions from which the subscriber may choose. In another embodiment the subscriber generates a new supplier function for the item to be listed under. The interface may provide a textbox or other methods of receiving a new supplier function from the subscriber.

At step a new request type is created for the combination of the specified category and supplier function. At step the request type is saved for subsequent reference.

After creating the request type the supplier specifies one or more parameters for the request type. Parameters are the attributes of the item being offered by the supplier and are used to distinguish different items stored under the same request type. Parameters are defined by parameter metadata. A parameter metadata indicates one or more of a name a display name a data type an owner type a description for the parameter or any other attribute.

In one embodiment parameters are associated with specific request types and are not shared between different request types. For example items under a request type given by a category Shirts and a supplier function Seller and items under a request type given by a category Shoes and a supplier function Seller may both have a parameter named Size but the parameters have their own sets of metadata. For example for Shirts the Size parameter may be of data type text and take the possible values of Small Medium and Large. On the other hand for the category Shoes the Size parameter may be of a data type Number or Integer and take on possible values of 5 5.5 6 etc. Thus while the two Size parameters may share a common name the parameters are not shared between the request types and comprise different metadata.

A data type indicates the type of data that can be used for a given parameter. A data type can represent a single piece of data such as a string a number a true or false value or a collection of data values such as an address with street city state and postal code data.

Optionally a data type may comprise a collection of data that can be extended or modified. For example a list data type may comprise a list of text for available colors for an item. Suppliers can add to such lists so that other suppliers or users can subsequently choose from them. A data type may also support a range. For example a number data type may indicate an exact value a minimum value and or a maximum value. Similarly a data type for date or time may indicate an exact value or it may indicate a range of values given by a From value and a To value.

In an embodiment wherein the subscriber specifies a preexisting request type the system presents a list of parameters associated with the request type when such parameters are already associated . Optionally at step the supplier may add one or more new parameters which will then be associated with this request type at step .

In another embodiment where the request type are not preexisting and are newly defined by a supplier the supplier defines a new set of one or more parameters to be associated with the request type.

A supplier may subscribe to a request type by associating a link hereinafter also referred to as a supplier request link with the request type. The supplier request link indicates where and how the supplier wants requests for the request type to be sent to the supplier as described in more detail below. This link may comprise a Uniform Resource Locator URL an email address an address for receiving an API call or other similar resource. The method of sending the request depends on the type of the supplier request link as should be apparent to one of ordinary skill in the art. The system may then use the supplier request link to communicate with the supplier for the request type.

Optionally a supplier request link indicates that some default information is stored on the system for a subscribed request type thereby eliminating the need for a separate communication with the supplier . An example of such default information is a web link to the supplier s web site or the supplier s contact information.

Another way a supplier may subscribe to a request type is by adding one or more items for the request type to the system . show a series of screenshots illustrating an example process of listing an item on system .

Starting with the supplier defines data for a particular listing. First the supplier may provide a supplier request link for requests to be sent to as described above. shows the supplier providing values for one or more of the parameters associated with the request type given by the category and supplier function. In this particular example the supplier has specified an item of category Automobile namely a blue Mercedes. Optionally the supplier may also provide a link indicated in the web link text box at the top of as well as other support information such as part numbers quantities etc.

Similarly if the supplier is a dealership wishing to list an item indicating an Oil Change service on the system the item may be listed under the category Automobile but with supplier function Oil Change Service and with such parameters as Inspection Points Price Location Opening Times etc.

In an optional embodiment system does not require the use of supplier functions. For example a category name may implicitly indicate a supplier function. Examples of such categories include Aircraft seller Automobile Repair Dog Groomer and Barber Shop. In such a case the request type is the category without a supplier function.

The system allows users to search the items added by subscribers . Upon a search request from a user the system responds with one or more results from suppliers that match the criteria set by the user s search.

In addition to providing supplier information as described in the system also retrieves items stored in the system which match the user s search criteria. is a flow chart illustrating a method for generating such a search response based on data stored in the system . At steps and the system receives a set of parameters associated with a search request from a user and retrieves a set of one or more items for the request type of the search request. Steps iterate over the retrieved items checking whether the item parameters satisfy the request s parameter values. For example a request parameter with name Length and value 20 matches an inventory item with exactly the same parameter name and value whereas a parameter value comprising a range matches an inventory item with a parameter value within that range. If the inventory parameters satisfy the request parameters then step creates a response to the user s search request. The system then presents the response to the user or saves the response for later presentation to the user.

Suppliers can send zero one or more than one response for a request. In one embodiment the response comprises a web link to the supplier site that provides more information or provides an opportunity for the user to engage with the supplier for a purchase for requesting more information to sign up for a service or to otherwise communicate with the supplier about the results.

Optionally a supplier may partially meet the search criteria but still be allowed to send a response for the request. Suppliers may use any of the request parameters in the response to determine whether they have items of relevance for the searcher. If a supplier does not have a relevant item the supplier may still respond with items or information of potential interest and the system may sort the responses by relevance for displaying to the searcher. Optionally users are given an opportunity to indicate their preferences relating to result relevance and sorting.

For example a user may submit a search with a value of Red assigned to a Color parameter. A supplier with a matching result may return the result comprising Red as the Color . Additionally a supplier with a result that matches the other parameters except with White assigned to the Color may still return that result and the system may assign a lower rank to the result in the sorting order for presentation to the user .

Optionally a supplier can control access to items which the supplier has listed in the system . Thus the supplier can use the system as a personal database or allow access to specific users or groups of users or the public as specified by the supplier . Optionally the system may restrict particular searches to the items of a particular supplier . One particular use for this is to allow users visiting a supplier s website to search that supplier s items. The user would be redirected to the system where the user will be restricted to the items for that particular supplier .

At step the metadata for the parameters associated with the request type are determined. At step the metadata is used to determine the names and display names of the parameters and create HTML code for receiving input via the HTML form. In the particular code example shown in the code comprises a display name and an input field of type text for a parameter.

wherein name is the name of the parameter and value name is the name of the data in the value. Examples of such names are

At step the HTML code for the parameters is added to the HTML form page. At step the HTML page is presented to the user over the network. The request type is then saved as a session parameter or as a hidden field in the form.

At step the system receives the HTTP request parameters which in the example shown here begin with a prefix of par. Steps iterate over the HTTP request parameters. For each parameter the system identifies the parameter name and determines whether a parameter with that name exists in the parameter map.

If a parameter with that name is not found steps determine a metadata according to the name and the request type create a new parameter with the data type found in the metadata add the newly created parameter to the parameter map and assign the parameter value to the parameter. Alternatively if a parameter with that name is found in the parameter map steps are skipped and the system assigns the parameter value at step .

A table for links comprises supplier request links for request types as described above wherein a link may be used for one or more request types. A request type may be associated with more than one link depending on the number of suppliers that have subscribed for that particular request type. An example of this is the case where a supplier uses one link such as a web address for more than one request type.

A link type table defines the types of the links such as email address web addresses API call addresses links for default information etc. A parameter metadata table associates parameters stored in table with corresponding request types.

A parameter metadata comprises one or more data types stored in table and one or more owner types stored in table . Parameters stored in table may be of data type Text stored in table parameter text data type Date stored in table parameter date data type Number stored in table parameter number or of other data types. Optionally parameters may be collectively stored in table regardless of data type with the parameter data stored in string format or in another universal format. Depending on the owner type a parameter belongs to a request or to a response or item . Other owner types are possible and the system is extensible to allow such extensions. Optionally separate tables can be used for request response and item parameters.

A user table stored entities that are allowed to send and receive messages to and from the system. A user may be an entity using the system to search for items of interest and may or may not be one of the entities that have subscribed to particular request types. Users in generate requests in for request types in . A request may generate zero or more responses in . As described above a response may comprise a link that the user may use to get more information. An optional response view tracker in may keep track of when and or how often a user clicks on such a link.

Optionally responses may be presented to the user in the order or priority decided by the user . In one embodiment a temporary table in the database is created using parameter names and metadata obtained from the request type s response parameter metadata for column definitions. For example for metadata that has the name Price and data type Number a columns with the name Price and data type Number is created in the table.

In an alternate embodiment for data types that comprise collections of data such as an address an indirect data type such as Distance can be used as the response s data type. Alternatively one of the data types and its name may be used as the collective data type for the column. For example a zip code and or city name data type may be used for a column.

The system can present results in sorted order based on database columns or parameter metadata. Responses may be generated in a desired ordering using a Structured Query Language SQL query with an order by clause. This method can be used to order the responses for a plurality of metadata or columns or to further filter the responses.

Optionally categories may comprise a hierarchical structure allowing suppliers to create categories within categories and supplier functions.

Optionally users may constrain search results to certain geographical regions such as nearby cities states countries or regions depending on user preference and search criteria.

In an optional embodiment the system provides suppliers with visibility into searches that comprise parameters similar or related to items offered by the suppliers . Optionally if a searcher is not anonymous a supplier may be provided an opportunity to provide a response to a request any time after the request has been sent out. For example if a supplier sees a search for an item which the supplier may offer but has not listed on the system the supplier may be provided an opportunity to provide a response to it.

Optionally a request type may comprise one or more attributes other than category or supplier function. One example of such an alternative attribute is an action request . An action request may indicate an action such as a Bank Transfer or a Request for more information. 

Optionally the system may send a request of a given request type to a subset of the suppliers subscribed to the request type based on user preferences persistently stored in the user s account of specified at the time of the request.

In an optional embodiment the system provides other request types such as Bank Transfer or any other operation that may take place between two parties and may be facilitated by the system as a request type.

Optionally the system provides a facility for ad targeting. A marketer may generate one or more relevant ads to a user at the time of the search request. The system may generate or provide the ad itself or coordinate with a third party who generates or provides the ad. The third party may be implemented by an automated ad generation engine such as a Sponsored Search ad generation service such as Google AdWords or a Contextual Advertisement ad generation service such as Google AdSense . The ad engine or the third party may generate an ad based on the request and its parameters and send the ad to the system for displaying to the searcher.

Optionally some or all suppliers have their data or services hosted by the system . In such an embodiment the messages are generated by the system .

Optionally requests and their responses may be saved in user accounts. Optionally information about when a web link in a response is clicked is saved for billing purposes. The system may also help in avoiding or reducing click fraud.

Optionally the system may verify the quality and or identity of the suppliers using the system using one or more options. One example comprises verifying that phone numbers and addresses are not reused when a supplier s account is suspended. This can be done by having the supplier send a text message or voice mail message to the phone number provided by the user. In another embodiment credit card numbers are verified. Alternatively security certificates may be used by one or more of the suppliers . Responses can be prioritized or filtered based on the presence of certificates based on the particular parameters of the certificates based on credit card verification or based on other information provided by suppliers .

While certain exemplary embodiments have been described and shown in the accompanying drawings it is to be understood that such embodiments are merely illustrative and not restrictive of the broad invention and that this invention is not limited to the specific constructions and arrangements shown and described since various other modifications may occur to those ordinarily skilled in the art upon studying this disclosure. In an area of technology such as this where growth is fast and further advancements are not easily foreseen the disclosed embodiments may be readily modifiable in arrangement and detail as facilitated by enabling technological advancements without departing from the principals of the present disclosure or the scope of the accompanying claims.

