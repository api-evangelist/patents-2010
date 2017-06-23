---

title: Method and system of retrieving Ajax web page content
abstract: The present disclosure describes a method and a system of retrieving Ajax web page content. The method of retrieving Ajax web page content includes: obtaining information of web page codes; retrieving JavaScript information in the information of the web page codes; analyzing the JavaScript information to determine function(s) that include(s) Ajax call(s) in the web page codes; and triggering the determined function(s) that include(s) the Ajax call(s) to obtain web page content. Through analyzing JavaScript information in web page codes, the above technical scheme obtains function(s) that include(s) Ajax call(s) in the web page codes and further triggers the function(s) to obtain web page content generated thereby, thus achieving retrieval of dynamic content in an Ajax web page. Using the above technical scheme, a search engine can collect more complete web page contents and hence provide a better search service to users.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08413044&OS=08413044&RS=08413044
owner: Alibaba Group Holding Limited
number: 08413044
owner_city: Grand Cayman
owner_country: KY
publication_date: 20100331
---
This application is a national stage application of an international patent application PCT US10 29444 filed Mar. 31 2010 which claims priority benefit of Chinese patent application No. 200910133630.5 filed Apr. 2 2009 entitled METHOD AND SYSTEM OF RETRIEVING AJAX WEB PAGE CONTENT which applications are hereby incorporated in their entirety by reference.

The present disclosure relates to fields of networking technologies and more particularly to methods and systems of retrieving Ajax web page content.

Asynchronous JavaScript and XML Ajax is a web page development technology for creating interactive web page applications. For a conventional web page if a portion of the web page content has been updated a user can see the updated content only after the entire web page is refreshed. With an Ajax web page however a user can obtain the updated portion of the content without refreshing the entire web page. From the perspective of a network device this avoids repeatedly transmitting unaltered information and thus saves network bandwidth and reduces server workload. From a user s perspective waiting times during web page browsing can be effectively reduced thus improving user experience.

A search engine is a system that can collect organize and process Internet information with the capability of providing search services to users. Currently the search engine has become one of the indispensible auxiliary tools of Internet surfing experience for users. A web crawler being an important component of the search engine can automatically retrieve web page content and provide real time updated data to the search engine. Though conventional web pages can be supported existing web crawlers fail to effectively retrieve contents that are generated dynamically by Ajax on Ajax web pages. As a result dynamic contents on Ajax web pages cannot be collected by the search engine leading to a failure of the search engine to provide a complete content search service to the user.

The present disclosure provides a method and a system of retrieving Ajax web page content and to provide a solution for the failure of a search engine to collect dynamic content in an Ajax web page. A technical scheme is described as follows.

analyzing the JavaScript information to determine functions that include Ajax calls in the web page codes and

a script analyzing unit used for analyzing the JavaScript information to determine functions that include Ajax calls in the web page codes and

a web page content acquisition unit used for triggering the functions that include the Ajax calls to obtain web page content.

Through analyzing JavaScript information in web page codes the above technical scheme obtains functions that include Ajax calls in the web page codes and further triggers the functions to obtain web page content generated thereby thus achieving retrieval of dynamic content in an Ajax web page. Using the above technical scheme a search engine can collect more complete web page contents and hence provide a better search service to users.

In order to allow someone skilled in the art to understand the technical scheme provided in the present disclosure implementation methods in the present disclosure are described below in further details using accompanying figures.

This block is similar to the working mechanism of a conventional web crawler. Through an URL i.e. Uniform Resource Locator address information of web page codes corresponding to the address is read from the network.

Upon obtaining the information of web page codes JavaScript information therein is retrieved first. Use HTML i.e. Hyper Text Mark up Language codes as an example. Generally the following two approaches may be used to add JavaScript information into HTML codes 

Specifically with respect to the first approach the JavaScript codes can be placed between and a tag pair in the HTML codes. A common format is shown as follows 

The portion within the tag pair in the above format corresponds to JavaScript codes. Multiple JavaScript sentences may be included within the tag pair. The tag may appear in part of the HTML codes or part of the HTML codes.

With respect to the second approach the JavaScript codes are placed in an external file. This external file is then referenced through a src property of the tag in the HTML codes. A common format is shown below 

Values of the src property define a storage path and a filename of a JavaScript file. The storage path may be an absolute path or a relative path. test.js in the above format refers to the JavaScript filename being referenced while js refers to the storage path of that file. A JavaScript file generally uses .js as its extension name and includes mere JavaScript codes having no tag or other HTML tags.

