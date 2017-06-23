---

title: Price comparison process and system
abstract: A data processing system is provided for obtaining client's real time pricing information from password protected secure data bases, and sending the client a price comparison report. If the web sites are secure, the system provides real time impersonation of the client in order to gain access to the web site.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08438076&OS=08438076&RS=08438076
owner: Y-Check, LLC
number: 08438076
owner_city: Kalamazoo
owner_country: US
publication_date: 20100212
---
This application claims priority to U.S. Provisional Application Ser. No. 61 152 348 filed Feb. 13 2009. The entire contents of the aforementioned application are incorporated herein.

The present disclosure relates to computer software and more particularly to a method system and computer software for comparing prices for the same item from various wholesalers with whom the purchaser has a password protected account. This product price comparison software compares prices among various wholesalers where pricing data is confidential and secured by logon and password and is not available to the general public.

Price comparison web sites are currently quite popular and widely available to the general public. These sites allow a user to type in a search phrase and return results from many different retailers. Examples of such sites can be seen at www.Bizrate.com www.PriceGrabber.com and www.NextTag.com. These and other comparison sites only search and compile data regarding products and prices that are available for sale to the general public. These and other sites and shopping services do not and cannot provide comparison pricing that is available from wholesale distributors and vendors.

Independent retailers such as pharmacies restaurants and others often buy items for resale from a specific group of wholesalers available in a geographic region. Retailers will frequently negotiate a purchase agreement with a primary wholesaler whereby the retailer agrees to buy a specified percentage of all purchases through the wholesaler in exchange for discount pricing rebates etc. In exchange for this purchase commitment the independent retailer is granted special pricing but this special pricing can vary greatly from retailer to retailer depending on the retailer s annual purchase volume specific contractual obligations buying group membership chain code affiliation available wholesaler stock manufacturer vendor promotions expiration date of the product and other factors.

Once the retailer has a purchase agreement with a wholesaler he generally takes it on faith that he is getting the best price and while most retailers have a secondary and tertiary backup wholesaler they do not aggressively compare prices because it is not convenient. Retailers are known to purchase large quantities of an item that are suddenly offered at very special reduced prices only to learn later that the same item was available from one of their alternate wholesalers at a lower price.

Some retailers with commitments to buy a specified percentage of total purchases from their primary wholesaler are reluctant to even purchase from a secondary wholesaler because they do not have a convenient method to quickly compare the savings from buying the secondary wholesaler item with the loss of rebate from the primary wholesaler.

If a retailer wants to seek out the best available price for an item the retailer would have to manually check for a price at each contracted wholesaler s web site through a POS point of sale system an electronic price list via telephone or even manually looking the item up in a catalog. This is a tedious and time consuming task for the retailer. The information returned in each of the previous examples would need to be compiled into a standardized list to be properly evaluated by the retailer. Consequently retailers frequently continue buying from their primary wholesaler and assume they are getting the best price or at least a fair price unaware of the savings available through another source and unable or unwilling to take the time and effort to compare prices.

Many wholesalers offer their retail customers product and price search capabilities on their websites. In order for the retailer to access this confidential information each site usually requires unique user names and passwords. These unique user names and passwords can be created maintained and recalled for each wholesale account.

What is needed is a method and system for automatically and rapidly compiling confidential pricing data from specifically contracted wholesalers in a manner that can be quickly and easily evaluated by the independent retailer. In so doing the retailer is able to make an informed purchase decision.

The present disclosure satisfies these needs and shortcomings by providing a method and system to automate the task of searching confidential price data from different individual wholesaler account websites and compiling this data into a standardized list useful for comparing prices.

The present disclosure further satisfies the aforementioned shortcomings by automating the compilation and search of wholesaler confidential pricing data not directly available from a web site. This information could be through other means such as email file transfer electronic data interchange web services or other methods.

The present disclosure further satisfies the aforementioned shortcomings by allowing only one logon and password to search and compile the confidential pricing data. Impersonation can be used to authenticate extract and compile information in its many different formats into a single standardized list.

