---

title: Searching and browsing URLs and URL history
abstract: System(s) and/or method(s) (“tools”) are described that present indicia for implicitly and explicitly user-associated web pages of a network browser application. The tools can present these indicia in a single graphic user interface, in response to a user's selection of a single unified access point, or in response to a search of the browser's user-associated web pages.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09141716&OS=09141716&RS=09141716
owner: MICROSOFT TECHNOLOGY LICENSING, LLC
number: 09141716
owner_city: Redmond
owner_country: US
publication_date: 20101005
---
This application is a divisional of and claims priority to U.S. patent application Ser. No. 11 179 155 filed on Jul. 12 2005 now U.S. Pat. No. 7 831 547 the disclosure of which is incorporated by reference herein.

Network browser interfaces currently permit users to view locators for web pages. Some interfaces display universal resource locators URLs for a user s favorite web pages in a graphical user interface for instance. And some interfaces display URLs for web pages that a user has visited. These interfaces may also show URLs for web pages found in searching a user s favorites or history. But these interfaces can make poor use of a user s display area confuse users or be difficult for users to navigate. Some interfaces for example present web page histories in cascading drop down menus which can be hard for some users to navigate especially those that cannot use a mouse well.

System s and or method s tools are described that present indicia for implicitly and explicitly user associated web pages of a network browser application. The tools can present these indicia in a single graphic user interface in response to a user s selection of a single unified access point or in response to a search of the browser s user associated web pages.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter.

The same numbers are used throughout the disclosure and figures to reference like components and features.

The following document describes tools that present indicia for implicitly and explicitly user associated web pages of a network browser application. In one embodiment the tools present these indicia in a single graphic user interface that floats or docks with the browser s user interface. In other embodiments the indicia are presented in response to a user s selection of a single unified access point opening the browser or a search of the browser s user associated web pages.

Before describing the tools in detail the following discussion of an exemplary operating environment is provided to assist the reader in understanding where and how the tools may be employed. The description provided below constitutes but one example and is not intended to limit application of the tools to any one particular operating environment

The communication network enables communication between the computer and the network computer and may comprise one or more of an intranet such as a company s internal network the Internet and the like.

The following discussion describes exemplary user interfaces and a related process for presenting indicia of user associated web pages. The process is shown at in and describes exemplary manners in which the tools interface with a user of a network browser. This process is illustrated as a series of blocks representing individual operations or acts performed by elements of environment such as user interface module . This and other processes described herein are directed to these elements to aid the reader in understanding particular embodiments of the tools and are not intended to limit application of the tools to this environment. These processes can be implemented in any suitable hardware software firmware or combination thereof In the case of software and firmware these processes represent sets of operations implemented as computer executable instructions.

Block presents a single unified access point enabling a user to gain access to indicia for explicitly and implicitly user associated web pages. The access point may comprise an icon graphic or selectable text. The user may select the access point with a single user action.

Block receives a user s selection to present a user interface enabling access to indicia for explicitly and implicitly user associated web pages. Block can receive this selection through a user clicking on access point shown in or in other manners.

Block presents a user interface enabling access to indicia for explicitly and implicitly user associated web pages. This user interface can comprise a single navigable graphic user interface through which the indicia may be viewed and or selected. It can be a window docked within a network browser s interface or be a floating entity for instance. The indicia may be selected by the way in which the web pages are associated with a user such as those explicitly associated with a user by the user marking the web pages as favorites explicitly associated with a user by the user marking the web pages as feeds and implicitly associated with a user by the user viewing the web pages thereby enabling a history of viewed web pages.

Block receives selection to view indicia for one or more explicitly and or implicitly user associated web pages. Here block receives a user s selection of favorites control shown in .

Block determines an order or hierarchy in which indicia will be displayed. Block can order indicia for explicitly user associated web pages alphabetically chronologically or following a user selected order. Block can set an order or hierarchy for indicia of implicitly user associated web pages following various algorithms. One of these algorithms orders indicia with a weighted combination of when web pages were viewed and how often they were viewed such as ordering indicia for pages visited most often in the last three weeks.

Block presents indicia for explicitly and or implicitly user associated web pages in a graphic user interface. The graphic user interface can comprise one or multiple windows or regions. The indicia may be presented automatically e.g. when a network browser is opened responsive to selection by a user of a single unified access point or responsive to a selection to view indicia for one or more types of user associated web pages. Thus block may act independent of or responsive to blocks and .

Favorites indicia are presented in a navigable hierarchy the hierarchy defined by a user though it may also be defined by user interface module . Here one favorite web page entitled MSN.com is indicated with two indicia a graphic at and text at . The graphic or text may be user defined web page defined or defined by user interface module . Two other indicia are oriented subservient to MSN.com . These other indicia are web pages that are related to and more specific than the parent MSN.com. Indicia for these web pages have text here descriptive titles which are shown at and . Similarly indicia for other favorite web pages is also presented here CNET.com at and Geek.com at and eBay.com at and Ofoto.com at and Ofoto Family Pics at and Ofoto Trip Pics at . A user may select one or more of the indicia after which network browser loads the associated web page s into a web page viewing area .

History indicia are presented based on their order determined at block . Here user interface module presents indicia for the top seven web pages based on which have been viewed by the user most often in the last three weeks. The indicia may comprise text or a graphic or icon e.g. text and icon . Here the indicia are square tiles comprising an icon provided by the particular web page or textual indicia created by user interface module .

The user interface module can use metadata associated with the web page to create indicia. For example the user interface module can truncate the URL for the web page and display it. Often a first portion of a URL is not particularly descriptive of the page truncating it can allow a descriptive indicia without requiring extensive space to present it. For example for a URL of 