Based on the above two approaches the JavaScript information in the HTML codes can be retrieved by checking the tag in the web page codes. As shown in a method of retrieving JavaScript information of web page codes may include the following procedures.

Sdetermines the type of JavaScript information located after the JavaScript tag. If the type corresponds to JavaScript codes Sis executed. If the type corresponds to JavaScript files Sis executed.

Sretrieves the JavaScript codes within the JavaScript tag s pair. Sretrieves storage paths and filenames of the JavaScript files.

Upon carrying out the above procedures for all nodes of tags in a HTML file code a certain number of JavaScript codes and or JavaScript files and respective storage paths are obtained. All the retrieved JavaScript codes may be stored in a temporary .js file e.g. temp.js . With respect to the JavaScript files analyzing all the codes of the JavaScript files is not required in the technical scheme of the present disclosure. Only the retrieved JavaScript filenames and respective storage paths may be stored at this block.

S analyzes the JavaScript information to determine functions that include Ajax calls in the web page codes.

Generally two types of JavaScript files are referenced in web page codes. One type refers to JavaScript framework documents. This type of file generally has a fixed filename prototype.js for example. Another type refers to non JavaScript framework documents. Within web page codes functions that include Ajax calls are defined in the non JavaScript framework document. As such contents of the JavaScript framework document may not need to be further analyzed. However property values corresponding to its framework type can be found based on its filename. Moreover functions that include Ajax calls and are defined in the non JavaScript framework document may be found using these property values. Furthermore functions that include Ajax calls in the web page codes may then be found. Specific procedures are shown as follows.

According to the above method determination is made as to whether the JavaScript file is a framework document or a non framework document. If determined to be a framework document corresponding property values are obtained.

Sdetermines functions which include Ajax calls and are defined in a non JavaScript framework document based on the Ajax property values.

In a JavaScript file all functions that include Ajax calls must include a specific piece of code which are called Ajax property values. Therefore whether a function includes an Ajax call can be determined based on whether the function includes these property values.

Ajax property values may be categorized into two types. Apart from the aforementioned property values that correspond to various types of JavaScript framework other property values exist in a situation when Ajax is called without using any type of JavaScript framework. These latter property values may be stored in advance in a database file. By matching codes of functions in a non JavaScript framework document with these property values functions that include Ajax calls can be determined

An assumption is made that functions used in the web page code constitute collection A and functions that have been determined at Sto include Ajax calls constitute collection B. The intersection of A and B corresponds to the required functions that include Ajax calls in the web page codes. A function that is not called in the web page i.e. a function that belongs to collection B but does not belong to collection A may not need to undergo further processing.

It should be noted that Smay be skipped if the JavaScript information obtained at S includes only JavaScript codes without JavaScript. Furthermore the temporary file temp.js which is used to store the JavaScript codes as described above may be processed as a non framework document here.

Upon determining which function includes Ajax calls in the web page code web page content that is generated dynamically by Ajax can be obtained through triggering these functions.

A number of functions that include Ajax calls are triggered by user operations e.g. by mouse clicking or selection. These operations may be realized by simulating operations of a browser. Specifically API i.e. Application Programming Interface provided by certain Web automated testing tools may be used to simulate relevant operations performed by a user in a browser. For example through the above procedures of S S a function getinfo on http www.test.com may be found to include an Ajax call with the function being triggered by mouse clicking. Therefore the following method may be used to simulate triggering of this function 

Upon simulating mouse clicking the function is triggered and the content that is dynamically generated by this function can be obtained correspondingly.

Through analyzing JavaScript information in web page codes the above technical scheme obtains functions that include Ajax calls in the web page codes and further triggers the function to obtain web page content generated thereby thus achieving retrieval of dynamic content in an Ajax web page. Using the above technical scheme a search engine can collect more complete web page contents and hence provide a better search service to users.

The method of retrieving Ajax web page content in accordance with the present disclosure is described below using a specific exemplary embodiment. Details of S S can be found in corresponding textual descriptions of S S.

It should be noted that the real codes provided in this exemplary embodiment are only meant for the purpose of illustrating the disclosed technical scheme and should be not construed as a limitation of the technical scheme.

According to the description at S the above codes are found to have no JavaScript codes directly embedded. However JavaScript files i.e. the two files prototype.js and ajax.js located within part are referenced. Information such as paths and filenames of these two files may be stored.

S analyzes the JavaScript information to determine functions that include Ajax calls in the web page codes.