The exemplifications set out herein illustrate embodiments of the disclosure that are not to be construed as limiting the scope of the disclosure in any manner. Additional features of the present disclosure will become apparent to those skilled in the art upon consideration of the following detailed description of illustrative embodiments exemplifying the best mode of carrying out the disclosure as presently perceived.

The price comparison service would in turn request and compile pricing data based on the client search request from a variety of sources such as a secured web site a secured web service or from a client specific price catalog stored in an electronic database . The price comparison service requests and compiles data from all the various available resources and returns the search results to the requesting client.

Many wholesalers offer their retail customers product and price search capabilities on their website. In order for the retailer to access confidential price data the retailer can logon to the secured website enter a user name and password enter a search phrase and wait for the price data to return ascertain the best price available and then log off the secured website . This process is then repeated for each wholesale web site that contains pricing data. The present embodiment uses impersonation in real time to emulate these steps and extract the price data to be used by the price comparison service .

When a client initiates a search request through the present data processing system he is actually initiating a request for retrieving data which already exists on a secure data base. Accordingly a search request is synonymous with retrieving data. Both secured web sites and secure File Transfer Protocol services can act as secured data bases. Both types of services can provide information when a customer initiates a request to retrieve information through the present data processing system.

Confidential price data may be accessed through a secured web service which may be implemented as a web application programming interface or web API. These secured web services often require client authentication. The client application would make a service request after authentication and then parse the returned data. The present embodiment uses impersonation in real time to emulate these steps and extract the price data to be used by the price comparison service .

Confidential pricing data may be accessed through a secured file transfer protocol or File Transfer Protocol FTP service . This process entails the retailer to navigate to a specific FTP location enter a user name and password download the available electronic price file log off the FTP service and then search the electronic price file for the desired product and price. The present embodiment uses impersonation to emulate these steps and import the price data through a price file import service into an electronic database that stores confidential price data in unique specific price catalogs . These client specific price catalogs are then used by the price comparison service when compiling client search request .

Confidential pricing data may be accessed through an Email . The present embodiment imports the emailed price data through a price file import service into an electronic database that stores confidential price data in unique specific price catalogs . These client specific price catalogs are then used by the price comparison service when compiling client search request .

The present embodiment deals specifically with comparing secured and confidential pricing information. The present embodiment can maintain user credentials for each wholesaler user combination as demonstrated in and respectively.

The authentication process requires the user to enter a unique user identification and a password to access the price comparison service . If the unique user identification and password are accepted a user session begins allowing the authenticated user access to the price comparison service . If the unique user identification and password are rejected access to the price comparison service is denied and the failure returned to the requesting process.

In an example embodiment price comparison takes place as a result of a client search request . is block diagram that illustrates the processing of that search request. As an example of the search process a pharmacist may be looking for the best price for a generic drug hydrocodone. After the user was authenticated to use the price comparison service as demonstrated in the user would submit the search phrase hydrocodone. 

The search phrase is validated for security purposes . If the phrase is invalid failure is returned . If the search phrase is valid the phrase is passed on to the price comparison service along with the user session data created during the authentication process.

The user session data is used to create a unique list of wholesalers that are available to that user. The number of wholesalers available to a user is limited only by the contractual obligations of the individual retailer. For each wholesaler in the created list the search phrase and the user session data is then passed to a wholesaler module specifically designed to process the data from each wholesaler and extract the confidential price data from the designated sources and . The data is returned to the price comparison service and matched against a common description catalog . The processed data is then written as a temporary result set into an electronic database. The results are then returned and can be accessed and manipulated during the user session.

In an example price comparison takes place as a result of a client search request . illustrated the search process itself while was a block diagram showing the overall system architecture needed to implement an example embodiment. The actual price comparison derives confidential price data from three sources in real time a secured web site a secure web service and unique specific price catalogs that are stored in an electronic database.

The credentials are passed to a website logon script . The logon script is executed . The logon script starts a web browser session navigates to the secure website logon URL uniform resource locator enters the user name credential in the logon name field enters the password credential in the password name field and then clicks the logon button or link just as if the user had completed the task manually.