Process shown in describes exemplary methods for searching user associated web pages. This process is illustrated as a series of blocks representing individual operations or acts performed by elements of environment such as search module and user interface module .

Block enables a user to enter a search. Continuing the illustrated embodiment described above user interface module provides search entry field as part of navigable window of .

Block receives search characters such as a word. sets forth the window of with a search term Canon shown in field at .

Block searches user associated web pages based on the search characters. Block can search one type of user associated web page such as just history feeds or favorites. Block can also search multiple or all types regardless of how the pages are associated with a user. This enables a user with a single search to see web pages having a search term or character that the user has viewed either recently or ever marked as a favorite and marked as associated with a desired feed for example. By default search module searches all user associated web pages.

Search module can search with all of the search characters at once or one at a time as they are entered. Here the search module searches character by character with each new character causing another search of that character and predecessor characters. So the search module searches for user associated web pages and their indicia or other metadata for a C then for a Ca then for a Can and so forth. This can enable a user to quickly find user associated web pages by searching in real time. A user may find the web page he or she is looking for with only Can thereby saving the user time.

Block can search for character matches in a web page itself and metadata for the web page. Here the search module searches text in the web page itself and metadata. The metadata can comprise the web pages titles or URLs metatag keywords metatag descriptions and user defined keywords.

Block determines an order or hierarchy for the results such as through a user driven weighted search. Here search module weighs the results based at least in part on user driven factors for the web pages such as user defined keywords user defined titles and the like. The search module orders the results of the Canon search with a highest weight given for a user defined keyword match if the web pages have user defined keywords followed by descending weighting factors for the titles and URLs the full text and the metatags.

Block can also arrange the results into groups having a similarity. The grouping can be based on those web pages having the same domain name and or the same user associated type e.g. history feeds and favorites . Here the results of the Canon search of the history feeds and favorites web pages comprise eleven web pages. The groups defined here are those web pages from favorites two pages those from feeds two pages those sharing the eBay domain name three pages and those sharing the CNET domain name four pages .

Block presents indicia for user associated web pages responsive to the search. Block can present the indicia in a flat list or a hierarchy e.g. a tree . Here the user interface module presents indicia oriented in a tree by groups and in indicia region shown in . Group is for web pages from the user s favorites having a group heading of Favorites shown at group is for web pages from the user s feeds having a group heading of Feeds shown at group is for web pages from eBay having a group heading of eBay.com shown at and group is for web pages from CNET having a group heading of CNET.com shown at .

The user interface module can present the indicia in real time here with the search module presenting web pages having just a C then those having Ca and so forth these results are not shown only results of Canon are shown .

The indicia may comprise icons or graphics for the web pages not shown . It may also comprise text resulting from the search. Text resulting from the search can comprise the search characters and surrounding previous or following characters. This provides the user with a small snap shot of the content of the web page. The indicia in are all text from the search showing the search characters Canon and the following text from the web page to the end of the sentence or the text that fits whichever is less.

The tools also enable a user to mark multiple web pages with a single user action. A user may mark a group of web pages as favorites or as one favorite for the entire group. The tools can also open multiple web pages with a single user action.

Process shown in describes exemplary methods for marking and opening multiple web pages. This process is illustrated as a series of blocks representing individual operations or acts performed by elements of environment such as marking opening module .

Block enables selection of one or more indicia of multiple web pages. Block can present indicia for web pages resulting from a search either of user associated web pages or otherwise selection by a user a list of user associated web pages or otherwise.

Continuing the illustrated embodiment described above consider again . Here two sets of indicia are shown. One set comprises search results of user associated web pages shown in groups the indicia shown at . The other set comprises history indicia shown at . A user may select more than one of these indicia such as by selecting multiple history indicia with highlighting. A user may also select a single indicia for multiple web pages such as by clicking on a group heading e.g. or .

Block receives a user s selection of multiple web pages. Here a user selects indicia for four web pages with a single user action that of clicking on group heading entitled CNET.com. 

Block opens multiple web pages responsive to a user s selection. Here marking opening module opens web pages associated with the four indicia presented as part of group . The web pages may be presented in separate windows or one may be presented and the others readied for presentation.

Block receives a user s selection to mark multiple web pages. A user may select one indicia for multiple pages all web pages currently opened multiple indicia for multiple web pages and the like. The user may do so with a single or multiple user actions. In a user can select indicia to mark all the search results those of a particular group or various open web pages. A user can also select to mark all opened web pages. Here assume that a user selects heading to mark the web pages of this group as a single favorite. The window may present options enabling a user to open or mark the group such as to open all the web pages in a group or save them as one or more favorites responsive to hovering over the indicia.

Block marks multiple web pages. Here marking opening module marks all of the web pages under heading as favorites responsive to the user s single action. The module can mark each web page as a separate favorite or as a single favorite having multiple web pages. Here the module marks a single favorite having these four web pages.

After marking web pages as a single favorite a user may select to open all of the web pages in the favorite with a single user action. The tools may do so following block or otherwise.

The above described tools present indicia for implicitly and explicitly user associated web pages of a network browser application. They can permit a user to view and interact with different types of user associated web pages in a single graphic interface. This can make easier or more intuitive a user s interaction with his or her favorite feed and history web pages. Although the tools have been described in language specific to structural features and or methodological acts it is to be understood that the subject matter defined in the appended claims is not necessarily limited to the specific features or acts described. Rather the specific features and acts are disclosed as exemplary forms of implementing the claimed system method and or computer readable media.