Smay determine that prototype.js is a framework document and ajax.js is a non framework document based on the filenames of these two JavaScript files retrieved at S.

Based on the types of the two JavaScript files being referenced Smay know that two relevant Ajax property values possibly exist in the web page if an Ajax call exists. The first type is an Ajax calling method provided in the prototype framework with its property value as new Ajax.Request .

Another type corresponds to a situation when no JavaScript framework is used. Respective property value is 

The non framework document ajax.js is then further analyzed. Assume contents of the codes of ajax.js be the following 

Four functions are found to be defined in ajax.js and are getInfo getDate getDateTime and sameToBilling respectively. Moreover property values new ActiveXObject Microsoft.XMLHTTP and new Ajax.Request appear in the getInfo function and the sameToBilling function respectively. As a result getInfo and sameToBilling can be determined to be functions that include Ajax calls.

Smay determine that getInfo is a function that includes an Ajax call in the web page codes based on the intersection of Collection A of functions that are used in the web page codes and Collection B of functions that include Ajax calls in the referenced JavaScript file . On the other hand the sameToBilling function may not be further processed because the sameToBilling function was not called in the web page.

getInfo is triggered by simulating the onclick i.e. mouse clicking operation to obtain web page content generated thereby.

As illustrated in the above exemplary embodiment the technical scheme provided in this disclosure determines which function that is defined in a referenced file includes an Ajax call by analyzing web page codes and on Ajax property values. Within the scope thereof functions that are actually called in associated web page are found. Moreover web page content is obtained by simulating execution of these functions thus avoiding execution of a function that is unrelated to the web page content. As a result efficiency of retrieving dynamic web page content is improved.

Corresponding to the above exemplary method the exemplary embodiments of the present disclosure further provide a system of retrieving Ajax web page content. As shown in the system includes 

a script analyzing unit used for analyzing the JavaScript information to determine functions that include Ajax calls in the web page codes and

a web page content acquisition unit used for triggering the functions that include the Ajax calls to obtain web page content.

a first retrieving sub unit which is used when the JavaScript information located after the JavaScript tag corresponds to JavaScript codes and retrieving the JavaScript codes and storing the retrieved codes into a JavaScript file 

a second retrieving sub unit which is used when the JavaScript information located after the JavaScript tag corresponds to JavaScript file and retrieving the storage path and the filename of the JavaScript file.

a first determining sub unit used for determining functions that include Ajax calls and are defined in the JavaScript file based on Ajax property values where the Ajax property values refer to code segments indicating an existence of an Ajax call in a function and

a second determining sub unit used for further determining functions that include Ajax calls in the web page codes from among the functions that have been determined by the first determining sub unit .

The Ajax property values may include property values corresponding to Ajax calls using a type of JavaScript framework and or property values corresponding to Ajax calls without using any type of JavaScript framework.

The first determining sub unit may be used for determining functions that contain Ajax calls and are defined in a non JavaScript framework document that is referenced in the web page.

The web page content acquisition unit may be used for triggering the functions that include the Ajax calls by simulating a user operation to obtain the web page content.

Because of its fundamental correspondence with the exemplary method the exemplary system has been described in a relatively simple manner. Details thereof can be referred to pertinent parts of the exemplary method. Descriptions of the above exemplary system are only meant for illustrative purpose. Units described as separate components therein may or may not be separate in a physical sense. Components illustrated in terms of units may or may not be physical units i.e. may be located in one place or may be distributed among multiple network units. Based on actual needs the goal of the exemplary embodiments may be achieved by selecting parts or all of the modules. A person of ordinary skills in the art can understand and implement the disclosed system without any innovative effect.

For the sake of description the above system was divided into various units which were separately described. The functions of various units may be implemented in one or more software and or hardware when implementing the disclosed system.

From the exemplary embodiments described above someone skilled in the art can clearly understand that the disclosed method and system may be implemented using software and universal hardware platforms. Based on this understanding the technical scheme of the present disclosure or portions contributing to existing technologies may be implemented in the form of software products which are stored in a storage media such as ROM RAM disk and drive. The software includes instructions for a computing device e.g. personal computer server or network device to execute the method described in various exemplary embodiments or a certain part of the exemplary embodiment of the current disclosure.

Above are only a few exemplary embodiments of the present disclosure. It is understood that a person of ordinary skills in the art can alter or modify the current disclosure in many different ways without departing from the spirit and the scope of this disclosure. These alterations and modifications should be considered to fall within the scope of the claims of the present disclosure and their equivalents.