The wholesaler software module confirms the success of the logon . If the logon fails the failure is returned to the calling process . If the logon is successful the search phrase is passed to website search script .

The website search script is executed using the previously created web browser session . The website search script navigates to the secure website product search page enters the search phrase into the search field and the clicks the search button or link just as if the user had completed the task manually.

The wholesaler software module confirms the success of the search . If the search failed the failure is returned . If the search was successful the search page results are passed to a parsing template .

The parsing template extracts pricing data from the results and matches the data for each returned item against a common description catalog . The results are then written to an electronic database for temporary storage . The parsing template checks the search results see if more data matching the search request is available. If more data is available a get next results script is executed using the previously created web browser session .

The script locates and clicks the next button or link button just as if the user had completed the task manually. This action causes the web browser to navigate to the next available results URL. The wholesaler software module confirms the success of the next results script . If there are more results the results are passed to the parsing template for processing .

This loop of actions and continues until no more results are available . When all results have been processed the impersonation logoff script is executed . The impersonation logoff script navigates to the secured web site URL containing the logoff button or link clicks the logoff button or link and ends the browser session . The results are then returned .

The credentials are passed to a web service impersonation script . The web service impersonation script is executed . The web service impersonation script would utilize the published web service API to navigate to the web service location authenticate using the retrieved user credentials and extract the search results. The wholesaler software module checks for results . If there are no results the process is terminated . If results exist they are passed to a parsing template to extract the confidential price data . The resulting data for each returned item is matched against a common description catalog . The matched results are then written to an electronic database for temporary storage . The results are then returned .

In this example the search phrase is submitted to the wholesaler module where the user credentials that identify the user are retrieved from secured storage in an electronic database .

The credentials are used to access and search the unique specific price catalog created for the user. The wholesaler software module checks for results . If there are no results the process is terminated . If results exist the resulting data for each returned item is matched against a common description catalog . The matched results are then written to an electronic database for temporary storage . The results are then returned .

In an example a request for a price catalog could be scheduled to happen at a specific date and time or it could be a request in real time. The request for a price catalog via FTP is submitted to the wholesaler module where the user credentials that identify the user are retrieved from secured storage in an electronic database .

The credentials are passed to a File Transfer Protocol FTP logon script . The logon script is executed . The logon script starts an FTP session navigates to the secure FTP location enters the user name credential in the logon name field enters the password credential in the password name field and initiates the logon just as if the user had completed the task manually.

The wholesaler software module confirms the success of the logon . If the logon fails the failure is returned to the calling process . If the logon is successful an FTP Get command is executed in the FTP Get Price File script just as if the user had completed the task manually.

The wholesaler software module confirms the success of the GET command . If the GET fails the failure is returned to the calling process . If the GET is successful an FTP logoff script is executed just as if the user had completed the task manually.

The retrieved price file data is passed to an import template in the file import service . The processed data is then written to a unique specific price catalog stored in an electronic database and success is returned to the calling process .

In an example an email is received and the Email address is verified against the client database and the referenced wholesaler data is retrieved and validated . If the address is not valid the failure is logged . If the address is valid the email price file attachment is downloaded . The price file download is verified . If the download failed the failure is logged .

If the price file download is successful the retrieved price file data is passed to an import template in the file import service . The processed data is then written to a unique and specific price catalog stored in an electronic database and success is logged .

The disclosed software can be web based and used on various computers. The search results can be returned from the client search request by various means including electronically and they may be printed.

The client may input one or more search terms and if desired by the client the search results may be organized into reports that may be printed by the client to create a tangible output. A wide variety of output formats are available depending upon the preference of the client. The following examples illustrate typical tangible printed outputs. Many other printed outputs besides those shown in the examples are possible.

This example shows a typical report for a request for information retrieval from 3 wholesalers and 2 products and two package sizes for one product.

This example shows a typical report for a request for information retrieval from 3 wholesalers and a single product.

