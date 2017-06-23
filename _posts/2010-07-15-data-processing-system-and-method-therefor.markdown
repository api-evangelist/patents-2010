---

title: Data processing system and method therefor
abstract: A data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing said data providing apparatus and said processing apparatus by a management apparatus. In the system, the management apparatus is configured to provide a key file in which is stored content key data and usage control policy data indicating a content of rights, including permission conditions of the content data. At least a part of said key file is encrypted. The data providing apparatus is configured to provide the content data encrypted by using the content key data stored in the key file. The data processing apparatus is configured to decrypt the key file to obtain the content key data from the key file and determine handling of the content data based on the usage control policy data stored in the key file.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08095578&OS=08095578&RS=08095578
owner: Sony Corporation
number: 08095578
owner_city: Tokyo
owner_country: JP
publication_date: 20100715
---
The present application is a continuation of U.S. application Ser. No. 09 856 276 filed Oct. 2 2001 the entirety of which is incorporated herein by reference to the extent permitted by law. U.S. application Ser. No. 09 856 276 is the Section 371 National Stage of PCT JP00 06308. This application claims the benefit of priority to PCT International Application No. PCT JP00 06308 filed Sep. 14 2000 Japanese Patent Application No. 11 309722 filed in the Japanese Patent Office on Sep. 17 1999 and Japanese Patent Application No. 11 309721 filed in the Japanese Patent Office on Sep. 17 1999.

The present invention relates to a data providing system providing content data and a method of same a data providing apparatus and a data processing apparatus.

There is a data providing system for distributing encrypted content data to data processing apparatuses of users concluding predetermined contracts and having the related data processing apparatuses decrypt and reproduce and record the content data.

As one of such data providing systems there is the conventional EMD electronic music distribution system for distributing music data.

In the EMD system shown in content providers and encrypt content data and and copyright information and by session key data obtained after mutual certification and supply them to a service provider on line or supply by off line. Here the copyright information and include for example SCMS serial copy management system information electronic watermark information requesting burying in the content data and information concerning the copyright requesting burying in a transmission protocol of the service provider .

The service provider decrypts the received content data and and copyright information and by using the session key data.

Then the service provider buries the copyright information and in the content data and decrypted or received off line to produce content data and . At this time the service provider changes predetermined frequency domains of for example the electronic watermark information among the copyright information and and buries them in the content data and and buries the SCMS information in a network protocol used when transmitting the related content data to the user.

Further the service provider encrypts the content data and by using content key data Kca Kcb and Kcc read out from a key database . Thereafter the service provider encrypts a secure container storing the encrypted content data and by the session key data obtained after the mutual certification and transmits the same to a CA conditional access module existing in a terminal of the user.

The CA module decrypts the secure container by using the session key data. Also the CA module receives the content key data Kca Kcb and Kcc from the key database of the service provider by using a charge function such as an electronic settlement and CA and decrypts them by using the session key data. By this in the terminal it becomes possible to decrypt the content data and by using the content key data Kca Kcb and Kcc.

At this time the CA module performs charge processing in units of content produces charge information in accordance with a result of this and encrypts this by the session key data and then transmits the same to a right clearing module of the service provider .

In this case the CA module collects items to be managed by the service provider concerning services provided by itself that is the contract update information and the monthly basic fee and other network rent of the users performs the charge processing in units of the content and ensure security of a physical layer of the network.

The service provider performs distributes profit among the service provider and the content providers and when receiving the charge information from the CA module .

At this time the profit is distributed from the service provider to the content providers and via for example the JASRAC Japanese Society for Rights of Authors Composers and Publishers . Also the profit of the content provider is distributed to copyright owner an artist a song writer and or composer of the related content data and their affiliated production companies by the JASRAC.

Also in the terminal when recording the content data and decrypted by using the content key data Kca Kcb and Kcc in a RAM type storage medium or the like copying is controlled by rewriting SCMS bits of the copyright information and . Namely on the user side copying is controlled based on the SCMS bits buried in the content data and to achieve protection of the copyright.

The SCMS prohibits copying of the content data over for example two generations. Copying of one generation can be carried out without restriction however so there is a problem of insufficient protection of the copyright owner.

Also in the EMD system the content data not encrypted by the service provider can be technically freely handled so interested parties of the content provider must monitor actions etc. of the service provider so there are problems in that the load of the related monitoring is large and at the same time there is a high possibility of improper loss of the profit of the content provider .

Also in the EMD system it is difficult to restrict acts of the terminal of the user authoring the content data distributed from the service provider and redistributing the same to another terminal etc. so there is the problem of the improper loss of the profit of the content provider .

The present invention was made in consideration with the problems of the related art mentioned above and has as an object thereof to provide a data providing system capable of adequately protecting the profit of right holders interested parties of the content provider and a method of the same.

Also another object of the present invention is to provide a data providing system capable of reducing the load of inspection for protecting the profit of the right holders of the content provider and a method of the same.

To solve the problems of the prior art mentioned above and achieve the above objects a data providing system of a first aspect of the present invention is preferably a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus provides the content data encrypted by using the content key data and the data processing apparatus decrypts the content key data and the usage control policy data stored in the key file and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the first aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related key file is sent to the data providing apparatus.

Then the content data encrypted by using the content key data is provided from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the key file are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a second aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus distributes a module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the second aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced.

Then the related produced key file is distributed from the management apparatus to the data providing apparatus.

Then the module storing the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus is distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

A data providing system of a third aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus distributes a module storing a content file containing content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the third aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is sent to the data providing apparatus.

Then the module storing the content file containing the content data encrypted by using the content key data and the key file received from the management apparatus is distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a fourth aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus individually distributes the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the fourth aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is sent to the data providing apparatus.

Then in the data providing apparatus the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus are distributed.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the content data stored in the distributed content file is determined based on the related decrypted usage control policy data.

Also a data providing system of a fifth aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data and distributes the related produced key file to the data processing apparatus the data providing apparatus distributes a content file storing the content data encrypted by using the content key data to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the fifth aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced.

The related produced key file is distributed from the management apparatus to the data processing apparatus.

Also the content file storing the content data encrypted by using the content key data is distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the content data stored in the distributed content file is determined based on the related decrypted usage control policy data.

Also a data providing system of a sixth aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus distributes a module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the sixth aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is sent to the data providing apparatus.

Then the module storing the content data encrypted by using the content key data and the key file received from the management apparatus is distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a seventh aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus individually distributes the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the seventh aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is sent to the data providing apparatus.

Then the content data encrypted by using the content key data and the key file received from the management apparatus are individually distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the distributed content data is determined based on the related decrypted usage control policy data.

Also a data providing system of an eighth aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating handling of the content data and distributes the related produced key file to the data processing apparatus the data processing apparatus distributes the content data encrypted by using the content key data to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the eighth aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is sent to the data processing apparatus.

Also the content data encrypted by using the content key data are distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the distributed content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a ninth aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces encrypted content key data and encrypted usage control policy data indicating handling of the content data the data providing apparatus individually distributes the content data encrypted by using the content key data the encrypted content key data received from the management apparatus and the encrypted usage control policy data to the data processing apparatus and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the ninth aspect of the present invention becomes as follows.

In the management apparatus the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data are produced and they are sent to the data providing apparatus.

Then the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus are individually distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the distributed content key data and the usage control policy data are decrypted and the handling of the content data stored in the distributed content file is determined based on the related decrypted usage control policy data.

Also a data providing system of a 10th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces encrypted content key data and encrypted usage control policy data indicating handling of the content data and distributes the same to the data processing apparatus the data providing apparatus distributes the content data encrypted by using the content key data to the data processing apparatus and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the distributed content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 10th aspect of the present invention becomes as follows.

In the management apparatus the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data are produced and they are sent to the data processing apparatus.

Also the content data encrypted by using the content key data are distributed from the data providing apparatus to the data processing apparatus.

Then in the data processing apparatus the distributed content key data and the usage control policy data are decrypted and the handling of the distributed content data is determined based on the related decrypted usage control policy data.

Also a data providing system of an 11th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a data processing apparatus and a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides the content data encrypted by using the content key data the data distribution apparatus distributes the provided content data to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 11th aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced.

Then the content data encrypted by using the content key data is provided from the data providing apparatus to the data distribution apparatus.

Then the provided content data is distributed from the data distribution apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the key file are decrypted and the handling of the distributed content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a 12th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a second module storing the provided content file and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 12th aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is sent to the data providing apparatus.

Then the first module storing the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus is provided from the data providing apparatus to the data distribution apparatus.

Then the second module storing the provided content file and the key file is distributed from the data distribution apparatus to the data processing apparatus.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed second module are decrypted and the handling of the content data stored in the distributed second module is determined based on the related decrypted usage control policy data.

Also a data providing system of a 13th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing a content file containing the content data encrypted by using the content key data and a key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a second module storing the provided content file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing system of a 14th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus individually distributes the distributed content file and key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 15th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the related produced key file to the data processing apparatus the data providing apparatus provides a content file storing the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 16th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a second module storing the provided content data and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing system of a 17th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus individually distributes the distributed content data and the key file to the data distribution apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of an 18th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the related produced key file to the data processing apparatus the data processing apparatus provides the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 19th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus provides encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data providing apparatus the data providing apparatus individually distributes the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus to the data distribution apparatus the data distribution apparatus individually distributes the distributed content data the encrypted content key data and the encrypted usage control policy data to the data distribution apparatus and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 20th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus provides encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data processing apparatus the data providing apparatus provides the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus and the data processing apparatus decrypts the distribute the content key data and the usage control policy data and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 21st aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file and the key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 22nd aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file to the data distribution apparatus provides the key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 23rd aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file provided from the data providing apparatus and the produced key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 24th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data provides the content file provided from the data providing apparatus to the data distribution apparatus and provides the produced key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 25th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file and a key file provided from the management apparatus in the database device the management apparatus produces the key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data providing apparatus the data distribution apparatus distributes the content file and key file obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 26th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces the key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data distribution apparatus the data distribution apparatus distributes the content file obtained from the database device and the key file provided from the data distribution apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 27th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces the key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data processing apparatus the data distribution apparatus distributes the content file obtained from the database device and the key file provided from the data distribution apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 28th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files and key files provided from corresponding management apparatuses in the database device the management apparatuses produce key files storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 29th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce key files storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 30th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce key files storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 31st aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files and key files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce the content files storing the related encrypted content data produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the produced content files and the produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 32nd aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce the content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the produced key files to corresponding data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatuses to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 33rd aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce the content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatuses to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a first aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides the content data encrypted by using the content key data and the data processing apparatus decrypts the content key data and the usage control policy data stored in the key file and determines the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a second aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the produced key file from the management apparatus to the data providing apparatus distributing a module storing a content file storing the content data encrypted by using the content key data and the key file distributed from the management apparatus from the data providing apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a third aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus distributing a module storing a content file containing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a fourth aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related key file from the management apparatus to the data providing apparatus individually distributing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus from the data providing apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a fifth aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related key file from the management apparatus to the data processing apparatus distributing a content file storing the content data encrypted by using the content key data from the data providing apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a sixth aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus distributing a module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a seventh aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus individually distributing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of an eighth aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file to the data processing apparatus in the data providing apparatus distributing the content data encrypted by using the content key data to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a ninth aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus individually distributing the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus to the data processing apparatus and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 10th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributing the same to the data processing apparatus in the data providing apparatus distributing the content data encrypted by using the content key data to the data processing apparatus and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of an 11th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a data processing apparatus and a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data providing the content data encrypted by using the content key data from the data providing apparatus to the data distribution apparatus in the data distribution apparatus distributing the provided content data to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 12th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file from the management apparatus to the data providing apparatus providing a first module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus from the data providing apparatus to the data distribution apparatus and distributing a second module storing the provided content file and the key file from the data distribution apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing method of a 13th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus providing a first module storing a content file containing the content data encrypted by using the content key data and a key file received from the management apparatus to the data distribution apparatus in the data distribution apparatus distributing a second module storing the provided content file to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing method of a 14th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the produced key file from the management apparatus to the data providing apparatus individually distributing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus from the data providing apparatus to the data distribution apparatus individually distributing the distributed content file and the key file from the data distribution apparatus to the data distribution apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 15th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file from the management apparatus to the data processing apparatus providing a content file storing the content data encrypted by using the content key data from the data providing apparatus to the data distribution apparatus and distributing the provided content file from the data distribution apparatus to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 16th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus providing a first module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus in the data distribution apparatus distributing a second module storing the provided content data and the key file to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing method of a 17th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus individually distributing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus in the data distribution apparatus individually distributing the distributed content data and the key file to the data distribution apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of an 18th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributing the related produced key file to the data processing apparatus in the data providing apparatus providing the content data encrypted by using the content key data to the data distribution apparatus in the data distribution apparatus distributing the provided content data to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 19th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus providing encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data providing apparatus in the data providing apparatus individually distributing the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data which are received from the management apparatus to the data distribution apparatus in the data distribution apparatus individually distributing the distributed content data the encrypted content key data and the encrypted usage control policy data to the data distribution apparatus and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 20th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus distributing encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data processing apparatus in the data providing apparatus distributing the content data encrypted by using the content key data to the data distribution apparatus in the data distribution apparatus distributing the provided content data to the data processing apparatus and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 21st aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file and the key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 22nd aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file to the data distribution apparatus and provides the key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 23rd aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data provides the content file provided from the data providing apparatus and the produced key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 24th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data provides the content file provided from the data providing apparatus to the data distribution apparatus and provides the produced key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 25th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file and a key file provided from the management apparatus in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data providing apparatus the data distribution apparatus distributes the content file and key file obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 26th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data distribution apparatus the data distribution apparatus distributes the content file obtained from the database device and the key file provided from the data distribution apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 27th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data processing apparatus the data distribution apparatus distributes the content file obtained from the database device and the key file provided from the data distribution apparatus to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 28th aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files and key files provided from corresponding management apparatuses in the database device the management apparatuses produce the key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 29th aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce the key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatuses to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 30th aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce the key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 31st aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files and key files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the produced content files and the produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 32nd aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the related produced key files to corresponding data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and key files provided from the management apparatuses to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 33rd aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 34th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus wherein the data providing apparatus distributes a module storing the content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data processing apparatus by using a predetermined communication protocol in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 34th aspect of the present invention becomes as follows.

The module storing the content data encrypted by using the content key data the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is distributed from the data providing apparatus to the data processing apparatus.

At this time the related module is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

In this way by storing the usage control policy data indicating the handling of the related content data in the module storing the content data in the data processing apparatus it becomes possible to handle use the content data based on the usage control policy data produced by the interested parties of the data providing apparatus.

Also the module is distributed from the data providing apparatus to the data processing apparatus in the format not depending upon a predetermined communication protocol so a compression method encryption method etc. of the content data stored in the module can be freely determined by the data providing apparatus.

Also in the data providing system of the 34th aspect of the present invention preferably the module further storing signature data for verifying a legitimacy of a producer and a transmitter of at least one data among the content data the content key data and the usage control policy data is distributed to the data processing apparatus.

Also in the data providing system of the 34th aspect of the present invention preferably the data providing apparatus distributes the module further storing at least one data between data for verifying if the related data is not tampered with and signature data for verifying if the related data was normally certified by a predetermined manager for at least one data among the content data the content key data and the usage control policy data to the data processing apparatus.

Also in the data providing system of the 34th aspect of the present invention preferably the data processing apparatus determines a purchase form of the content data based on the usage control policy data and where the content data is transferred to another data processing apparatus the signature data indicating the legitimacy of the purchaser of the related content data and the signature data indicating the legitimacy of the transmitter of the related content data are made different.

A data providing system of 35th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus distributes a module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 35th aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced.

Then the related produced key file is distributed from the management apparatus to the data providing apparatus.

Then the module storing the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Also in the data providing system of the 35th aspect of the present invention preferably the management apparatus produces signature data for verifying the legitimacy of the producer of the key file and produces the key file further storing the related signature data.

Also in the data providing system of the 35th aspect of the present invention preferably the data providing apparatus produces the content key data and the usage control policy data and transmits the same to the management apparatus and the management apparatus produces the key file based on the received content key data and usage control policy data and registers the related produced key file.

Also a data providing apparatus of the present invention is a data providing apparatus which is managed by a management apparatus and distributes content data to a data processing apparatus receiving a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data from the management apparatus and distributing a module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus.

Also a data processing apparatus of the present invention is a data processing apparatus managed by a management apparatus and utilizing content data receiving a module containing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and a content file storing the content data encrypted by using the content key data determining at least one between a purchase form and an usage form of the content data based on the usage control policy data and transmitting a log data indicating the log of the determined at least one of the related purchase form and usage form to the management apparatus.

Also a data providing system of a 36th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus distributes a module storing a content file containing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 36th aspect of the present invention becomes as follows.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related key file is sent to the data providing apparatus.

Then the module storing the content file containing the content data encrypted by using the content key data and the key file received from the management apparatus is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a 37th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

The mode of operation of the data providing system of the 37th aspect of the present invention becomes as follows. In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related key file is sent to the data providing apparatus.

Then in the data processing apparatus the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus are individually distributed to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the content data stored in the distributed content file is determined based on the related decrypted usage control policy data.

Also a data providing system of a 38th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the related produced key file to the data processing apparatus the data providing apparatus distributes a content file storing the content data encrypted by using the content key data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 38th aspect of the present invention.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced.

The related produced key file is distributed from the management apparatus to the data processing apparatus.

Also the content file storing the content data encrypted by using the content key data is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the content data stored in the distributed content file is determined based on the related decrypted usage control policy data.

Also a data providing system of a 39th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus distributes a module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 39th aspect of the present invention.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related key file is sent to the data providing apparatus.

Then the module storing the content data encrypted by using the content key data and the key file received from the management apparatus is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a 40th aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 40th aspect of the present invention.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related key file is sent to the data providing apparatus.

Then the content data encrypted by using the content key data and the key file received from the management apparatus are individually distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the distributed content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a 41st aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the related produced key file to the data processing apparatus the data providing apparatus distributes the content data encrypted by using the content key data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 41st aspect of the present invention.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related produced key file is distributed to the data processing apparatus.

Also the content data encrypted by using the content key data is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed key file are decrypted and the handling of the distributed content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a 42nd aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 42nd aspect of the present invention.

In the management apparatus the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data are produced and are sent to the data providing apparatus.

Then the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus are individually distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the distributed content key data and the usage control policy data are decrypted and the handling of the content data stored in the distributed content file is determined based on the related decrypted usage control policy data.

Also a data providing system of a 43rd aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the same to the data processing apparatus the data providing apparatus distributes the content data encrypted by using the content key data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 43rd aspect of the present invention.

In the management apparatus the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data are produced and are distributed to the data processing apparatus.

Then the content data encrypted by using the content key data is distributed from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the distributed content key data and the usage control policy data are decrypted and the handling of the distribution the content data is determined based on the related decrypted usage control policy data.

Also a data providing system of a 44th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus and a data processing apparatus wherein the data providing apparatus provides a first module storing content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data distribution apparatus the data distribution apparatus distributes a second module storing the encrypted content data content key data and the usage control policy data stored in the provided first module to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 44th aspect of the present invention.

The first module storing the content data encrypted by using the content key data the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is provided from the data providing apparatus to the data distribution apparatus by for example using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Next the second module storing the encrypted content data content key data and the usage control policy data stored in the provided first module is distributed from the data distribution apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed second module are decrypted and the handling of the content data is determined based on the related decrypted usage control policy data.

In this way by storing the usage control policy data indicating the handling of the related content data in the first module and second module storing the content data in the data processing apparatus it becomes possible to have the data processing apparatus perform the handling usage of the content data based on the usage control policy data produced by the interested parties of the data providing apparatus.

Also the second module is distributed from the data distribution apparatus to the data processing apparatus in a format not depending upon on a predetermined communication protocol so the compression method and encryption method etc. of the content data stored in the second module can be freely determined by the data providing apparatus.

A data providing system of a 45th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a second module storing the provided content file and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Below an explanation will be made of the mode of operation of the data providing system of the 45th aspect of the present invention.

In the management apparatus the key file storing the encrypted content key data and the encrypted usage control policy data indicating the handling of the content data is produced and the related key file is sent to the data providing apparatus.

Then the first module storing the content file storing the content data encrypted by using the content key data and the key file received from the management apparatus is provided from the data providing apparatus to the data distribution apparatus.

Then the second module storing the provided content file and the key file is distributed from the data distribution apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or while being recorded on a storage medium.

Then in the data processing apparatus the content key data and the usage control policy data stored in the distributed second module are decrypted and the handling of the content data stored in the distributed second module is determined based on the related decrypted usage control policy data.

A data providing system of a 46th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing a content file containing the content data encrypted by using the content key data and a key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a second module storing the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing system of a 47th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a first data distribution apparatus and a second data distribution apparatus distributing the content data from the first data distribution apparatus and the second data distribution apparatus to a data processing apparatus and managing the data providing apparatus the first data distribution apparatus the second data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the first data distribution apparatus and the second data distribution apparatus the first data distribution apparatus distributes a second module storing the provided content file and the key file to the data processing apparatus the second data distribution apparatus distributes a third module storing the provided content file and the key file to the data processing apparatus and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and the third module and determines the handling of the content data based on the related decrypted usage control policy data.

Also a data providing system of a 48th aspect of the present invention is a data providing system for providing first content data from a first data providing apparatus to a data distribution apparatus providing second content data from a second data providing apparatus to the data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the first data providing apparatus the second data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a first key file storing an encrypted first content key data and an encrypted first usage control policy data indicating the handling of the first content data and a second key file storing an encrypted second content key data and an encrypted second usage control policy data indicating the handling of the second content data the first data providing apparatus provides a first module storing a first content file storing the first content data encrypted by using the first content key data and the first key file received from the management apparatus to the data distribution apparatus the second data providing apparatus provides a second module storing a second content file storing the second content data encrypted by using the second content key data and the second key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a third module storing the provided first content file the first key file the second content file and the second key file to the data processing apparatus and the data processing apparatus decrypts the first content key data the second content key data the first usage control policy data and the second usage control policy data stored in the distributed third module determines the handling of the first content data based on the related decrypted first usage control policy data and determines the handling of the second content data based on the related decrypted second usage control policy data.

Also a data providing system of a 49th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus individually distributes the distributed content file and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 50th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the related produced key file to the data processing apparatus the data providing apparatus distributes a content file storing the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 51st aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus provides a first module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes a second module storing the provided content data and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing system of a 52nd aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data the data providing apparatus individually distributes the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus the data distribution apparatus individually distributes the distributed content data and the key file to the data distribution apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 53rd aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus wherein the management apparatus produces a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributes the related produced key file to the data processing apparatus the data providing apparatus distributes the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributes the provided content data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 54th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus provides encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data providing apparatus the data providing apparatus individually distributes the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus to the data distribution apparatus the data distribution apparatus distributes the distributed content data the encrypted content key data and the encrypted usage control policy data to the data distribution apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 55th aspect of the present invention is a data providing system for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus wherein the management apparatus provides encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data processing apparatus the data providing apparatus provides the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributes the distributed provided content data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the distributed content key data and the usage control policy data and determines the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing system of a 56th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file and the key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also in the data providing system of the 56th aspect of the present invention preferably the management apparatus produces a first module storing the content file and the key file and provides the related first module to the data distribution apparatus and the data distribution apparatus produces a second module storing the content file and the key file stored in the first module and distributes the related second module to the data processing apparatus.

Also in the data providing system of the 56th aspect of the present invention preferably the management apparatus has at least one database among a database for storing and managing the content file a database for storing and managing the key file and a database for storing and managing the usage control policy data and centrally manages at least one among the content file the key file and the usage control policy data by using a content identifier uniquely allocated to the content data.

Also a data providing system of a 57th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file to the data distribution apparatus and provides the key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 58th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file provided from the data providing apparatus and the produced key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 59th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data provides the content file provided from the data providing apparatus to the data distribution apparatus and provides the produced key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 60th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file and a key file provided from the management apparatus in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data providing apparatus the data distribution apparatus distributes the content file and key file obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 61st aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data providing apparatus the data distribution apparatus distributes the content file obtained from the database device and the key file provided from the data distribution apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 62nd aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data processing apparatus the data distribution apparatus distributes the content file obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing system of a 63rd aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files and key files provided from corresponding management apparatuses in the database device the management apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 64th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatuses to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 65th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 66th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files and key files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the produced content files and the produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 67th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the related produced key files provided from the management apparatuses to corresponding data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and key files provided from the management apparatuses to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing system of a 68th aspect of the present invention is a data providing system having a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the provided content files based on the related decrypted usage control policy data.

Also a data providing system of a 69th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus and a data processing apparatus wherein the data providing apparatus provides a first module storing content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data distribution apparatus performs charge processing in units of the content data based on log data received from the data processing apparatus and performs a profit distribution processing for distributing the profit paid by interested parties of the data processing apparatus to interested parties of the related data providing apparatus and interested parties of the data distribution apparatus the data distribution apparatus distributes a second module storing the encrypted content data content key data and usage control policy data stored in the provided first module to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the relate a communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module determines the handling of the content data based on the related decrypted usage control policy data produces the log data for the handling of the related content data and sends the related log data to the data providing apparatus.

Also a data providing system of a 70th aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus and a management apparatus wherein the data providing apparatus provides content data the data distribution apparatus distributes the content file provided from the data providing apparatus or a content file in accordance with the content data provided by the data providing apparatus provided from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the usage control policy data stored in a key file received from the data distribution apparatus or the management apparatus determines the handling of the content data stored in the content file received from the data distribution apparatus or the management apparatus based on the related decrypted usage control policy data and further distributes the content file and key file received from the data distribution apparatus or the management apparatus to the other data processing apparatus.

Also a data providing method of a 34th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus comprising the steps of distributing a module storing the content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a 35h aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the produced key file from the management apparatus to the data providing apparatus and distributing a module storing a content file storing the content data encrypted by using the content key data and the key file distributed from the management apparatus from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a 36th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus distributing a module storing a content file containing the content data encrypted by using the content key data and a key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a 37th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file from the management apparatus to the data providing apparatus and individually distributing a content file storing the content data encrypted by using the content key data and the key file distributed from the management apparatus from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 38th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file from the management apparatus to the data processing apparatus and distributing a content file storing the content data encrypted by using the content key data from the data providing apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 39th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus distributing a module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a 40th aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus individually distributing the content data encrypted by using the content key data and the key file received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 41st aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributing the related produced key file to the data processing apparatus in the data providing apparatus distributing the content data encrypted by using the content key data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 42nd aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus individually distributing the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 43rd aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributing the same to the data processing apparatus in the data providing apparatus distributing the content data encrypted by using the content key data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 44th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus and a data processing apparatus comprising the steps of providing a first module storing content data encrypted by using content key data encrypted the content key data and encrypted usage control policy data indicating the handling of the content data from the data providing apparatus to the data distribution apparatus distributing a second module storing the encrypted content data content key data and the usage control policy data stored in the provided the first module from the data distribution apparatus to the data processing apparatus by using the content key data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data based on the related decrypted usage control policy data.

Also a data providing method of a 45th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file from the management apparatus to the data providing apparatus providing a first module storing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus from the data providing apparatus to the data distribution apparatus and distributing a second module storing the provided content file and the key file from the data distribution apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing method of a 46th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus providing a first module storing a content file containing the content data encrypted by using the content key data and a key file received from the management apparatus to the data distribution apparatus in the data distribution apparatus distributing a second module storing the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing method of a 47th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the produced key file from the management apparatus to the data providing apparatus individually providing a content file storing the content data encrypted by using the content key data and the key file received from the management apparatus from the data providing apparatus to the data distribution apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and individually distributing the distributed content file and the key file from the data distribution apparatus to the data distribution apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 48th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data distributing the related produced key file from the management apparatus to the data processing apparatus providing a content file storing the content data encrypted by using the content key data from the data providing apparatus to the data distribution apparatus distributing the provided content file from the data distribution apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 49th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus providing a first module storing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus in the data distribution apparatus distributing a second module storing the provided content data and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed second module and determining the handling of the content data stored in the distributed second module based on the related decrypted usage control policy data.

Also a data providing method of a 50th aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data in the data providing apparatus individually providing the content data encrypted by using the content key data and the key file received from the management apparatus to the data distribution apparatus in the data distribution apparatus individually distributing the distributed content data and the key file to the data distribution apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 51st aspect of the present invention is a data providing method for distributing content data from a data providing apparatus to a data processing apparatus and managing the data providing apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus preparing a key file storing encrypted content key data and encrypted usage control policy data indicating the handling of the content data and distributing the related produced key file to the data processing apparatus in the data providing apparatus providing the content data encrypted by using the content key data to the data distribution apparatus in the data distribution apparatus distributing the provided content data to the data processing apparatus and in the data processing apparatus decrypting the content key data and the usage control policy data stored in the distributed key file and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 52nd aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus providing encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data providing apparatus in the data providing apparatus individually distributing the content data encrypted by using the content key data and the encrypted content key data and the encrypted usage control policy data received from the management apparatus to the data distribution apparatus in the data distribution apparatus individually distributing the distributed content data the encrypted content key data and the encrypted usage control policy data to the data distribution apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or recording the same on a storage medium and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 53rd aspect of the present invention is a data providing method for providing content data from a data providing apparatus to a data distribution apparatus distributing the content data from the data distribution apparatus to a data processing apparatus and managing the data providing apparatus the data distribution apparatus and the data processing apparatus by a management apparatus comprising the steps of in the management apparatus distributing encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data processing apparatus in the data providing apparatus providing the content data encrypted by using the content key data to the data distribution apparatus the data distribution apparatus distributing the provided content data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol by recording the same on a storage medium and in the data processing apparatus decrypting the distributed content key data and the usage control policy data and determining the handling of the distributed content data based on the related decrypted usage control policy data.

Also a data providing method of a 54th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file and the key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 55th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides master source data of content to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus encrypts the provided master source data by using content key data to produce content data produces a content file storing the related content data produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file to the data distribution apparatus and provides the key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 56th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the content file provided from the data providing apparatus and the produced key file to the data distribution apparatus the data distribution apparatus distributes the provided content file and the key file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 57th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus and a data processing apparatus wherein the data providing apparatus provides a content file storing encrypted content data using content key data to the management apparatus the management apparatus manages the data providing apparatus the data distribution apparatus and the data processing apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data provides the content file provided from the data providing apparatus to the data distribution apparatus and provides the produced key file to the data processing apparatus the data distribution apparatus distributes the provided content file to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 58th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file and a key file provided from the management apparatus in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data providing apparatus the data distribution apparatus distributes the content file and key file obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 59th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data distribution apparatus the data distribution apparatus distributes the content file obtained from the database device and the key file provided from the data distribution apparatus to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 60th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a management apparatus a database device and a data processing apparatus wherein the data providing apparatus encrypts content data by using content key data produces a content file storing the related encrypted content data and stores the related produced content file in the database device the management apparatus produces a key file storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data and provides the related produced key file to the data processing apparatus the data distribution apparatus distributes the content file obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key file and determines the handling of the content data stored in the distributed content file based on the related decrypted usage control policy data.

Also a data providing method of a 61st aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files and key files provided from corresponding management apparatuses in the database device the management apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 62nd aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatuses to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 63rd aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses encrypt content data by using content key data produce content files storing the related encrypted content data and store the related produced content files in the database device the management apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 64th aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files and key files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and send the produced content files and the produced key files to corresponding data providing apparatuses the data distribution apparatus distributes the content files and key files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 65th aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses send the related produced key files to corresponding data distribution apparatus the data distribution apparatus distributes the content files obtained from the database device and the key files provided from the management apparatuses to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 66th aspect of the present invention is a data providing method using a plurality of data providing apparatuses a data distribution apparatus a plurality of management apparatuses a database device and a data processing apparatus wherein the data providing apparatuses provide master sources of content data to corresponding management apparatuses and store content files received from the related management apparatuses in the database the management apparatuses encrypt the master sources received from corresponding data providing apparatuses by using content key data produce content files storing the related encrypted content data send the related produced content files to the data providing apparatuses produce key files storing the encrypted content key data and encrypted usage control policy data indicating the handling of the content data for the content data provided by corresponding data providing apparatuses and provide the related produced key files to the data processing apparatus the data distribution apparatus distributes the content files obtained from the database device to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the provided key files and determines the handling of the content data stored in the distributed content files based on the related decrypted usage control policy data.

Also a data providing method of a 67th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus and a data processing apparatus wherein the data providing apparatus provides a first module storing content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data distribution apparatus performs charge processing in units of the content data based on log data received from the data processing apparatus performs profit distribution processing for distributing the profit paid by interested parties of the data processing apparatus to interested parties of the related data providing apparatus and interested parties of the data distribution apparatus the data distribution apparatus distributes a second module storing the encrypted content data content key data and usage control policy data stored in the provided first module to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module determines the handling of the content data based on the related decrypted usage control policy data produces the log data for the handling of the related content data and sends the related log data to the data providing apparatus.

Also a data providing method of a 68th aspect of the present invention is a data providing method using a data providing apparatus a data distribution apparatus a data processing apparatus and a management apparatus wherein the data providing apparatus provides content data the data distribution apparatus distributes the content file provided from the data providing apparatus or a content file in accordance with the content data provided by the data providing apparatus received from the management apparatus to the data processing apparatus and the data processing apparatus decrypts the usage control policy data stored in the key file received from the data distribution apparatus or the management apparatus determines the handling of the content data stored in the content file received from the data distribution apparatus or the management apparatus based on the related decrypted usage control policy data and further distributes the content file and key file received from the data distribution apparatus or the management apparatus to the other data processing apparatus.

Also a data providing system of a 71st aspect of the present invention is a data providing system for distributing content data from a data providing apparatus to a data processing apparatus wherein the data providing apparatus distributes a module storing content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data in a format not depending upon at least one among existence of a compression of the content data a compression method a method of the encryption and parameters of a signal giving the content data to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed module and determines the handling of the content data based on the related decrypted usage control policy data.

Also a data providing system of a 72nd aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus and a data processing apparatus wherein the data providing apparatus distributes a first module storing content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data in a format not depending upon at least one among existence of compression of the content data a compression method a method of the encryption and parameters of a signal giving the content data to the data distribution apparatus the data distribution apparatus distributes a second module storing the encrypted content data content key data and the usage control policy data stored in the provided first module to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol or by recording the same on a storage medium and the data processing apparatus decrypts the content key data and the usage control policy data stored in the distributed second module and determines the handling of the content data based on the related decrypted usage control policy data.

Also a data providing system of a 73rd aspect of the present invention is a data providing system having a data providing apparatus a data distribution apparatus and a data processing apparatus wherein the data providing apparatus distributes a first module storing content data encrypted by using content key data the encrypted content key data and encrypted usage control policy data indicating the handling of the content data to the data distribution apparatus the data distribution apparatus encrypts a plurality of second modules storing the encrypted content data content key data and the usage control policy data stored in the provided first module by using a common key obtained by mutual certification with the data processing apparatus and then distributes the same to the data processing apparatus by using a predetermined communication protocol but in a format not depending upon the related communication protocol and the data processing apparatus has a first processing circuit for decrypting the distributed plurality of second modules by using the common key selecting a single or a plurality of second modules from among the related decrypted plurality of second modules and performing charge processing with respect to a distribution service of the second modules and a tamper resistant second processing circuit receiving the selected the second modules decrypting the content key data and the usage control policy data stored in the related second modules and determining the handling of the content data based on the related decrypted usage control policy data.

Below an explanation will be given of an EMD electronic music distribution system according to the present embodiment.

In the present embodiment the content data distributed to the user means digital data with the information per se having value and includes image data audio data programs software etc. but an explanation will be given below by taking as an example music data.

As shown in the EMD system has a content provider an EMD service center clearinghouse hereinafter also described as an ESC and a user home network .

Here the content provider EMD service center and SAMs to correspond to the data providing apparatus management device and the data processing apparatuses according to claim claim claim and claim .

In the EMD system the content provider sends the content key data Kc used when encrypting the content data C of the content to be provided by itself usage control policy UCP certificate of title data indicating the content of rights such as usage permission conditions of the content data C and electronic watermark information management data indicating the content and buried location of the electronic watermark information to the EMD service center serving as the reputable authority manager.

The EMD service center registers certifies or authorizes the content key data Kc usage control policy data and the electronic watermark information key data received from the content provider .

Also the EMD service center produces a key file KF with the content key data Kc encrypted by the distribution use key data KDto KDof a corresponding period the usage control policy data and its own signature data stored therein and sends this to the content provider .

Here the signature data is used for verifying existence of tampering with the key file KF the legitimacy of the author of the key file KF and the fact that the key file KF was normally registered in the EMD service center .

Also the content provider encrypts the content data C by the content key data Kc and distributes a secure container module of the present invention storing the related produced content file CF key file KF received from the EMD service center its own signature data etc. therein to the user home network by using a network such as the Internet digital broadcast or package media such as storage media.

Here the signature data stored in the secure container is used for verifying the existence of tampering with the corresponding data and the legitimacy of the author and transmitter of the related data.

The AV apparatuses to include built in SAMs to . The SAMs to are connected to each other via a bus for example an IEEE Institute of Electrical and Electronics Engineers 1394 serial interface bus.

The SAMs to decrypt the secure container received by the network apparatus via the network or the like from the content provider on line and or the secure container received at the AV apparatuses to from the content provider via storage media off line by using the distribution use key data KDto KDof the corresponding period then perform the verification of the signature data.

The secure container supplied to the SAMs to becomes the object of the reproduction recording to a storage medium etc. after the purchase and or usage form is determined by an operation of the users in the network apparatus and the AV apparatuses to .

The SAMs to record the log of the purchase and or usage form of the secure container as usage log data and at the same time produce usage control status data indicating the purchase form.

The usage log data is transmitted from the user home network to the EMD service center in response to for example a request from the EMD service center .

The usage control status data is transmitted from the user home network to the EMD service center whenever for example the purchase form is determined.

The EMD service center determines calculates a charge content based on the usage log data and performs settlement at a settlement manager such as a bank via a payment gateway . By this the money paid to the settlement manager by the user of the user home network is paid to the content provider by the settlement processing by the EMD service center .

Also the EMD service center transmits the settlement report data to the content provider at every predetermined period.

In the present embodiment the EMD service center has a certificate authority function a key data management function and a right clearing profit distribution function.

Namely the EMD service center functions as a second certificate authority with respect to a route certificate authority as the highest authority manager located at a neutral position located in the lower layer of the route certificate authority and certifies the legitimacy of the related public key data by attaching a signature by secret key data of the EMD service center to the certificate data of the public key data used for the verification processing of the signature data in the content provider and SAMs to . Also as mentioned above the registration and authorization of the usage control policy data of the content provider by the EMD service center is one of the certificate authority functions of the EMD service center .

Also the EMD service center has a key data management function for managing the key data for example the distribution use key data KDto KD.

Also the EMD service center has a right clearing profit distribution function of performing settlement for a purchase and or usage of the content by the user based on the suggested retailer price SRP described in the authorized usage control policy data and the usage log data input from the SAMs to and distributing money paid by the user to the content provider .

As shown in in the secure container the content file CF produced by the content provider and the key file KF produced by the EMD service center are stored.

In the content file CF header data containing the header portion and the content ID the encrypted content data C using the content key data Kc and the signature data using a secret key data Kof the content provider for them are stored.

In the key file KF the header data containing the header portion and the content ID the content key data Kc and the usage control policy data encrypted by the distribution use key data KDto KDand the signature data by secret key data Kof the EMD service center for them are stored.

Also in the flow of the data related to the data transmitted and received between the content provider and the EMD service center is shown.

Note that in and the following drawings the flow of the data input and output to and from the signature data processing unit and the encryption and or decryption unit using session key data Kis omitted.

As shown in and the content provider has a content master source database an electronic watermark information addition unit a compression unit an encryption unit a random number generation unit an expansion unit a signature processing unit a secure container preparation unit a secure container database a key file database a storage unit database a mutual certification unit an encryption and or decryption unit a usage control policy data preparation unit an audial check unit a SAM management unit an EMD service center management unit and a content ID generation unit .

The content provider registers for example its own generated public key data ID and its own bank account number account number for settlement in the EMD service center off line before communicating with the EMD service center and acquires its own identifier identification number CP ID. Also the content provider receives the public key data of the EMD service center and the public key data of the route certificate authority from the EMD service center .

The content master source database stores the content data as the master source of the content to be provided to the user home network and outputs content data S to be provided to the electronic watermark information addition unit .

The electronic watermark information addition unit buries a source watermark Ws a copy control watermark Wc a user watermark Wu a link watermark WL etc. in the content data S to produce content data S and outputs the content data S to the compression unit .

The source watermark Ws is information concerning the copyright such as the name of the copyright owner of the content data the ISRC code authoring date authoring apparatus ID identification data and destination of distribution of the content.

The copy control watermark Wc is information containing a copy prohibition bit for prevention of copying via an analog interface.

The user watermark Wu contains for example the identifier CP ID of the content provider for specifying the origin of distribution and the destination of distribution of the secure container and identifiers SAM IDto SAM IDof the SAMs to of the user home network .

By burying the link watermark WL in the content data C even in a case where the content data C is distributed by an analog broadcast for example a television or AM FM radio the EMD service center can introduce a content provider handling the related content data C to the user in response to a request from the user. Namely by detecting the link watermark WL buried in the content data C utilizing an electronic watermark information decoder at the receiving location of the related content data C and transmitting the content ID contained in the related detected link watermark WL to the EMD service center the EMD service center can introduce the content provider etc. handling the related content data C to the related user.

Concretely for example if the user pushes a predetermined button at a point of time when he thinks that the music being broadcast is good while listening to the radio in a car the electronic watermark information decoder built in the related radio detects the content ID contained in the link watermark WL buried in the related content data C a communication address etc. of the EMD service center registering the related content data C etc. and stores the related detected data in a media SAM carried in for example a memory stick or other semiconductor memory or an MD Mini Disc or other optical disc or other portable medium. Then he sets the related movable media in the network apparatus carrying a SAM connected to the network. Then after mutual certification by the related SAM and the EMD service center he transmits the personal information carried in the media SAM and the stored content ID etc. from the network apparatus to the EMD service center . Thereafter the network apparatus receives an introduction list etc. of the content provider etc. handling the related content data C from the EMD service center .

In addition for example when the EMD service center receives the content ID etc. from the user the information specifying the related user may be notified to the content provider providing the content data C corresponding to the related content ID. In this case the content provider receiving the related communication transmits the related content data C to the network apparatus of the user if the related user is a contracting subscriber or may transmit promotional information concerning itself to the network apparatus of the user if the related user is not a contracting subscriber.

Note that in the second embodiment mentioned later an EMD service center can introduce a service provider handling the related content data C to the user based on the link watermark WL.

Also in the present embodiment preferably the content and buried location of each electronic watermark information are defined as a watermark module WM and the watermark module WM is registered and managed in the EMD service center . The watermark module WM is used when for example the network apparatus and the AV apparatuses to in the user home network verify the legitimacy of the electronic watermark information.

For example in the user home network by deciding that the electronic watermark information is legitimate where both of the buried location of the electronic watermark information and the content of the buried electronic watermark information match based on the user watermark module managed by the EMD service center the burial of a false electronic watermark information can be detected with a high probability.

The compression unit compresses the content data S by an acoustic compression method for example ATRAC3 Adaptive Transform Acoustic Coding 3 trademark and outputs compressed content data S to the encryption unit .

In this case at the time of compression by the compression unit it is also possible to bury the electronic watermark information in the content data again. Concretely as shown in when the content data is expanded at the expansion unit to produce content data S and the content data S is reproduced at the audial check unit the influence exerted upon the quality of sound by the burial of the electronic watermark information is decided by for example a person actually listening to it. Where it does not satisfy a predetermined standard the electronic watermark information addition unit is instructed to perform the processing for burying the electronic watermark information again.

By this when employing an acoustic compression method accompanied by for example loss of data it is possible to adequately cope with the case where the buried electronic watermark information is lost due to the related compression. Further it is also possible to expand the compressed content data again and confirm whether or not the buried electronic watermark information can be correctly detected. In this case the feeling of the sound quality is also verified. Where there is a problem in the sound the burial of the electronic watermark information is adjusted. For example where the electronic watermark information is buried by using a masking effect the layer for burying the electronic watermark information is adjusted.

The encryption unit uses the content key data Kc as the common key encrypts the content data by a common key encryption method such as DES Data Encryption Standard or Triple DES to produce the content data C and outputs this to the secure container preparation unit .

Also the encryption unit encrypts an A V expansion use software Soft a meta data Meta and the watermark module WM by using the content key data Kc as the common key and then outputs them to the secure container preparation unit .

DES is the encryption method for processing 64 bits of plain text as one block by using a common key of 56 bits. The processing of DES is comprised of a portion for scrambling the plain text to convert the same to encrypted text data scrambling portion and a portion for creating the key magnification key data used in the data scrambling portion from the common key data key processing portion . All algorithms of the DES are public therefore here the basic processing of the data scrambling portion will be simply explained.

First 64 bits of the plain text are divided to Hof the upper significant 32 bits and Lof lower significant 32 bits. By receiving as input the magnification key data Kof 48 bits supplied from the key processing unit and the Lof the lower significant 32 bits the output of an F function scrambled Lof the lower significant 32 bits is calculated. The F function is comprised of two types of basic transforms of substitution of switching numerical values by a predetermined rule and transposition of switching bit locations by a predetermined rule. Next an exclusive OR of the Hof the upper significant 32 bits and the output of the F function is calculated and the result thereof is defined as L. Also Lis made H.

Then based on the Hof the upper significant 32 bits and the Lof the lower significant 32 bits the above processing is repeated 16 times. The obtained Hof the upper significant 32 bits and Lof the lower significant 32 bits are output as the encrypted text. The decryption is realized by inversely following the sequence by using the common key data used for the encryption.

The random number generation unit generates a random number of a predetermined number of bits and stores the related random number as the content key data Kc in the storage unit .

Note that it is also possible if the content key data Kc is produced from the information concerning a song provided by the content data. The content key data Kc is updated for example every predetermined time.

Also where a plurality of content providers exist it is also possible to use inherent content key data Kc from individual content providers or it is also possible to use the content key data Kc common to all content providers .

In the key file database as shown in the key file KF shown in received from the EMD service center via the EMD service center management unit is stored. The key file KF exists for every content data C. As will be mentioned later a link is designated with the corresponding content file CF by directory structure data DSD in the header of the content file CF.

In the key file KF as shown in and the header content key data Kc usage control policy data usage permission condition SAM program download containers SDCto SDC and signature data SIGare stored.

Here as the signature data using the secret key data Kof the content provider use can be also made of the signature data Kfor all data stored in the key file KF as shown in . Alternatively signature data for the data from the header to the information concerning the key file signature data for the content key data Kc and the usage control policy data and signature data for the SAM program download container SDC can be separately provided too as shown in .

In the header data as shown in a synchronization signal the content ID the signature data by the secret key data Kof the content provider for the content ID the directory structure data hyper link data the information concerning the key file KF the signature data by the secret key data Kof the content provider for the directory structure data etc. are contained.

Note that as the information to be contained in the header data various information can be considered and freely varied according to the situation. For example it is also possible if the information as shown in is contained in the header data.

Also in the content ID for example the information as shown in is contained. The content ID is produced in the EMD service center or the content provider . Where it is produced in the EMD service center the signature data by the secret key data Kof the EMD service center is added as shown in while where it is produced at the content provider the secret key data Kof the content provider is added.

The content ID is produced by for example the content ID generation unit as shown in and stored in the storage unit . Note that it is also possible if the content ID is produced by the EMD service center .

The directory structure data indicates correspondence among the content files CF in the secure container and correspondence between the content files CF and the key files KF.

For example where the content files CFto CFand the key files KFto KFcorresponding to them are stored in the secure container as shown in the links among the content files CFto CFand the links between the content files CFto CFand the key files KFto KFare established by the directory structure data.

The hyper link data indicates a hierarchy structure among the key files KF and the correspondence between the content files CF and the key files KF covering all files inside and outside the secure container .

Concretely as shown in the address information of the linked site for every content file CF and key file KF and the certificate value hash value thereof are stored in the secure container . The links are verified by comparing the hash value of one s own address information obtained by using the hash function H x and the certificate value of the other party.

Also in the usage control policy data as shown in the content ID identifier CP ID of the content provider an expiration date of the usage control policy data the communication address of the EMD service center usage space examination information wholesale price information a handling plan handling control information handling control information of a commodity demo the signature data for them etc. are contained.

Note that as in the second embodiment mentioned later where a secure container is transmitted via the service provider to a user home network in the usage control policy data an identifier SP ID of the service provider for providing the secure container by the content provider is contained.

Also in the SAM program download containers SDCto SDC as shown in a download driver indicating the routine of the download used when downloading a program in the SAMs to a label reader such as an UCP L Label R Reader indicating a syntax grammar of the usage control policy data UCP U lock key data for locking unlocking rewriting and erasing of the storage units flash ROM built in the SAMs to in block units and the signature data for them are contained.

Note that the storage unit is provided with various databases including for example a database for storing the certificate data.

The signature processing unit obtains the hash value of the data covered by the signature and produces the signature data SIG thereof by using the secret key data Kof the content provider .

Note that the hash value is produced by using a hash function. A hash function is a function receiving as input the data covered compressing the related input data to data having a predetermined bit length and outputting the same as the hash value. The hash function has as its characteristic feature that it is difficult to predict the input of the hash function from the hash value output . When one bit input to the hash function varies many bits of the hash value vary so it is difficult to find the input data having an identical hash value.

The secure container preparation unit produces the content file CF storing the header data meta data Meta the content data C A V expansion use software Soft and the watermark module WM input from the encryption unit and encrypted by the content key data Kc therein as shown in .

It is also possible to contain the file reader and the signature data of the file reader in the secret key data Kas shown in . By doing this in the SAMs to a plurality of secure containers storing the content files CF of different formats received from a plurality of secure containers of different streams can be efficiently processed.

Here the file reader is used when reading a content file CF and the key file KF corresponding to that and indicates the reading routine etc. of these files.

Note in the present embodiment a case where the related file reader is transmitted in advance from the EMD service center to the SAMs to is exemplified. Namely in the present embodiment the content file CF of the secure container does not store the file reader.

In the header data as shown in the synchronization signal content ID signature data by the secret key data Kof the content provider for the content ID directory information hyper link information serial number expiration date and producer information of the content file CF file size existence of encryption encryption algorithm information concerning the signature algorithm signature data by the secret key data ICof the content provider concerning the directory information etc. are contained.

In the meta data Meta as shown in explanatory text of the commodity content data C commodity demo and PR information information related to the commodity and the signature data from the content provider for them are contained.

In the present invention as shown in and the case where the meta data Meta is stored in the content file CF and transmitted is exemplified but it is also possible not to store the meta data Meta in the content file CF but transmit the same from the content provider to the SAM etc. through a route different from the route for transmitting the content file CF.

The A V expansion use software Soft is the software used when expanding the content file CF in the network apparatus and the AV apparatuses to of the user home network and is the expansion use software of for example the ATRAC3 method.

In this way by storing the A V expansion use software Soft in the secure container the content data C can be expanded by using the A V expansion use software Soft stored in the secure container in the SAMs to . Even if the compression and expansion method of the content data C is freely set by the content provider for every content data C or every content provider a large load will not be imposed on the user.

The watermark module WM contains for example the information required for detecting the electronic watermark information buried in the content data C and software as mentioned before.

Also the secure container preparation unit produces the secure container storing the content file CF shown mentioned above signature data

SIGof the related content file CF the key file KF shown in corresponding to the related content file CF read out from the key file database signature data SIGof the related key file KF certificate data CERof the content provider read out from the storage unit and signature data SIGof the related certificate data CERtherein.

Here the signature data SIGis used for verifying the legitimacy of the producer and transmitter of the content file CF at the received site of the secure container .

Here the signature data SIGis used for verifying the legitimacy of the transmitter of the key file KF at the received site of the secure container . Note that at the received site of the secure container the legitimacy of the producer of the key file KF is verified based on the signature data SIGin the key file KF. Also the signature data SIGis used also for verifying whether or not the key file KF is registered in the EMD service center .

In the present embodiment the encrypted content data C is stored in the secure container in a form not depending upon the compression method of the content data C existence of compression encryption method including both the cases of the common key encryption method and public key encryption method parameters of the signals giving the content data C sampling frequency etc. and the preparation method algorithm of the signature data. Namely these items can be freely determined by the content provider .

Also the secure container preparation unit outputs the secure container stored in the secure container database to the SAM management unit in response to a request from the user.

In this way in the present embodiment an in band method of storing the certificate CERof the public key data ICof the content provider in the secure container and transmitting the same to the user home network is employed. Accordingly the user home network does not have to communicate with the EMD service center for obtaining the certificate CER.

Note that in the present invention it is also possible to employ an out of band method of obtaining the certificate CERfrom the EMD service center by the user home network without storing the certificate CERin the secure container .

The mutual certification unit performs mutual certification between the EMD service center and the user home network to produce the session key data common key Kwhen the content provider transmits or receives data on line with the EMD service center and the user home network . The session key data Kis newly produced at each mutual certification.

The encryption and or decryption unit encrypts the data to be transmitted on line to the EMD service center and the user home network by the content provider by using the session key data K.

Also the encryption and or decryption unit decrypts the data received on line from the EMD service center and the user home network by the content provider by using the session key data K.

The usage control policy data preparation unit produces the usage control policy data and outputs this to the EMD service center management unit .

The usage control policy data is a descriptor defining operating rules of the content data C and for example describes the suggested retailer s price SRP intended by an operator of the content provider copy rule of the content data C etc.

Also when distributing the secure container to the SAMs to on line the SAM management unit uses as the communication protocol for transmitting the secure container an MHEG Multimedia and Hypermedia Information Coding Experts Group protocol if a digital broadcast or uses an XML SMIL HTML Hyper TextMarkup Language if the Internet and buries the secure containers in these communication protocols in a form not depending upon the coding method by tunneling.

Accordingly it is not necessary to match formats between the communication protocol and the secure container so the format of the secure container can be flexibly set.

Note that the communication protocol used when transmitting the secure container from the content provider to the user home network is not limited to those mentioned above and may be any protocol.

Also the secure RAM region is a region where predetermined permission certification is necessary for accessing the stored data. Signature data produced by using a MAC Message Authentication Code function with the key file KF and the certificate data CERand a storage use key data Khaving an inherent value in accordance with the type of the apparatus shown in as factors and the data obtained by encrypting the related key file KF and the certificate data CERby using media key data Khaving an inherent value in the storage medium are stored.

Also in the secure RAM region for example certificate revocation data revocation list for specifying the content provider and the SAMs to which became invalid due to illegitimate actions or the like is stored.

Also in the secure RAM region as will be mentioned later usage control status UCS data etc. produced when the purchase and or usage form of the content data C is determined in the SAMs to of the user home network is determined are stored. By this by the storage of the user control status data in the secure RAM region a ROM type storage medium with a purchase and or usage form determined therein is obtained.

In the media SAM for example the media ID serving as the identifier of the ROM type storage medium and the media key data Kare stored.

As the storage medium of the ROM type used in the present embodiment for example other than one shown in also a ROM type storage medium shown in and a ROM type storage medium shown in can be considered.

The ROM type storage medium shown in has the ROM region and the media SAM having the certificate authority function but is not provided with the secure RAM region as in the ROM type storage medium shown in . Where use is made of the ROM type storage medium the content file CF is stored in the ROM region and the key file KF is stored in the media SAM .

Also the ROM type storage medium shown in has the ROM region and the secure RAM region and does not have the media SAM as in the ROM type storage medium shown in . Where the ROM type storage medium is used the content file CF is stored in the ROM region and the key file KF is stored in the secure RAM region . Also where the ROM type storage medium is used mutual certification is not carried out with the SAM.

Also in the present embodiment other than the ROM type storage medium also a RAM type storage medium is used.

As the RAM type storage medium used in the present embodiment there is for example as shown in a RAM type storage medium having the media SAM secure RAM region and nonsecure RAM region . In the RAM type storage medium the media SAM has the certificate authority function and stores the key file KF. Also in the RAM region the content file CF is stored.

Also as the RAM type storage medium used in the present embodiment other than that also a RAM type storage medium shown in and a RAM type storage medium shown in can be considered.

The RAM type storage medium shown in has the nonsecure RAM region and the media SAM having the certificate authority function but is not provided with the secure RAM region as in the RAM type storage medium shown in . Where the RAM type storage medium is used the content file CF is stored in the RAM region and the key file KF is stored in the media SAM .

Also the RAM type storage medium shown in has the secure RAM region and the nonsecure RAM region but does not have the media SAM as in the RAM type storage medium shown in . Where use is made of the RAM type storage medium the content file CF is stored in the RAM region and the key file KF is stored in the secure RAM region . Also where use is made of the RAM type storage medium mutual certification is not carried out with the SAM.

Also where the secure container is distributed on line to the user home network by using a network or a digital broadcast the SAM management unit encrypts the secure container by using the session key data Kin the encryption and or decryption unit and then distributes the same via the network to the user home network .

In the present embodiment as the SAM management unit and the EMD service center management unit and the content provider management unit and service provider management unit mentioned later use is made of a communication gateway having a tamper resistant structure whereby for example monitoring and tampering of the processing content of the internal portion cannot be carried out or are difficult.

Here in both of the case where the content data C is distributed from the content provider to the user home network by using the storage medium and the case where it is distributed on line by using the network use is made of the secure container of a common form with the usage control policy data stored therein. Accordingly in the SAMs to of the user home network the rights clearing based on the common usage control policy data can be carried out in both of the cases of off line and on line.

Also as mentioned above in the present embodiment the in band method of enclosing the content data C encrypted by the content key data Kc and the content key data Kc for decrypting the related encryption in the secure container is employed. In the in band method when it is intended to reproduce the content data C by the apparatus of the user home network it is not necessary to separately distribute the content key data Kc so there is an advantage that the load of the network communication can be reduced. Also the content key data Kc has been encrypted by the distribution use key data KDto KD but the distribution use key data KDto KDare managed at the EMD service center and distributed to the SAMs to of the user home network in advance when the SAMs to access the EMD service center for the first time therefore in the user home network the usage of the content data C off line becomes possible without connecting with the EMD service center on line.

Note that the present invention has the flexibility to employ the out of band method for separately supplying the content data C and the content key data Kc to the user home network as will be mentioned later.

When receiving the settlement report data from the EMD service center the EMD service center management unit decrypts it at the encryption and or decryption unit by using the session key data Kand then stores the same in the storage unit .

As the settlement report data for example the content of the settlement concerning the content provider performed by the EMD service center at the settlement manager shown in is described.

Also the EMD service center management unit transmits the content ID as a global unique identifier of the content data C to be provided a public key data

K and signature data SIGof them to the EMD service center and receives as input the certificate data CERof the public key data Kfrom the EMD service center .

Also the EMD service center management unit produces as shown in a registration module Modstoring the content ID as the global unique identifier of the content data C to be provided the content key data Kc the usage control policy data the watermark module WM CP ID as the global unique identifier of the content provider and signature data SIGby the secret key data Kof the content provider for them therein when registering the content key data Kc the usage control policy data and the watermark module WM in the EMD service center and receiving the key file KF for each of the content data C. Then the EMD service center encrypts the registration module Modin the encryption and or decryption unit by using the session key data Kand then transmits the same via the network to the EMD service center . As the EMD service center management unit as mentioned above for example use is made of a communication gateway having a high tamper resistant structure whereby monitoring or tampering of the processing content of the internal portion cannot be carried out or are difficult.

Below an explanation will be given of the flow of the processing in the content provider by referring to and .

Note that as a prerequisite for performing the following processing the interested party of the content provider performs the registration processing for the EMD service center off line by using for example its own ID and a bank account for performing the settlement processing and acquires the global unique identifier CP ID. The identifier CP ID is stored in the storage unit .

First an explanation will be given of the processing where the content provider requests the certificate data CERfor proving the legitimacy of the public key data Kcorresponding to its own secret key data Kfrom the EMD service center by referring to .

The content provider generates a random number by using a true random number generator to produce the secret key data Kproduces the public key data Kcorresponding to the related secret key data Kand stores the same in the storage unit .

The EMD service center management unit reads out the identifier CP ID and the public key data of the content provider from the storage unit .

Then the EMD service center management unit transmits the identifier CP ID and the public key data Kto the EMD service center .

Then the EMD service center management unit receives as input the certificate data CERand the signature data SIGthereof from the EMD service center in accordance with the related registration and writes them into the storage unit .

Next an explanation will be given of the processing where the content provider registers the content key data Kc usage control policy data and the watermark module WM in the EMD service center and receives the key file KF corresponding to the content data C by referring to and .

Step A Mutual certification is carried out between the mutual certification unit of the content provider shown in and the EMD service center .

Step A The session key data Kobtained by the mutual certification performed at step A is shared by the content provider and the EMD service center .

Step A The content provider reads out the content ID content key data Kc usage control policy data watermark module WM and CP ID etc. to be registered into the EMD service center from the database of the storage unit etc.

Step A In the signature processing unit the signature data SIGindicating the legitimacy of the sender is produced for a module containing for example the usage control policy data read out at step A by using the secret key data Kof the content provider .

Then the EMD service center management unit produces the registration use module Modstoring the content ID content key data Kc usage control policy data watermark module WM and CP ID and the signature data SIGfor them therein as shown in .

Step A The encryption and or decryption unit encrypts the registration use module Modproduced at step A by using the session key data Kshared at step A.

Step A The EMD service center management unit transmits the registration use module Modencrypted at step A to the EMD service center .

Step A The EMD service center decrypts the received registration use module Modby using the session key data Kshared at step A.

Step A The EMD service center verifies the signature data SIGstored in the decrypted registration use module Modby using the public key data K confirms the legitimacy of the sender of the registration use module Mod and performs the processing of step A under the condition that the legitimacy of the sender is proved.

Step A The EMD service center stores and registers the content ID content key data Kc usage control policy data watermark module WM and CP ID stored in the registration use module Modin the predetermined database.

Note that the EMD service center management unit receives as shown in for example six months worth of the key files KF from the EMD service center after the registration processing in accordance with the registration use module Modis carried out for the EMD service center decrypts the related received key files KF by using the session key data Kobtained by the mutual certification between the mutual certification unit and the EMD service center and then stores the same in the key file database

Next an explanation will be given of the processing where the content provider transmits the secure container to the SAM of the user home network by referring to and .

Note that in the following example the case where the secure container is transmitted from the content provider to the SAM is exemplified but the case where the secure container is transmitted to each of the SAMs to is the same except it transmitted to each of the SAMs to via the SAM .

First as shown in the content data S is read out from the content master source database and output to the electronic watermark information addition unit .

Next the electronic watermark information addition unit buries the electronic watermark information in the content data S to produce the content data and outputs this to the compression unit .

Next the compression unit compresses the content data S by for example the ATRAC3 method to produce the content data S and outputs this to the encryption unit .

Also as shown in the content key data Kc is produced by generating a random number at the random number generation unit and the related produced content key data Kc is stored in the storage unit .

Next the encryption unit encrypts the content data S input from the compression unit meta data Meta read out from the storage unit the A V expansion use software Soft and the watermark module WM by using the content key data Kc and outputs the same to the secure container preparation unit . In this case it is also possible if the meta data Meta and the watermark module WM are not encrypted.

Then the secure container preparation unit produces the content file CF shown in . Also in the signature processing unit the hash value of the content file CF is obtained and the signature data SIGis produced by using the secret key data K.

Also the secure container preparation unit reads out the key file KF corresponding to the content data C from the key file database and outputs this to the signature processing unit .

Then the signature processing unit obtains the hash value of the key file KF input from the secure container preparation unit produces the signature data SIGby using the secret key data and outputs this to the secure container preparation unit .

Next the secure container preparation unit produces the secure container storing the content file CF and the signature data SIGthereof shown in the key file KF and the signature data SIGthereof shown in and the certificate data CERand the signature data SIGthereof shown in read out from the storage unit therein and stores this in the secure container database . Then the secure container preparation unit reads out the secure container to be provided to the user home network in response to for example a request from the user from the secure container database encrypts this at the encryption and or decryption unit by using the session key data Kobtained by the mutual certification between the mutual certification unit and the SAM and then transmits the same via the SAM management unit to the SAM of the user home network .

Below a summary of the flow of the overall processing of the content provider will be explained relative to the secure container preparation processing.

Step B The content provider receives as input its own certificate data CERfrom the EMD service center in advance and stores this in the storage unit database .

Step B The content data to be newly authored and an already stored content master source such as legacy content data are digitized allocated a content ID and stored in the content master source database and uniquely managed.

Step B The meta data Meta is produced for each content master source uniquely managed at step B and is stored in the storage unit .

Step B The content data S serving as the content master source is read out from the content master source database and output to the electronic watermark information addition unit the electronic watermark information is buried and the content data S is produced.

Step B The electronic watermark information addition unit stores the content of the buried electronic watermark information and the burial location in the predetermined database.

Step B In the compression unit the content data S with the electronic watermark information buried therein is compressed to produce the content data S.

Step B In the expansion unit the compressed content data S is expanded to produce the content data S.

Step B In the audial check unit the check of the sound of the expanded content data S is carried out.

Step B The content provider detects the electronic watermark information buried in the content data S based on the buried content and the burial location stored in the database at step B.

Then the content provider performs the processing of step B where both of the audial check and the detection of the electronic watermark information succeed while repeats the processing of step B where either one fails.

Step B A random number is generated at the random number generation unit to produce the content key data Kc and this is stored in the storage unit .

Step B In the encryption unit the compressed content data is encrypted by using the content key data Kc to produce the content data C.

Step B In the usage control policy data preparation unit the usage control policy data for the content data C is produced.

Step B The content provider outputs the content ID content key data Kc and the usage control policy data to the EMD service center .

Step B The content provider receives as input the key file KF encrypted by the distribution use key data KDto KDfrom the EMD service center .

Step B The content provider connects the links of the content data C and the key file KF by the hyper link.

Step B In the signature processing unit the signature data indicating the legitimacy of the producer is produced by using the secret key data Kfor each of the content data C and the key files KF.

Step B Where the content data is provided in a composite form using a plurality of secure containers the processing of the steps B to B is repeated to produce the secure container and the link between the content file CF and the key file KF and the link among the content files CF by using the hyper link etc.

The EMD service center has a certificate authority CA function a key management function and a rights clearing profit distribution function.

As shown in the EMD service center has a key server a key database a settlement processing unit a signature processing unit a settlement manager management unit a certificate and or usage control policy management unit a usage control policy database a certificate database a content provider management unit a CP database a SAM management unit a SAM database a mutual certification unit an encryption and or decryption unit and a KF preparation unit .

Note that in the flow of the data related to the data transmitted and received between the EMD service center and the content provider in the flow of the data among the functional blocks in the EMD service center is shown.

Also in the flow of the data related to the data transmitted and received between the SAMs to and the settlement manager shown in in the flow of the data among the functional blocks in the EMD service center is shown.

The key server reads out six months worth of the distribution use key data having the expiration date of one month stored in the key database and outputs the same to the SAM management unit .

Also other than the key database distribution use key data KD one series of key data for storing the key data such as the secret key data K of the EMD service center storage use key data K media key data K and the MAC key data Kare stored.

The settlement processing unit performs settlement processing based on the usage log data input from the SAMs to the suggested retailer s price SRP input from the certificate and or usage control policy management unit and sales price produces the settlement report data and settlement claim data outputs the settlement report data to the content provider management unit and outputs the settlement claim data to the settlement manager management unit .

Note that the settlement processing unit monitors whether or not transactions based on an illegal dumping price were carried out based on the sales price.

Here the usage log data indicates the log of the purchase and usage reproduction recording transfer etc. of the secure container in the user home network and is used when determining the payment sum of a license fee related to the secure container in the settlement processing unit .

In the usage log data for example the content ID serving as the identifier of the content data C stored in the secure container the identifier CP ID of the content provider distributing the secure container the compression method of the content data C in the secure container an identifier Media ID of the storage medium storing the secure container the identifier SAM ID of the SAMs to receiving the distribution of the secure container USER ID of the user of the related SAMs to etc. are described. Accordingly the EMD service center determines the sum of payment for each other party based on a distribution rate table determined in advance when it is necessary to distribute the money paid by the user of the user home network to license owners of for example the compression method and the storage medium other than the owner of the content provider and produces the settlement report data and the settlement claim data in accordance with the related determination. The related distribution rate table is produced for example for every content data stored in the secure container .

Also the settlement claim data is the authenticated data for which the payment of money to the settlement manager may be claimed. For example when the money paid by the user is distributed to a plurality of right holders it is produced for individual right holders.

Note that the settlement manager sends a statement of the related settlement manager to the EMD service center when the settlement is terminated. The EMD service center notifies the content of the related statement to the corresponding right holders.

The settlement manager management unit transmits the settlement claim data produced by the settlement processing unit via the payment gateway shown in to the settlement manager .

Note that as will be mentioned later it is also possible if the settlement manager management unit transmits the settlement claim data to the right holders of the content provider etc. and the right holders per se perform the settlement at the settlement manager by using the received settlement claim data .

Also the settlement manager management unit obtains the hash value of the settlement claim data in the signature processing unit and transmits signature data SIGproduced by using the secret key data Ktogether with the settlement claim data to the settlement manager .

The certificate and or usage control policy management unit reads out the certificate data CERand certificate data CERto CERetc. which are registered stored in the certificate database and authenticated and at the same time registers the usage control policy data of the content provider the content key data Kc the watermark module WM etc. in the usage control policy database to authenticate the same.

Here for the usage control policy database a search is carried out by using the content ID as a search key while for the certificate database a search is carried out by using the identifier CP ID of the content provider as the search key.

Also the certificate and or usage control policy management unit obtains the hash values of for example the usage control policy data content key data Kc and the watermark module WM and stores the authenticated data attached with the signature data using the secret key data Kin the usage control policy database

The content provider management unit has a function of communication with the content provider and can access the CP database for managing the identifiers CP ID etc. of the registered content providers .

The SAM management unit has a function of communication with the SAMs to in the user home network and can access the SAM database storing the identifiers SAM ID and SAM registration list etc. of the registered SAMs.

The KF preparation unit outputs the content key data Kc and usage control policy data input from the content provider management unit and the SAM program download containers SDCto SDCto the signature processing unit .

Also the KF preparation unit encrypts the content key data Kc the usage control policy data and the SAM program download containers SDCto SDCby using the distribution use key data KDto KDof the corresponding period input from the key server produces the key file KF storing the related encrypted data and the signature data SIGby the secret key data Kfor the related encrypted data input from the signature processing unit therein as shown in and stores the related produced key file KF in the KF database

First an explanation will be given of the flow of the processing when transmitting the distribution use key data from the EMD service center to the SAMs to in the user home network by referring to .

As shown in the key server reads out for example three months worth of the distribution use key data KDto KDfrom the key database every predetermined period and outputs the same to the SAM management unit .

Also the signature processing unit obtains the hash values of each of the distribution use key data KDto KDto produce signature data SIG SIGindividually corresponding to them by using the secret key data Kof the EMD service center and outputs them to the SAM management unit .

The SAM management unit encrypts these three months worth of the distribution use key data KDto KDand the signature data SIGto SIGof them by using the session key data Kobtained by the mutual certification between the mutual certification unit and the SAMs to and then transmits them to the SAMs to .

Next an explanation will be given of the processing in the case where the EMD service center receives an issuance request of the certificate data CERfrom the content provider by referring to .

In this case when receiving the identifier CP ID of the content provider public key data and the signature data SIGfrom the content provider the content provider management unit decrypts them by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in .

Then after confirming the legitimacy of the related decrypted signature data SIGat the signature processing unit it is confirmed whether or not the content provider issuing the issuance request of the related certificate data is registered in the CP database based on the identifier CP ID and the public key data K.

Then the certificate and or usage control policy management unit reads out the certificate data CERof the related content provider from the certificate database and outputs this to the content provider management unit .

Also the signature processing unit obtains the hash value of the certificate data CER produces the signature data SIGby using the secret key data Kof the EMD service center and outputs this to the content provider management unit .

Then the content provider management unit encrypts the certificate data CERand the signature data SIGthereof by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in and then transmits the same to the content provider .

Next an explanation will be given of the processing where the EMD service center receives the issuance request of the certificate data CERfrom the SAM by referring to .

In this case when receiving an identifier SAMof the SAM public key data K and signature data SIGfrom the SAM the SAM management unit decrypts them by using the session key data Kobtained by the mutual certification between the mutual certification unit and the SAM .

Then after confirming the legitimacy of the related decrypted signature data SIGin the signature processing unit based on the identifier SAMID and the public key data it is confirmed whether or not the SAM outputting the issuance request of the related certificate data is registered in the SAM database

Then the certificate and or usage control policy management unit reads out the certificate data CERof the related SAM from the certificate database and outputs this to the SAM management unit .

Also the signature processing unit obtains the hash value of the certificate data CER produces signature data SIGby using the secret key data Kof the EMD service center and outputs this to the SAM management unit .

Then the SAM management unit encrypts the certificate data CERand the signature data SIGthereof by using the session key data Kobtained by the mutual certification between the mutual certification unit and the SAM and then transmits the same to the SAM .

Note that the processing where the SAMs to request the certificate data is the same as the case of the SAM mentioned above except only the object is replaced by the SAMs to .

Note that in the present invention it is also possible if the EMD service center produces the certificate data CERof the public key data Kat the time of shipment when a secret key data Kand the public key data Kof the SAM are stored in the storage unit of the SAM at for example the related shipment of the SAM .

At this time at the related shipment it is also possible to store the certificate data CERin the storage unit of the SAM .

Next an explanation will be given of the processing where the EMD service center receives the registration use module Modshown in from the content provider by referring to .

In this case when the content provider management unit receives the registration use module Modshown in from the content provider the registration use module Modis decrypted by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in .

Then in the signature processing unit the legitimacy of the signature data SIGis verified by using the public key data Kread out from the key database

Next the certificate and or usage control policy management unit registers the usage control policy data content key data Kc watermark module WM and SRP stored in the registration use module Modin the usage control policy database

Next the content provider management unit outputs the content key data Kc and the usage control policy data to the KF preparation unit .

Next the KF preparation unit outputs the content key data Kc and usage control policy data input from the content provider management unit and the SAM program download containers SDCto SDCto the signature processing unit .

Then the signature processing unit obtains the hash value with respect to the whole data input from the KF preparation unit produces the signature data SIGthereof by using the secret key data Kof the EMD service center and outputs this to the KF preparation unit .

Next in the KF preparation unit by using the distribution use key data KDto KDof the corresponding period input from the key server the content key data Kc and usage control policy data and the SAM program download containers SDCto SDCare encrypted and the key file KF storing the related encrypted data and the signature data SIGinput from the signature processing unit therein is produced and is stored in the KF database

Here as the SAM program download containers SDCto SDC it is also possible to use those stored in the registration use module Modor it is also possible to use those held by the EMD service center in advance.

Next the content provider management unit encrypts the key file KF obtained by accessing the KF database by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in and then transmits the same to the content provider .

Next an explanation will be given of the settlement processing performed in the EMD service center by referring to .

When receiving as input the usage log data and signature data SIGthereof from for example the SAM of the user home network the SAM management unit decrypts the usage log data and the signature data SIGby using the session key data Kobtained by the mutual certification between the mutual certification unit and the SAM verifies the signature data SIGby the public key data Kof the SAM and then outputs the same to the settlement processing unit .

Then the settlement processing unit performs the settlement processing based on the usage log data input from the SAM management unit and the suggested retailer s price SRP contained in the usage control policy data read out from the usage control policy database via the certificate and or usage control policy management unit and the sales price and produces the settlement claim data and the settlement report data .

The settlement processing unit outputs the settlement claim data to the settlement manager management unit and at the same time outputs the settlement report data to the content provider management unit .

Next the settlement manager management unit transmits the settlement claim data and the signature data SIGthereof via the payment gateway shown in to the settlement manager after the mutual certification and the decryption by the session key data K.

By this the money of the sum indicated in the settlement claim data is paid to the content provider .

Next an explanation will be given of the processing where the EMD service center transmits the settlement report to the content provider by referring to .

When the settlement is carried out in the settlement processing unit as mentioned above the settlement report data is output from the settlement processing unit to the content provider management unit .

In the settlement report data as mentioned above for example the content of the settlement concerning the content provider performed with respect to the settlement manager shown in by the EMD service center is described.

When receiving as input the settlement report data from the settlement processing unit the EMD service center encrypts this by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in and then transmits the same to the content provider .

Also after registering authenticating the usage control policy data as mentioned above the EMD service center may encrypt the authenticated certificate module by the distribution use key data KDto KDand transmit the same from the EMD service center to the content provider too.

Also the EMD service center performs the processing at the time of shipment of the SAMs to and the registration processing of the SAM registration list other than the above but these processings will be mentioned later.

The network apparatus includes a built in SAM . Also the AV apparatuses to includes built in SAMs to .

Note that the AV apparatuses to can have a network communication function too or may not have the network communication function but utilize the network communication function of the network apparatus via the bus .

As shown in the network apparatus has the SAM a communication module a decryption and or expansion module a purchase and or usage form determination operation unit a download memory a reproduction module and an external memory .

The SAMs to are modules for performing the charge processing in units of content and communicate with the EMD service center .

The SAMs to are managed in their specifications versions etc. by for example the EMD service center . If there is a desire for mounting them by a home electric apparatus maker they are licensed as a black box charging module for charging in units of content. For example a home electric apparatus developer manufacturer cannot determine the specifications inside the ICs integrated circuits of the SAMs to . The EMD service center standardizes the interfaces etc. of the related ICs. They are mounted in the network apparatus and the AV apparatuses to according to that.

The SAMs to are hardware modules IC modules etc. having tamper resistance so that the processing contents thereof are completely sheltered from the outside the processing contents cannot be monitored or tampered with from the outside and the data stored inside in advance and the data being processed cannot be monitored and tampered with from the outside.

When the functions of the SAMs to are realized in the form of ICs secret memories are provided inside the ICs and secret programs and secret data are stored there. If the function of a SAM can be incorporated in any other portion of the apparatus not limited to the physical form of an IC that portion can be defined as a SAM too.

Note that in the flow of the data related the processing of inputting a secure container from the content provider and decrypting the key file KF in the secure container is shown.

As shown in the SAM has a mutual certification unit encryption and or decryption units and a content provider management unit an error correction unit a download memory management unit a secure container decryption unit a decryption and or expansion module management unit an EMD service center management unit a usage monitor unit a charge processing unit a signature processing unit a SAM management unit a media SAM management unit a stack work memory and an external memory management unit .

Note that the AV apparatuses to do not have the download memory so the download memory management unit does not exist in the SAM to .

Note that the predetermined function of the SAM shown in is realized by executing a secret program in for example a not illustrated CPU.

Also in the external memory after going through the following processing as shown in a usage log data and a SAM registration list are stored.

Here the memory space of the external memory cannot be seen from the outside for example a host CPU of the SAM . Only the SAM can manage access with respect to the storage region of the external memory .

Also as the stack memory use is made of for example a SARAM. As shown in the secure container content key data Kc usage control policy data UCP a lock key data Kof a storage unit certificate data CERof the content provider usage control status data UCS SAM program download containers SDCto SDC etc. are provided.

Below among the functions of the SAM the processing contents of the functional blocks when the secure container from the content provider is input will be explained by referring to .

The mutual certification unit performs mutual certification between the content provider and the EMD service center when the SAM transmits and receives the data on line between the content provider and the EMD service center to produce a session key data common key Kand outputs this to the encryption and or decryption unit . The session key data Kis newly produced with each mutual certification.

The encryption and or decryption unit encrypts and or decrypts the data transmitted and received between the content provider and the EMD service center by using the session key data Kproduced by the mutual certification unit .

The error correction unit corrects the error of the secure container and outputs the same to the download memory management unit .

Note that it is also possible if the user home network has a function for detecting whether or not the secure container has been tampered with.

In the present embodiment the case where the error correction unit was built in the SAM was exemplified but it is also possible to impart the function of the error correction unit to the outside of the SAM for example the host CPU .

The download memory management unit performs the mutual certification between the mutual certification unit and a media SAM in a case where the download memory has a media SAM having a mutual certification function as shown in and then encrypts the secure container after the error correction by using the session key data Kobtained by the mutual certification and writes the same into the download memory shown in . As the download memory use is made of for example a nonvolatile semiconductor memory such as memory stick.

Note that as shown in where a memory not provided with a mutual certification function such as a HDD hard disk drive is used as a download memory the inside of the download memory is not secure so the content file CF is downloaded on the download memory and a key file KF having a high secrecy is downloaded on for example the stack memory shown in .

The secure container decryption unit decrypts the content key data Kc usage control policy data and the SAM program download containers SDCto SDCin the key file KF stored in the secure container input from the download memory management unit by using distribution use key data KDto KDread out from the storage unit .

The related decrypted content key data Kc usage control policy data and the SAM program download containers SDCto SDCare written into the stack memory .

The EMD service center management unit manages the communication with the EMD service center shown in .

The signature processing unit verifies the signature data in the secure container by using a public key data Kof the EMD service center read out from the storage unit and the public key data Kof the content provider .

The storage unit stores as the secret data which cannot be read out and rewritten from the outside of the SAM as shown in a plurality of distribution use key data KDto KDwith expiration dates SAM IDs user IDs passwords information reference use IDs a SAM registration list storage use key data K public key data Kof the route CA public key data Kof the EMD service center media key data K public key data Kof the EMD service center secret key data Kof the SAM the certificate data CERstoring public key data Kof the SAM therein signature data SIGof the certificate CERusing the secret key data Kof the EMD service center the original key data for the mutual certification with the decryption and or expansion module where the common key encryption method is employed the original key data for the mutual certification with the media SAM where the common key encryption method is employed and certificate data CERof the media SAM where the public key encryption method is employed .

Also in the storage unit a secret program for realizing at least one part of the functions shown in is stored.

As the storage unit use is made of for example a flash EEPROM electrically erasable programmable RAM .

Below an explanation will be made of the flow of the processing in the SAM when storing the distribution use key data KDto KDreceived from the EMD service center in the storage unit by referring to .

In this case first mutual certification is carried out between the mutual certification unit and the mutual certification unit shown in .

Next three months worth of the distribution use key data Kto Kencrypted by the session key data Kobtained by the related mutual certification and the signature data SIGto SIGthereof are written from the EMD service center via the EMD service center management unit into the stack memory .

Next in the encryption and or decryption unit by using the session key data K the distribution use key data Kto Kand the signature data SIGto SIGthereof are decrypted.

Next in the signature processing unit after the legitimacy of the signature data SIGto SIGstored in the stack memory is confirmed the distribution use key data Kto Kare written into the storage unit .

Below an explanation will be made of the flow of the processing in the SAM receiving as input the secure container provided by the content provider by referring to .

Mutual certification is carried out between the mutual certification unit of the SAM shown in and the mutual certification unit shown in .

The encryption and or decryption unit decrypts the secure container supplied from the content provider via the content provider management unit by using the session key data Kobtained by the related mutual certification.

Next the signature processing unit verifies the signature data SIGshown in and then verifies the legitimacy of the signature data SIGand SIGby using the public key data Kof the content provider stored in the certificate data CERshown in .

At this time when it is verified that the signature data SIGis legitimate the legitimacy of the producer and the transmitter of the content file CF is confirmed.

Also when it is verified that the signature data SIGis legitimate the legitimacy of the transmitter of the key file KF is confirmed.

Also the signature processing unit verifies the legitimacy of the signature data SIGin the key file KF shown in that is the legitimacy of the producer of the key file KF and whether or not the key file KF is registered in the EMD service center by using the public key data Kread out from the storage unit .

The content provider management unit outputs the secure container to the error correction unit when the legitimacy of the signature data SIG SIG and SIGis confirmed.

The error correction unit performs the error correction of the secure container and then outputs the same to the download memory management unit .

The download memory management unit writes the secure container into the download memory after performing the mutual certification between the mutual certification unit and the media SAM shown in .

Next the download memory management unit performs mutual certification between the mutual certification unit and the media SAM shown in and then reads out the key file KF shown in stored in the secure container from the download memory and outputs the same to the secure container decryption unit .

Then in the secure container decryption unit by using the distribution use data KDto KDof the corresponding period input from the storage unit the content key data Kc usage control policy data and the SAM program download containers SDCto SDCin the key file KF shown in are decrypted.

Then the decrypted content key data Kc usage control policy data and the SAM program download containers SDCto SDCare written into the stack memory .

Below an explanation will be made of the processing contents of the functional blocks related to the processing of using and purchasing the content data C downloaded on the download memory by referring to .

The usage monitor unit reads out the usage control policy data and the usage control status data from the stack memory and monitors so that the purchase and or usage of the content is carried out within a range permitted by the related read out usage control policy data and usage control status data .

Here the usage control policy data is stored in the KF after decryption and stored in the stack memory as explained by using .

Also the usage control status data is stored in the stack memory when the purchase form is determined by the user as will be mentioned later.

The charge processing unit produces the usage log data in response to an operation signal S from the purchase and or usage form determination operation unit shown in .

Here the usage log data describes the log of the purchase and usage forms of the secure container by the user as mentioned before and is used when performing settlement processing in accordance with the purchase of the secure container and determining the payment of the license fee in the EMD service center .

Also the charge processing unit notifies the sales price or the suggested retailer s price data SRP read out from the stack memory to the user according to need.

Here the sales price and the suggested retailer s price data SRP have been stored in the usage control policy data of the key file KF shown in stored in the stack memory after decryption.

The charge processing by the charge processing unit is carried out based on the right content such as the usage permission condition indicated by the usage control policy data and the usage control status data under the monitoring of the usage monitor unit . Namely the user purchases and uses the content within the range according to the related right content etc.

Also the charge processing unit produces the usage control status UCS data describing the purchase form of the content by the user and writes this into the stack memory .

As the purchase form of the content there are for example an outright purchase without restriction as to the reproduction by the purchaser and copying for the usage of the related purchaser a reproduction charge for charging with each reproduction etc.

Here the usage control status data is produced when the user determines the purchase form of the content and is used for control so that the user uses the related content within the range permitted by the related determined purchase form hereafter. In the usage control status data the ID of the content the purchase form the price in accordance with the related purchase form the SAM ID of the SAM with the purchase of the related content performed therefor the USER ID of the purchased user etc. are described.

Note that where the determined purchase form is a reproduction charge for example the usage control status data is transmitted from the SAM to the content provider in real time simultaneously with the purchase of the content data C and the content provider instructs the EMD service center to obtain the usage log data at the SAM within the predetermined period.

Also where the determined purchase form is an outright purchase for example the usage control status data is transmitted in real time to both of the content provider and the EMD service center . In this way in the present embodiment in both cases the usage control status data is transmitted in real time to the content provider .

The EMD service center management unit transmits the usage log data read out from the external memory via the external memory management unit to the EMD service center .

At this time the EMD service center management unit produces the signature data SIGof the usage log data by using the secret key data Kin the signature processing unit and transmits the signature data SIGtogether with the usage log data to the EMD service center .

The usage log data can be transmitted to the EMD service center in response to for example a request from the EMD service center or periodically or can be transmitted when the amount of information of the log information contained in the usage log data becomes a predetermined amount or more too. The related amount of information is determined in accordance with for example the storage capacity of the external memory .

The download memory management unit outputs the content data C read out from the download memory content key data Kc read out from the stack memory and the user watermark use data input from the charge processing unit to the decryption and or expansion module management unit in the case where for example a reproduction operation of the content is carried out in response to the operation signal S from the purchase form determination operation unit shown in .

Also the decryption and or expansion module management unit outputs the content file CF read out from the download memory and the content key data Kc and a half disclosure parameter data read out from the stack memory to the decryption and or expansion module management unit when a demo operation of the content is carried out in response to the operation signal S from the purchase form determination operation unit shown in .

Here the half disclosure parameter data is described in the usage control policy data and indicates the handling of the content in the demo mode. In the decryption and or expansion module it becomes possible to reproduce the encrypted content data C in the half disclosure state based on the half disclosure parameter data . As the procedure of the half disclosure there is for example a procedure of designating the blocks to be decrypted and the blocks not to be decrypted by using the content key data Kc limiting the reproduction function at the demo or limiting a demo enable period by the half disclosure parameter data by utilizing the fact that the decryption and or expansion module processes the data signal in units of predetermined blocks.

First an explanation will be made of the flow of the processing up to when the purchase form of the secure container downloaded on the download memory from the content provider is determined by referring to .

When the operation signal S indicating the demo mode is output to the charge processing unit by the operation of the purchase and or usage form determination operation unit shown in by the user for example the content file CF stored in the download memory is output via the decryption and or expansion module management unit to the decryption and or expansion module shown in .

At this time for the content file CF mutual certification between the mutual certification unit and the media SAM encryption and or decryption by the session key data K mutual certification between the mutual certification unit and the mutual certification unit and encryption and or decryption by the session key data Kare carried out.

The content file CF is decrypted by using the session key data Kat the decryption unit shown in and then output to the decryption unit .

Also the content key data Kc and the half disclosure parameter data read out from the stack memory are output to the decryption and or expansion module shown in . At this time after the mutual certification between the mutual certification unit and the mutual certification unit encryption and decryption by the session key data Kare carried out with respect to the content key data Kc and the half disclosure parameter data .

Next the decrypted half disclosure parameter data is output to the half disclosure processing unit . Under the control of the half disclosure processing unit the decryption of the content data C using the content key data Kc by the decryption unit is carried out in half disclosure.

Next the content data C decrypted in half disclosure is expanded at the expansion unit and then output to the electronic watermark information processing unit .

Next the user watermark use data is buried in the content data C in the electronic watermark information processing unit and then the content data C is reproduced at the reproduction module and sound in accordance with the content data C is output.

Then when the user trying out the content determines the purchase form by operating the purchase and or usage form determination operation unit the operation signal S indicating the related determined purchase form is output to the charge processing unit .

Then in the charge processing unit the usage log data and the usage control status data in accordance with the determined purchase form are produced the usage log data is written into the external memory via the external memory management unit and at the same time the usage control status data is written into the stack memory .

Thereafter in the usage monitor unit control monitoring is carried out so that the content data is purchased and used within the range permitted by the usage control status data .

Then a new key file KFshown in mentioned later is produced and the related produced key file KFis stored in the download memory via the download memory management unit .

As shown in the usage control status data stored in the key file KFis sequentially encrypted by using the storage key data Kand the media key data Kby utilizing the CBC mode of the DES.

Here the storage use key data Kis data determined in accordance with the type of apparatus for example a SACD Super Audio Compact Disc a DVD Digital Versatile Disc apparatus CD R apparatus and MD Mini Disc apparatus and is used for establishing one to one correspondence between the types of the apparatuses and the types of the storage media. Also the media key data Kis data unique to the storage medium.

Also in the signature processing unit a hash value Hof the key file KFis produced by using the secret key data Kof the SAM and the related produced hash value His written into the stack memory in correspondence to the key file KF. The hash value His used for verifying the legitimacy of the producer of the key file KFand whether or not the key file KFwas tampered with.

Next the flow of the processing where the content data C with the purchase form already determined therefor stored in the download memory will be explained by referring to .

In this case under the monitoring of the usage monitor unit based on the operation signal S the content file CF stored in the download memory is output to the decryption and or expansion module shown in . At this time mutual certification is carried out between the mutual certification unit shown in and the mutual certification unit of the decryption and or expansion module shown in .

Also the content key data Kc read out from the stack memory is output to the decryption and or expansion module .

Then in the decryption unit of the decryption and or expansion module the decryption of the content file CF using the content key data Kc and the expansion processing by an expansion unit are carried out and in the reproduction module the content data C is reproduced.

At this time by the charge processing unit the usage log data stored in the external memory is updated in accordance with the operation signal S.

The usage log data is read out from the external memory and then after passing through the mutual certification transmitted via the EMD service center management unit together with the signature data SIGto the EMD service center .

Next as shown in the flow of the processing in the SAM in a case where for example after the purchase form of the content file CF downloaded on the download memory of the network apparatus is determined as mentioned above a new secure container storing the related content file CF is produced and the secure container is transferred via the bus to the SAM of the AV apparatus will be explained by referring to .

The user operates the purchase and or usage form determination operation unit and instructs the transfer of the predetermined content stored in the download memory to the AV apparatus and the operation signal S in accordance with the related operation is output to the charge processing unit .

By this the charge processing unit updates the usage log data stored in the external memory based on the operation signal S.

Also the charge processing unit transmits the usage control status data indicating the related determined purchase form via the EMD service center management unit to the EMD service center whenever the purchase form of the content data is determined.

Also the download memory management unit outputs the content file CF and the signature data SIGthereof shown in the key file KF and the signature data SIGthereof and the key file KFand the hash value Hthereof read out from the download memory to the SAM management unit . At this time the mutual certification between the mutual certification unit of the SAM and the media SAM and the encryption and or decryption by the session key data Kare carried out.

Also the signature processing unit obtains the hash value of the content file CF produces signature data SIGby using the secret key data K and outputs this to the SAM management unit .

Also the signature processing unit obtains the hash value of the key file KF produces signature data SIGby using the secret key data Kand outputs this to the SAM management unit .

Also the SAM management unit reads out the certificate data CERand the signature data SIGthereof and the certificate data CERand the signature data SIGthereof shown in from the storage unit .

Also the mutual certification unit outputs the session key data Kobtained by performing the mutual certification with the SAM to the encryption and or decryption unit .

The SAM management unit produces a new secure container comprised of the data shown in B C and D encrypts the secure container in the encryption and or decryption unit by using the session key data K and then outputs the same to the SAM of the AV apparatus shown in .

At this time in parallel to the mutual certification between the SAM and the SAM mutual certification of the bus serving as the IEEE1394 serial bus is carried out.

Below as shown in the flow of the processing in the SAM when writing the secure container input from the SAM into the storage medium of a RAM type or the like will be explained by referring to .

Here the RAM type storage medium has for example an unsecure RAM region a media SAM and a secure RAM region .

In this case the SAM management unit of the SAM receives as input the secure container from the SAM of the network apparatus as shown in and .

Then in the encryption and or decryption unit the secure container input via the SAM management unit is decrypted by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit of the SAM .

Next in the signature processing unit the legitimacy of the signature data SIGis verified by using the public key data and the legitimacy of the producer of the content file CF is confirmed. Also in the signature processing unit the legitimacy of the signature data SIGis verified by using the public key data K and the legitimacy of the transmitter of the content file CF is confirmed.

Then after it is confirmed that the producer and the transmitter of the content file CF are legitimate the content file CF is output from the SAM management unit to a storage module management unit and the content file CF is written into the RAM region of the RAM type storage medium shown in .

Also the key file KF and the signature data and SIGthereof the key file KFand the hash value Kthereof the certificate data CERand the signature data SIGthereof and the certificate data CERand the signature data SIGthereof decrypted by using the session key data Kare written into the stack memory .

Next the signature processing unit verifies the signature data SIGread out from the stack memory by using the public key data Kread out from the storage unit and confirms the legitimacy of the certificate data CER.

Then the signature processing unit verifies the legitimacy of the signature data SIGstored in the stack memory by using the public key data Kstored in the certificate data CERwhen confirming the legitimacy of the certificate data CER. Then when it is verified that the signature data SIGis legitimate the legitimacy of the key file KF is confirmed.

Also the signature processing unit verifies the signature data SIGread out from the stack memory by using the public key data Kread out from the storage unit and confirms the legitimacy of the certificate data CER.

Then the signature processing unit verifies the legitimacy of the signature data stored in the stack memory by using the public key data Kstored in the certificate data CERwhen confirming the legitimacy of the certificate data CER. Then when it is verified that the signature data SIGis legitimate the legitimacy of the producer of the key file KF is confirmed.

When it is confirmed that the producer and the transmitter of the key file KF are legitimate the key file KF is read out from the stack memory and written into the secure RAM region of the RAM type storage medium shown in via the storage module management unit .

Also the signature processing unit verifies the legitimacy of the hash value Hby using the public key data Kand confirms the legitimacy of the producer and transmitter of the key file KF.

Then when the legitimacy of the producer and the transmitter of the key file KFis confirmed the key file KFshown in is read out from the stack memory and output to the encryption and or decryption unit .

Note that in the related example the case where the producer and the transmitter of the key file KFwere the same was mentioned but where the producer and the transmitter of the key file KFare different the signature data of the producer and the signature data of the transmitter are produced with respect to the key file KF and the legitimacy of the both signature data is verified in the signature processing unit .

Then the encryption and or decryption unit encrypts the content key data Kc and the usage control status data in the key file KFby sequentially using the storage use key data K media key data K and the purchaser key data Kread out from the storage unit and outputs the same to the storage module management unit .

Then by the storage module management unit the encrypted key file KFis stored in the secure RAM region of the RAM type storage medium .

Note that the media key data Kis stored in the storage unit in advance by the mutual certification between the mutual certification unit shown in FIG. and the media SAM of the RAM type storage medium shown in .

Here the storage use key data Kis data determined in accordance with the type of apparatus AV apparatus in the related example of for example the SACD Super Audio Compact Disc DVD Digital Versatile Disc apparatus CD R apparatus and MD Mini Disc apparatus and is used for establishing one to one correspondence between the types of the apparatuses and the types of the storage media. Note that the physical structures of the disc media are the same between SACD and DVD so there is a case where the recording and or reproduction of the storage medium of an SACD can be carried out by using a DVD apparatus. The storage use key data Kperforms the function of preventing illegitimate copies in such a case.

Note that in the present embodiment it is also possible not to encrypt using the storage use key data K.

Also the media key data Kis data unique to the storage medium RAM type storage medium in the related example .

The media key data Kis stored in the storage medium RAM type storage medium shown in in the related example . It is preferred from the viewpoint of the security that encryption and the decryption using the media key data Kbe carried out in the media SAM of the storage medium. At this time the media key data Kis stored in the related media SAM where the media SAM is mounted in the storage medium while is stored in for example a region out of management of the host CPU in the RAM region where the media SAM is not mounted in the storage medium.

Note that it is also possible to perform the mutual certification between the apparatus side SAM SAM in the related example and the media SAM media SAM in the related example transfer the media key data Kvia the secure communication route to the apparatus side SAM and perform the encryption and decryption using the media key data Kin the apparatus side SAM as in the present embodiment.

In the present embodiment the storage use key data Kand the media key data Kare used for protecting the security of the level of the physical layer of the storage medium.

Also the purchaser key data Kis data indicating the purchaser of the content file CF and is allocated by the EMD service center to the related purchased user when for example the content is purchased by outright purchase. The purchaser key data Kis managed in the EMD service center .

Also in the above embodiment the case where the key files KF and KFwere stored in the secure RAM region of the RAM type storage medium by using the storage module was exemplified but as indicated by a dotted line in it is also possible to store the key files KF and KFin the media SAM from the SAM .

Next the flow of the processing when determining the purchase form in the AV apparatus where the user home network is distributed the ROM type storage medium shown in with the purchase form of the content undetermined therefor off line will be explained by referring to and .

The SAM of the AV apparatus first performs the mutual certification between the mutual certification unit shown in and the media SAM of the ROM type storage medium shown in and then receives as input the media key data Kfrom the media SAM .

Note that where the SAM holds the media key data Kin advance it is also possible if the related input is not carried out.

Next the key file KF and the signature data SIGthereof and the certificate data CERand the signature data SIGthereof shown in stored in the secure container stored in the secure RAM region of the ROM type storage medium are input via the media SAM management unit or not illustrated read out module management unit and are written into the stack memory .

Next in the signature processing unit after the legitimacy of the signature data SIGis confirmed the public key data Kis extracted from the certificate data CER and by using this public key data Kthe legitimacy of the signature data SIG that is the legitimacy of the transmitter of the key file KF is verified.

Also in the signature processing unit by using the public key data Kread out from the storage unit the legitimacy of the signature data SIGstored in the key file KF that is the legitimacy of the producer of the key file KF is verified.

When the legitimacy of the signature data SIGand SIGis confirmed in the signature processing unit the key file KF is read out from the stack memory to the secure container decryption unit .

Next in the secure container decryption unit by using the distribution use data KDto KDof the corresponding period the content key data Kc usage control policy data and the SAM program download containers SDCto SDCstored in the key file KF are decrypted and are written into the stack memory .

Next after the mutual certification between the mutual certification unit shown in and the decryption and or expansion module shown in the decryption and or expansion module management unit of the SAM outputs the content key data Kc stored in the stack memory and the half disclosure parameter data stored in the usage control policy data and the content data C stored in the content file CF read out from the ROM region of the ROM type storage medium to the decryption and or expansion module shown in . Next in the decryption and or expansion module the content data C is decrypted in the half disclosure mode by using the content key data Kc and then expanded and output to a reproduction module . Then in the reproduction module the content data C from the decryption and or expansion module is reproduced.

Next the purchase form of the content is determined by the purchase operation of the purchase form determination operation unit shown in by the user and the operation signal S indicating the related determined purchase form is input to the charge processing unit .

Next the charge processing unit produces the usage control status data in response to the operation signal S and writes this into the stack memory .

Next the content key data Kc and the usage control status data are output from the stack memory to the encryption and or decryption unit .

Next the encryption and or decryption unit sequentially encrypts the content key data Kc and the usage control status data input from the stack memory by using the storage use key data Kthe media key data K and the purchaser key data Kread out from the storage unit and writes them into the stack memory .

Next in the media SAM management unit the key file KFshown in is produced by using the encrypted content key data Kc the usage control status data and the SAM program download containers SDCto SDCread out from the stack memory .

Also in the signature processing unit the hash value Hof the key file KFshown in Fig. Figure C is produced and the related hash value His output to the media SAM management unit .

Next after the mutual certification between the mutual certification unit shown in and the media SAM shown in the media SAM management unit writes the key file KFand the hash value Hinto the secure RAM region of the ROM type storage medium via a storage module shown in .

At this time the usage control status data and the usage log data produced by the charge processing unit are read out from the stack memory and the external memory at the predetermined timing and transmitted to the EMD service center .

Note that where the key file KF is stored in the media SAM of the ROM type storage medium as indicated by the dotted line in the SAM receives as input the key file KF from the media SAM . Also in this case the SAM writes the produced key file KFinto the media SAM .

Below as shown in the flow of the processing when the secure container is read out from the ROM type storage medium with the purchase form undetermined therefor in the AV apparatus to produce a new secure container this is transferred to the AV apparatus the purchase form is determined in the AV apparatus and this is written into a RAM type storage medium will be explained by referring to and .

Note that the transfer of the secure container from the ROM type storage medium to the RAM type storage medium can be carried out between the network apparatus shown in and any of the AV apparatuses to shown in .

First mutual certification is carried out between the SAM of the AV apparatus and the media SAM of the ROM type storage medium and media key data Kof the ROM type storage medium is transferred to the SAM .

Also mutual certification is carried out between the SAM of the AV apparatus and the media SAM of the RAM type storage medium and media key data Kof the RAM type storage medium is transferred to the SAM .

Note that where encryption using the media key data Kand Kis carried out in the media SAM and the media SAM the transfer of the media key data Kand Kis not carried out.

Next the SAM outputs the content file CF and the signature data SIGthereof shown in read out from the ROM region of the ROM type storage medium the key file KF and the signature data SIGthereof shown in read out from the secure RAM region and the certificate data CERand the signature data SIGthereof to the encryption and or decryption unit via the media SAM management unit or not illustrated read out module management unit as shown in .

Also the content file CF and the key file KF are output from the media SAM management unit to the signature processing unit .

Then in the signature processing unit the hash values of the content file CF and the key file KF are obtained signature data SIGand SIGare produced by using secret key data Kand they are output to the encryption and or decryption unit .

Also the certificate data CERand the signature data SIGthereof are read out from the storage unit and output to the encryption and or decryption unit .

Then the secure container shown in is encrypted by using the session key data Kobtained by mutual certification between the SAM and in the encryption and or decryption unit and then output via the SAM management unit to the SAM of the AV apparatus .

In the SAM as shown in the secure container shown in input from the SAM via the SAM management unit is decrypted in the encryption and or decryption unit by using the session key data K and then the legitimacy of the signature data SIGand SIGstored in the secure container that is the legitimacy of the producer and the transmitter of the content file CF is confirmed.

Then after it is confirmed that the producer and the transmitter of the content file CF are legitimate the content file CF is written into the RAM region of the RAM type storage medium via the media SAM management unit .

Also after the key file KF and the signature data SIGand SIGthereof and certificate data CERand the signature data SIGthereof input from the SAM via the SAM management unit are written into the stack memory they are decrypted in the encryption and or decryption unit by using the session key data K.

Next the related decrypted signature data SIGis verified in the signature processing unit . When the legitimacy of the certificate data CERis confirmed by using the public key data Kstored in the certificate data CER the legitimacy of the signature data SIGand SIG that is the legitimacy of the producer and the transmitter of the key file KF is confirmed.

Then when the legitimacy of the producer and the transmitter of the key file KF is confirmed the key file KF is read out from the stack memory and output to the secure container decryption unit .

Next the secure container decryption unit decrypts the key file KF by using the distribution use data KDto KDof the corresponding period and writes the related decrypted key file KF into the stack memory .

Next the usage control policy data stored in the already decrypted key file KF stored in the stack memory is output to the usage monitor unit . The usage monitor unit manages the purchase form and usage form of the content based on the usage control policy data .

Next for example when the demo mode is selected by the user the content data C of the content file CF already decrypted by the session key data K the content key data Kc stored in the stack memory the half disclosure parameter data obtained from the usage control policy data and the user watermark use data are output via the decryption and or expansion module management unit shown in to the reproduction module after passing through mutual certification Then in the reproduction module the reproduction of the content data C corresponding to the demo mode is carried out.

Next the purchase and or usage form of the content is determined by the operation of the purchase and or usage form determination operation unit shown in by the user and the operation signal S in accordance with the related determination is output to the charge processing unit .

Then in the charge processing unit the usage control status data and the usage log data are produced in accordance with the determined purchase and or usage form and are written into the stack memory and the external memory .

Next the content key data Kc and the usage control status data are read out from the stack memory to the encryption and or decryption unit sequentially encrypted in the encryption and or decryption unit by using the storage use key data K media key data K and the purchaser key data Kread out from the storage unit and output to the storage module management unit . Then for example in the storage module management unit the key file KFshown in is produced and the key file KFis written into the media SAM of the RAM type storage medium via the media SAM management unit .

Also the content file CF stored in the secure container is written into the RAM region of the RAM type storage medium by the storage module management unit .

Also the usage control status data and the usage log data are transmitted to the EMD service center at the predetermined timing.

Where the functions of the SAMs to are realized as hardware by using an ASIC type CPU including a memory data having a high degree of secrecy such as a security functional module for realizing the functions shown in program module for performing the rights clearing of the content and the key data are stored in that memory. One series of rights clearing use program modules such as an encryption library module public key code common key code random number generator hash function program module for the usage control of the content and the program module of the charge processing are mounted as for example software.

For example a module such as the encryption and or decryption unit shown in is mounted as an IP core in the ASIC type CPU as hardware due to the problem of for example processing speed. Depending on the clock speed or performance of the CPU code system etc. it is also possible to mount the encryption and or decryption unit as software.

Also as the storage unit shown in the program module for realizing the functions shown in and the memory for storing the data use is made of for example a nonvolatile memory flash ROM while as the working memory a high speed writable memory such as an SRAM is used. Note that other than them as the memory included in the SAMs to it is also possible to use a ferroelectric memory FeRAM .

Also in the SAMs to other than the above a clock function used for the verification of the date in the expiration date and the contract period etc. for the usage of the content is included.

As mentioned above the SAMs to have tamper resistance sheltering the program module data and the processing content from the outside. In order to prevent the program and content of data having high secrecy stored in the memory inside the IC of the related SAM and values of the register group related to the system configuration of the SAM and the encryption library and the register group of the clock from being read out and newly written via the bus of the host CPU of the apparatuses with the SAMs to mounted thereon that is in order to prevent the host CPU of the mounted apparatus from not existing in the allocated address space an address space not seen from the host CPU on the mounted apparatus side is set up in the related SAM by using an MMU memory management unit for managing the memory space on the CPU side.

Also the SAMs to have structures durable against physical attack from the outside such as X rays or heat and further have structures such that even if real time debugging reverse engineering using a debug use tool hardware ICE or software ICE or the like is carried out the processing content thereof cannot be seen or the debug use tool per se cannot be used after the manufacture of the IC.

The SAMs to per se are usual ASIC type CPUs including memories in the hardware structure. Their functions depend on the software for operating the related CPU but are different from the general ASIC type CPU in the point that they have a hardware structure of the encryption function and tamper resistance.

Where all of the functions of the SAMs to are realized by software there are cases where the software processing is carried out by enclosing the same inside a module having the tamper resistance and cases where they are achieved by software processing on the host CPU mounted on the usual set and steps are taken so that decipherment becomes impossible at only the related processing. The former is the same as the case where an encryption library module is stored in the memory as not the IP core but the usual software module and can be considered similar to the case where the functions are realized as the hardware. On the other hand the latter is referred to as tamper resistant software. Even if the execution situation is deciphered by the ICE debugger the execution sequence of the tasks is scattered in this case tasks are divided so that the a divided task has a meaning as a program that is no influence will be exerted upon the lines before and after that and the tasks per se are encrypted so one type of secure processing can be realized similar to a task scheduler MiniOS . The related task scheduler is buried in the target program.

As shown in the decryption and or expansion module has the mutual certification unit decryption unit decryption unit expansion unit electronic watermark information processing unit and the half disclosure processing unit .

The mutual certification unit performs the mutual certification with the mutual certification unit shown in when the decryption and or expansion module receives as its input the data from the SAM and produces the session key data K.

The decryption unit decrypts the content key data Kc half disclosure parameter data user watermark use data and the content data C input from the SAM by using the session key data K. Then the decryption unit outputs the decrypted content key data Kc and the content data C to the decryption unit outputs the decrypted user watermark use data to the electronic watermark information processing unit and outputs the half disclosure parameter data to the half disclosure processing unit .

The decryption unit decrypts the content data C in the half disclosure mode by using the content key data Kc under the control from the half disclosure processing unit and outputs the decrypted content data C to the expansion unit .

The expansion unit expands the decrypted content data C and outputs the same to the electronic watermark information processing unit .

The expansion unit performs the expansion processing by using the A V expansion use software stored in the content file CF shown in and performs the expansion processing by for example the ATRAC3 method.

The electronic watermark information processing unit buries the user watermark in accordance with decrypted user watermark use data in the decrypted content data C and produces new content data C. The electronic watermark information processing unit outputs the related new content data C to the reproduction module .

In this way the user watermark is buried at the decryption and or expansion module when reproducing the content data C.

Note that in the present invention it is also possible if the user watermark use data is not buried in the content data C.

The half disclosure processing unit instructs the blocks not to be decrypted and the blocks to be decrypted in for example the content data C to the decryption unit based on the half disclosure parameter data .

Also the half disclosure processing unit performs the control such as limiting the reproduction function at the time of a demo or the demo period based on the half disclosure parameter data .

The reproduction module performs the reproduction in accordance with the decrypted and expanded content data C 

Next an explanation will be made of the data format when transmitting and receiving data with the signature data produced by using the secret key data attached thereto and the certificate data among the content provider EMD service center and the user home network .

In this case a module Modencrypted by the session key data Kobtained by the mutual certification between the content provider and the SAM is transmitted from the content provider to the SAM .

In the module Mod the certificate data CERstoring the secret key data Kof the content provider the signature data SIGbased on the secret key data Kwith respect to the certificate data CER and the data Data to be transmitted are stored.

In this way by transmitting the module Modstoring the certificate data CERfrom the content provider to the SAM when verifying the signature data SIGat the SAM it becomes unnecessary to transmit the certificate data CERfrom the EMD service center to the SAM .

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual certification between the content provider and the SAM is transmitted from the content provider to the SAM .

In the module Mod the data Data to be transmitted and the signature data SIGby the secret key data Kthereof are stored.

Further a module Modshown in encrypted by the session key data Kobtained by the mutual certification between the EMD service center and the SAM is transmitted from the EMD service center to the SAM .

In the module Mod the certificate data CERof the content provider and the signature data SIGby the secret key data Kthereof are stored.

In this case a module Modencrypted by the session key data Kobtained by the mutual certification between the content provider and the SAM is transmitted from the SAM to the content provider .

In the module Mod the certificate data CERstoring the secret key data Kof the SAM the signature data SIGby the secret key data Kwith respect to the certificate data CER and the data Data to be transmitted are stored.

In this way by transmitting the module Modstoring the certificate data CERfrom the SAM to the content provider when verifying the signature data SIGin the content provider it becomes unnecessary to transmit the certificate data CERfrom the EMD service center to the content provider .

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual certification between the content provider and the SAM is transmitted from the SAM to the content provider .

In the module Mod the data Data to be transmitted and the signature data SIGby the secret key data Kthereof are stored.

Also from the EMD service center to the content provider a module Modshown in encrypted by session key data Kobtained by the mutual certification between the EMD service center and the content provider is transmitted.

In the module Mod the certificate data CERof the SAM and the signature data SIGby the secret key data Kthereof are stored.

In this case a module Modencrypted by the session key data Kobtained by the mutual certification between the content provider and the EMD service center is transmitted from the content provider to the EMD service center .

In the module Mod the certificate data CERstoring the secret key data Kof the content provider the signature data SIGby the secret key data Kwith respect to the certificate data CER and the data Data to be transmitted are stored.

In this case from the content provider to the EMD service center a module Modshown in encrypted by the session key data Kobtained by the mutual certification between the content provider and the EMD service center is transmitted.

In the module Mod the data Data to be transmitted and the signature data SIGby the secret key data Kthereof are stored.

At this time the certificate data CERof the content provider has been already registered in the EMD service center .

In this case a module Modencrypted by the session key data Kobtained by the mutual certification between the EMD service center and the SAM is transmitted from the SAM to the EMD service center .

In the module Mod the certificate data CERstoring the secret key data Kof the SAM the signature data SIGby the secret key data Kwith respect to the certificate data CERand the data Data to be transmitted are stored.

In this case a module Modshown in encrypted by the session key data Kobtained by the mutual certification between the EMD service center and the SAM is transmitted from the SAM to the EMD service center .

In the module Mod the data Data to be transmitted and the signature data SIGby the secret key data Kthereof are stored.

At this time in the EMD service center the certificate data CERof the SAM has been already registered.

Below an explanation will be made of the registration processing in the EMD service center at the time of shipment of the SAMs to .

Note that the registration processings of the SAMs to are the same so the registration processing of the SAM will be mentioned below.

At the time of shipment of the SAM by the key server of the EMD service center shown in the key data shown below is initially registered in the storage unit shown in etc. via the SAM management unit .

Further in the SAM for example at the time of shipment the program etc. used when accessing the EMD service center by the SAM the first time are stored in the storage unit etc.

Namely in the storage unit for example the identifier SAM ID of the SAM given an at the left side in storage use key data K public key data Kof the route certificate authority public key data Kof the EMD service center secret key data Kof the SAM certificate data CERand the signature data SIGthereof and the original key data for creating the certification use key data between the decryption and or expansion module and the media SAM are stored by the initial registration.

Note that it is also possible to transmit the certificate data CERfrom the EMD service center to the SAM when registering the same after the time of shipment of the SAM .

Also in the storage unit at the time of shipment of the SAM a file reader indicating the reading format of the content file CF and the key file KF shown in is written by the EMD service center .

In the SAM when utilizing the data stored in the content file CF and the key file KF the file reader stored in the storage unit is used.

Here the public key data Kof the route certificate authority uses an RSA generally used in electronic commercial transactions over the Internet and has a data length of for example 1024 bits. The public key data Kis issued by the route certificate authority shown in .

Also the public key data Kof the EMD service center is produced by utilizing an elliptical curve code having a short data length and a power equivalent to the RSA or more. Its data length is for example 160 bits. Note when considering the power of the encryption desirably the public key data Khas 192 bits or more. Further the EMD service center registers the public key data Kin the route certificate authority .

Also the route certificate authority produces the certificate data CERof the public key data K. The certificate data CERstoring the public key data Kis preferably stored in the storage unit at the time of shipment of the SAM . In this case the certificate data CERis signed by a secret key data Kof the route certificate authority .

The EMD service center produces the secret key data Kof the SAM by generating a random number and produces the public key data forming a pair together with this.

Also the EMD service center is given the certification of the route certificate authority issues the certificate data CERof the public key data Kand attaches the signature data to this by using its own secret key data K. Namely the EMD service center achieves the function of a second CA certificate authority .

Also the unique identifier SAM ID under the management of the EMD service center is allocated to the SAM by the SAM management unit of the EMD service center shown in . This is stored in the storage unit of the SAM and at the same time stored also in the SAM database shown in and managed by the EMD service center .

Also the SAM is connected to and registered at the EMD service center by for example the user after the time of shipment. At the same time the distribution use public key data KDto KDare transferred from the EMD service center to the storage unit .

Namely the user utilizing the SAM must perform a registration procedure at the EMD service center before downloading the content. This registration procedure is carried out off line by for example mail by the user himself giving information specifying himself by using for example a registration card attached when purchasing the apparatus with the SAM mounted thereon in the related example network apparatus .

The EMD service center issues the identifier USER ID inherent to the user in accordance with the registration procedure of the SAM by the user manages the correspondence between the SAM ID and the USER ID in for example the SAM database shown in and utilizes the same at the time of charging.

Also the EMD service center allocates the information reference use identifier ID and the password used at the first time to the user of the SAM and notifies this to the user. The user can make an inquiry about information for example the usage situation usage log of the content data up to the present at the EMD service center by using the information reference use identifier ID and the password.

Also the EMD service center confirms the identity of the user at the credit card company or the like or confirms the user off line at the time of registration of the user.

Next as shown in an explanation will be made of the procedure for storing the SAM registration list in the storage unit inside the SAM .

The SAM shown in acquires the SAM registration list of the SAMs to existing in its own system by utilizing a topology map produced when powering up apparatuses connected to the bus and connecting new apparatuses to the bus where for example the IEEE1394 serial bus is used as the bus .

Note that the topology map produced in accordance with the IEEE1394 serial bus that is the bus is produced for the SAMs to and SCMS processing circuits and when for example as shown in in addition to the SAMs to SCMS processing circuits and of AV apparatus and are connected to the bus .

Accordingly the SAM extracts the information for the SAMs to from the related topology map and produces the SAM registration list shown in .

Then the SAM registers the SAM registration list shown in in the EMD service center and acquires the signature.

These processings are automatically carried out by the SAM by utilizing the session of the bus . The registration instruction of the SAM registration list is issued to the EMD service center .

The EMD service center confirms the expiration date when receiving the SAM registration list shown in from the SAM . Then the EMD service center sets up the corresponding portion by referring to the existence of the settlement function designated by the SAM at the time of registration. Further the EMD service center checks the revocation list and sets a revocation flag in the SAM registration list. The revocation list is the list of the SAMs for which usage is prohibited invalid by the EMD service center for the reason of for example illegitimate usage.

Also the EMD service center extracts the SAM registration list corresponding to the SAM at the time of settlement and confirms if the SAM described therein is contained in the revocation list. Further the EMD service center attaches the signature to the SAM registration list.

Note that the SAM revocation list is produced aimed at only the SAMs of the identical system connected to the identical bus and the validity and invalidity of the related SAMs are indicated by the revocation flag corresponding to each SAM.

Step S The EMD service center transmits the certificate data CERof the public key data Kof the content provider to the content provider after the content provider goes through the predetermined registration processing.

Also the EMD service center transmits the certificate CERto CERof the public key data Kto Kof the SAMs to to the SAMs to after the SAMs to pass through the predetermined registration processing.

Also the EMD service center transmits three months worth of the distribution use key data KDto KDeach having the expiration date of one month to the SAMs to of the user home network after the mutual certification.

In this way in the EMD system the distribution use key data KDto KDare distributed to the SAMs to in advance. Therefore even in the state where the space between the SAMs to and the EMD service center is off line the secure container distributed from the content provider can be decrypted and purchased and used in the SAMs to . In this case the log of the related purchase and or usage is described in the usage log data and the usage log data is automatically transmitted to the EMD service center when the SAMs to and the EMD service center are connected. Therefore the settlement processing in the EMD service center can be reliably carried out. Note that a SAM for which usage log data cannot be collected by the EMD service center in a predetermined period is regarded as being invalidated by the revocation list.

Note that the usage control status data is transmitted from the SAMs to to the EMD service center in real time in principle.

Step S The content provider transmits the right registration request module Modshown in to the EMD service center after the mutual certification.

Then the EMD service center registers and authenticates the usage control policy data and the content key data Kc after the predetermined signature verification.

Also the EMD service center produces six months worth of the key files KF in accordance with the registration use module Modand transmits them to the content provider .

Step S The content provider produces the content files CF and the signature data SIGthereof and the key file KF and the signature data SIGthereof shown in and distributes the secure container storing them and the certificate data CERand the signature data SIGthereof shown in to the SAMs to of the user home network on line and or off line.

In the on line case the content provider use transport protocol is used. The secure container is transported from the content provider to the user home network in a form not depending upon the related protocol namely as data transmitted by using a predetermined layer of communication protocol comprised of a plurality of layers . Also in the off line case the secure container is transported from the content provider to the user home network in the state stored in a ROM type or RAM type storage medium.

Step S The SAMs to SAM of the user home network verify the signature data SIG SIG and SIGin the secure container distributed from the content provider and confirm the legitimacy of the producer and transmitter of the content file CF and the key file KF then decrypt the key file KF by using the distribution use data KDto KDof the corresponding period.

Step S In the SAMs to the purchase and or usage form is determined based on the operation signal S in accordance with the operation of the purchase and or usage form determination operation unit shown in by the user.

At this time in the usage monitor unit shown in the purchase and or usage form of the content file CF by the user is managed based on the usage control policy data stored in the secure container .

Step S In the charge processing unit shown in of the SAMs to the usage log data and the usage control status data describing the operation of the settlement of the purchase and or usage form by the user are produced based on the operation signal S and are transmitted to the EMD service center .

Step S The EMD service center performs the settlement processing based on the usage log data in the settlement processing unit shown in and produces the settlement claim data and the settlement report data . The EMD service center transmits the settlement claim data and the signature data SIGthereof via the payment gateway shown in to the settlement manager . Further the EMD service center transmits the settlement report data to the content provider .

Step S In the settlement manager after verifying the signature data SIG based on the settlement claim data the money paid by the user is distributed to the owner of the content provider .

As explained above in the EMD system the secure container of the format shown in is distributed from the content provider to the user home network and the processing for the key file KF in the secure container is carried out in the SAMs to .

Also the content key data Kc and the usage control policy data stored in the key file KF have been encrypted by using the distribution use key data KDto KDand decrypted inside only the SAMs to holding the distribution use key data KDto KD. Then in the SAMs to the purchase form and the usage form of the content data C are determined based on a module having tamper resistance and the handling content of the content data C described in the usage control policy data .

Accordingly according to the EMD system the purchase and usage of the content data C in the user home network can be reliably carried out based on the content of the usage control policy data produced by the interested parties of the content provider .

Also in the EMD system by distributing the content data C from the content provider to the user home network by using the secure container in both of the cases of on line and off line the rights clearing of the content data C in the SAMs to can be shared in both cases.

Also in the EMD system when purchasing using recording and transferring the content data C in the network apparatus and the AV apparatuses to in the user home network by performing processing always based on the usage control policy data common rights clearing rule can be employed.

As shown in in the multi processor system as the protocol for transporting the secure container from the content provider to the user home network use is made of for example TCP IP and XML SMIL.

Also as the protocol for transferring the secure container between SAMs of the user home network and the protocol for transferring the secure container between the user home networks and use is made of for example XML SMIL constructed in the 1394 serial bus interface. Also in this case it is also possible to store the secure container in a ROM type or RAM type storage medium and transport the same between SAMs.

In the above embodiment as shown in the case where the key file KF was encrypted by using the distribution use key data KD in the EMD service center and the key file KF was decrypted by using the distribution use key data KD in the SAMs to was exemplified but the encryption of the key file KF using the distribution use key data KD does not always have to be carried out when the secure container is directly supplied from the content provider to the SAMs to as shown in .

In this way the encryption of the key file KF by using the distribution use key data KD has a large effect when suppressing illegitimate action by the service provider by giving the distribution use key data KD to only the content provider and the user home network when the content data is supplied from the content provider to the user home network via the service provider as in the second embodiment mentioned later.

Note also in the case of the first embodiment the encryption of the key file KF by using the distribution use key data KD has an effect in the point of raising the force of suppressing illegitimate usage of the content data.

Further in the above embodiment the case where the suggested retailer s price data SRP was stored in the usage control policy data in the key file KF shown in was exemplified but it is also possible to store the suggested retailer s price data SRP price tag data other than in the key file KF in the secure container . In this case signature data produced by using the secret key data Kis attached to the suggested retailer s price data SRP.

In the first embodiment as shown in the case where the EMD service center performed the settlement processing in the settlement manager via the payment gateway by using the settlement claim data produced by itself was exemplified but it is also possible to transmit for example the settlement claim data from the EMD service center to the content provider as shown in and have the content provider itself perform the settlement processing at the settlement manager via the payment gateway by using the settlement claim data .

In the first embodiment the case where the secure container was supplied from a single content provider to the SAMs to of the user home network was exemplified but it is also possible to supply secure containers and from two or more content providers and to the SAMs to .

In this case the EMD service center distributes key files KFato KFaand KFbto KFbencrypted by using six months worth of distribution use key data KDato KDaand KDbto KDbto the content providers and

Also the EMD service center distributes three months worth of distribution use key data KDato KDaand KDbto KDbto the SAMs to .

Then the content provider supplies a secure container storing a content file CFa encrypted by using unique content key data Kca and key files KFato

KFaof the corresponding period received from the EMD service center to the SAMs to on line and or off line.

At this time as the identifier of a key file use is made of the global unique identifier content ID distributed by the EMD service center . The content data is centrally managed by the EMD service center .

Also the content provider supplies a secure container storing a content file CFb encrypted by using unique content key data Kcb and key files KFbto

KFbof the corresponding period received from the EMD service center to the SAMs to on line and or off line.

The SAMs to decrypt the secure container by using the distribution use key data KDato KDaof the corresponding period determine the purchase form of the content after passing through the predetermined signature verification processing etc. and transmit usage log data and usage control status data produced in accordance with the related determined purchase form and usage form to the EMD service center .

Also the SAMs to decrypt the secure container by using the distribution use key data KDbto KDbof the corresponding period determine the purchase form of the content after passing through the predetermined signature verification processing etc. and transmit usage log data and usage control status data produced in accordance with the related determined purchase form and usage form to the EMD service center .

In the EMD service center based on the usage log data settlement claim data for the content provider is produced and settlement processing is carried out at the settlement manager using this.

Also in the EMD service center settlement claim data for the content provider is produced based on the usage log data and settlement processing is carried out at the settlement manager using this.

Also the EMD service center registers and authenticates the usage control policy data and . At this time the EMD service center distributes the global unique identifier content ID for the key files KFa and KFb corresponding to the usage control policy data and

Also the EMD service center issues certificate data CERand CERof the content providers and and attaches signature data SIGand SIGto them to verify their legitimacy.

In the above embodiment the case where the content files CF and the key files KF were stored in the secure container with directory structures and transmitted from the content provider to the SAMs to was exemplified but it is also possible to separately transmit the content files CF and the key file KF to the SAMs to .

In the first technique as shown in the content files CF and the key files KF are separately transmitted from the content provider to the SAMs to in a format not depending upon the communication protocol.

Also in the second technique as shown in the content files CF are transmitted from the content provider to the SAMs to in a format not depending upon the communication protocol and at the same time the key files KF are transmitted from the EMD service center to the SAMs to . The related key files KF are transmitted from the EMD service center to the SAMs to when for example the users of the SAMs to are about to determine the purchase form of the content data C.

When the first technique and the second technique are employed a link is established between related content files CF and between the content files CF and the key files KF corresponding to them by using hyper link data stored in the header of at least one of the content file CF and the key file KF. In the SAMs to the rights clearing and the usage of the content data C are carried out based on the related link.

Note that in the present modification as the formats of the content file CF and the key file KF for example those shown in are employed.

Also in this case preferably together with the content file CF and the key file KF the signature data SIGand SIGthereof are transmitted.

In the above embodiment the case where the content file CF and the key file KF were separately provided in the secure container was exemplified but for example it is also possible to store the key file KF in the content file CF in the secure container as shown in .

In this case the signature data by the secret key data Kof the content provider is attached to the content file CF storing the key file KF.

In the above embodiment the case where the content data C was stored in the content file CF and the content key data Kc and the usage control policy data were stored in the key file KF and transmitted from the content provider to the SAM or the like was exemplified but it is also possible to transmit at least one among the content data C content key data Kc and the usage control policy data from the content provider to the SAM or the like without employing the file format and in a format not depending upon the communication protocol.

For example as shown in it is also possible if a secure container storing the key file KF containing the content data C encrypted by the content key data Kc the encrypted content key data Kc the encrypted usage control policy data etc. is produced in the content provider and the secure container is transmitted to the SAM etc. in a format not depending upon the communication protocol.

Also as shown in it is also possible to individually transmit the key file KF containing the content data C encrypted by the content key data Kc encrypted content key data Kc the encrypted usage control policy data and so on from the content provider to the SAM etc. in a format not depending upon the communication protocol. Namely the content data C is transmitted by an identical route to the key file KF without employing the file format.

Also as shown in it is also possible if the content data C encrypted by the content key data Kc is transmitted from the content provider to the SAM etc. in a format not depending upon the communication protocol and at the same time the key file KF containing the encrypted content key data Kc and the encrypted usage control policy data etc. is transmitted from the EMD service center to the SAM etc. Namely the content data C is transmitted by a different route from that for the key file KF without employing the file format.

Also as shown in it is also possible if the content data C encrypted by the content key data Kc the content key data Kc and the usage control policy data are transmitted from the content provider to the SAM etc. in a format not depending upon the communication protocol. Namely the content data C content key data Kc and the usage control policy data are transmitted by the identical route without employing the file format.

Also as shown in it is also possible if the content data C encrypted by the content key data Kc is transmitted from the content provider to the SAM etc. in a format not depending upon the communication protocol and at the same time the content key data Kc and the usage control policy data are transmitted from the EMD service center to the SAM etc. Namely the content data C content key data Kc and the usage control policy data are transmitted by different routes without employing the file format.

In the above embodiment the case where the content data was directly distributed from the content provider to the SAMs to of the user home network was exemplified but in the present embodiment an explanation will be made of a case where the content data provided by the content provider is distributed to a SAM of the user home network via the service provider.

As shown in the EMD system has a content provider an EMD service center the user home network a service provider the payment gateway and the settlement manager .

The content provider EMD service center SAMs to and the service provider correspond to the data providing apparatus management device data processing apparatus and the data distribution apparatus according to claim and claim etc.

The content provider is the same as the content provider of the first embodiment except for the point that it supplies the content data to the service provider .

Also the EMD service center is the same as the EMD service center of the first embodiment except for the point that the certificate authority function key data management function and the rights clearing function are provided also to the service provider in addition to the content provider and SAMs to .

Also the user home network has a network apparatus and AV apparatuses to . The network apparatus includes a SAM and a CA module and the AV apparatuses to include the SAMs to .

Here the SAMs to are the same as the SAMs to of the first embodiment except for the point that they are distributed a secure container from the service provider and the point that they perform the verification processing of the signature data and the preparation of an SP use purchase log data data distribution device use purchase log data for the service provider in addition to the content provider .

In the EMD system the content provider transmits the usage control policy UCP data in the same way as that of the first embodiment mentioned before indicating the rights contents such as the usage permission condition of the content data C of the content to be provided by itself and the content key data Kc to the EMD service center as the authority manager having a high reliability. The usage control policy data and the content key data Kc are registered and authenticated certified in the EMD service center .

Also the content provider encrypts the content data C by the content key data Kc and produces the content file CF. Also the content provider receives six months worth of the key files KF for the content files CF from the EMD service center .

In the related key file KF the signature data for verifying the existence of tampering of the related key file KF and the legitimacy of the producer and the transmitter of the related key file KF is stored.

Then the content provider supplies the secure container shown in storing the content file CF key file KF and its own signature data to the service provider by using a network such as the Internet digital broadcast storage medium or informal protocol or off line or the like.

Also the signature data stored in the secure container is used for verifying the existence of tampering of the corresponding data and the legitimacy of the producer and transmitter of the related data.

When receiving the secure container from the content provider the service provider verifies the signature data and confirms the producer and the transmitter of the secure container .

Next the service provider produces price tag data PT indicating the price obtained by adding a price for service such as authoring performed by itself to the price SRP for the content intended by the content provider notified for example off line.

Then the service provider produces the secure container storing the content file CF and key file KF extracted from the secure container price tag data and the signature data by its own secret key data Kwith respect to them.

At this time the key file KF has been encrypted by the distribution use key data KDto KD and the service provider does not hold the related distribution use key data KDto KD therefore the service provider cannot see or rewrite the content of the key file KF.

The service provider distributes the secure container to the user home network on line and or off line.

At this time in the case of off line the secure container is stored in the ROM type storage medium or the like and supplied to the SAMs to as it is. On the other hand in the case of on line mutual certification is carried out between the service provider and the CA module the secure container is encrypted by using the session key data Kin the service provider and transmitted and the secure container received at the CA module is decrypted by using the session key data Kand then transferred to the SAMs to .

In this case as the communication protocol for transmitting the secure container from the content provider to the user home network an MHEG Multimedia and Hypermedia Information Coding Experts Group protocol is used in the case of a digital broadcast and XML SMIL HTML Hyper Textmarkup Language is used in the case of the Internet. In these communication protocols the secure container is buried by tunneling in a format not depending upon the related communication protocol encoding method or the like .

Accordingly it is not necessary to ensure compatibility of the format between the communication protocol and the secure container so the format of the secure container can be flexibly set.

Next in the SAMs to the signature data stored in the secure container is verified and the legitimacy of producers and transmitters of the content file CF and the key file KF stored in the secure container is confirmed. Then in the SAMs to when the related legitimacy is confirmed the key file KF is decrypted by using the distribution use data KDto KDof the corresponding period distributed from the EMD service center .

The secure container supplied to the SAMs to is reproduced and recorded into the storage medium after the purchase and or usage form is determined in accordance with the operation of the user in the network apparatus and the AV apparatuses to .

The SAMs to store the log of the purchase and or usage of the secure container as the usage log data .

A usage log data log data or the management device use log data is transmitted from the user home network to the EMD service center in response to for example a request from the EMD service center .

Also the SAMs to transmit the usage control status UCS data indicating the related purchase form to the EMD service center when the purchase form of the content is determined.

The EMD service center determines calculates the charge content for each of the content provider and the service provider based on the usage log data and performs settlement at the settlement manager such as a bank via the payment gateway based on the results. By this the money paid by the user of the user home network is distributed to the content provider and the service provider by the settlement processing by the EMD service center .

In the present embodiment the EMD service center has the certificate authority function key data management function and the rights clearing profit distribution function.

Namely the EMD service center functions as a second certificate authority with respect to the route certificate authority as the highest authority manager at the neutral position and verifies the legitimacy of the related public key data by attaching a signature by the secret key data of the EMD service center to the certificate data of the public key data to be used for the verification processing of the signature data in the content provider service provider and the SAMs to . Further as mentioned before also the registration and authentication of the usage control policy data of the content provider content key data Kc and the price tag data of the service provider are achieved by the certificate authority function of the EMD service center .

Also the EMD service center has a key data management function for performing for example management of the key data of the distribution use key data KDto KD.

Also the EMD service center has a rights clearing profit distribution function of performing settlement with respect to the purchase and or usage of the content by the user of the user home network based on the usage control policy data registered by the content provider the usage log data input from the SAMs to and the price tag data registered by the service provider and distributing and paying the money paid by the user to the content provider and the service provider .

As shown in the content provider has a content master source server electronic watermark information addition unit compression unit encryption unit random number generation unit signature processing unit secure container preparation unit secure container database key file database storage unit mutual certification unit encryption and or decryption unit usage control policy data preparation unit EMD service center management unit and a service provider management unit .

In components given the same reference numerals as those of are the same as the components of the same reference numerals explained in the first embodiment referring to and .

Namely the content provider has a configuration providing the service provider management unit in place of the SAM management unit shown in .

The service provider management unit provides the secure container shown in input from the secure container preparation unit to the service provider shown in off line and or on line.

Where the secure container shown in is distributed to the service provider on line the service provider management unit encrypts the secure container by using the session key data Kin the encryption and or decryption unit and then distributes the same via the network to the service provider .

Also the flow of the data in the content provider shown in similarly applies also to the content provider .

Below an explanation will be made of the flow of the processing when transmitting the secure container from the content provider to the service provider .

Step C The session key data Kobtained by the mutual certification at step C is shared between the content provider and the service provider .

Step C By the service provider the secure container database possessed by the content provider for CP is accessed.

Step C The service provider selects the secure container necessary for its distribution service by referring to for example the lists of the content ID and the meta data centrally managed at the secure container database

Step C The content provider encrypts the secure container selected at step C by using the session key data Kshared at step C.

Step C The content provider inserts the secure container obtained at step C into a content provider use commodity transport protocol.

Step C The service provider takes out the secure container from the content provider use commodity transport protocol.

Step C The service provider decrypts the secure container by using the session key data Kshared at step C.

Step C The service provider verifies the signature data stored in the decrypted secure container to confirm the legitimacy of the transmitter and performs the processing of step C under the condition that the transmitter is legitimate.

The service provider produces the secure container storing the content file CF and the key file KF in the secure container received from the content provider and the price tag data produced by itself and distributes the secure container to the network apparatus and the AV apparatuses to of the user home network on line and or off line.

The service format of the content distribution by the service provider is roughly classified to an independent type service and a linked type service.

The independent type service is for example a service dedicated to download for individually distributing the content. Further the linked type service is a service for distributing content linked to the program and CMs advertisements . For example content such as a theme song and other song of a drama are stored in a stream of the drama program. The user can purchase the content such as theme song or other song existing in the stream when watching the drama program.

Note that in the flow of the data when supplying the secure container produced by using the secure container supplied from the content provider to the user home network is shown.

As shown in the service provider has a content provider management unit a storage unit a mutual certification unit an encryption and or decryption unit a signature processing unit a secure container preparation unit a secure container database a price tag data preparation unit a user home network management unit an EMD service center management unit and a user preference filter generation unit .

Below an explanation will be made of the flow of the processing in the service provider when creating the secure container from the secure container supplied from the content provider and distributing this to the user home network by referring to and .

The content provider management unit receives the secure container shown in from the content provider on line and or off line and writes the secure container into the storage unit .

At this time the content provider management unit decrypts the secure container in the encryption and or decryption unit by using the session key data Kobtained by mutual certification between the mutual certification unit shown in and the mutual certification unit shown in in the case of on line and then writes the same into the storage unit .

Note that the service provider can have a dedicated secure container database for storing the secure container separately from the storage unit .

Next in the signature processing unit the signature data SIGshown in of the secure container stored in the storage unit is verified by using the public key data Kof the EMD service center read out from the storage unit . After the legitimacy thereof is confirmed the public key data Kis extracted from the certificate data CERshown in .

Next the signature processing unit verifies the signature data SIGand SIGshown in of the secure container stored in the storage unit that is verifies the legitimacy of the producer and transmitter of the content file CF and the transmitter of the key file KF by using the related extracted public key data

Also the signature processing unit verifies the signature data SIGstored in the key file KF shown in by using the public key data Kread out from the storage unit that is verifies the legitimacy of the producer of the key file KF. At this time the verification of the signature data SIGserves also as the verification of whether or not the key file KF is registered in the EMD service center .

Next the secure container preparation unit reads out the content file CF and the signature data SIGthereof the key file KF and the signature data SIGthereof the certificate data CERof the service provider and the signature data SIGthereof and the certificate data CERof the content provider and the signature data SIGthereof from the storage unit when the legitimacy of the signature data SIG SIGand SIGis confirmed.

Also the price tag data preparation unit produces price tag data indicating the price obtained by adding the price of its own service to the price for the content requested by the content provider notified from for example the content provider off line and stores this in the storage unit .

Also the signature processing unit obtains the hash values of the content file CF key file KF and the price tag data produces signature data SIG SIG and SIGby using secret key data Kof the service provider and outputs them to the secure container preparation unit .

Here the signature data SIGis used for verifying the legitimacy of the transmitter of the content file CF the signature data SIGis used for verifying the legitimacy of the transmitter of the key file KF and the signature data SIGis used for verifying the legitimacy of the producer and transmitter of the price tag data .

Next the secure container preparation unit produces the secure container storing the content file CF and the signature data SIGand SIGthereof the key file KF and the signature data SIGand SIGthereof the price tag data and the signature data SIGthereof the certificate data CERand the signature data SIGthereof and the certificate data CERand the signature data SIGthereof as shown in and stores the same in the secure container database

The secure containers stored in the secure container database are centrally managed by the service provider by using for example content IDs.

The secure container preparation unit reads out the secure container in response to the request from the user home network from the secure container database and outputs this to the user home network management unit .

At this time the secure container may be a composite container storing a plurality of content files CF and a plurality of key files KF corresponding to them too. For example it is also possible to store a plurality of content files CF concerning a song a video clip a text card liner notes and a jacket in a single secure container . It is also possible if these plurality of content files CF etc. are stored in the secure container with a directory structure.

Also where the secure container is transmitted in a digital broadcast an MHEG Multimedia and Hypermedia Information Coding Experts Group protocol is used while where it is transmitted by the Internet an XML SMIL HTML Hyper Text Markup Language protocol is used.

At this time the content files CF and the key files KF etc. in the secure container are stored in predetermined layers in the communication protocol employed between the service provider and the user home network in a format not depending upon the encoding method tunneling the protocols of MHEG and HTML.

For example where the secure container is transmitted in a digital broadcast as shown in the content file CF is stored as the MHEG content data in the MHEG object.

Also in the transport layer protocol the MHEG object is stored in PES packetized elementary stream Video in the case of a moving picture image stored in the PES Audio in the case of audio and stored in Private Data in the case of a still image.

Also as shown in the key file KF price tag data and the certificate data CERand CERare stored in an ECM entitlement control message in TS Packet of the transport layer protocol.

Here a mutual link is established among the content file CF key file KF price tag data and the certificate data CERand CERby the directory structure data DSDin the header of the content file CF.

Next the user home network management unit supplies the secure container to the user home network off line and or on line.

Where the secure container is to be distributed to the network apparatus of the user home network on line the user home network management unit encrypts the secure container by using the session key data Kin the encryption and or decryption unit after the mutual certification and then distributes the same via the network to the network apparatus .

Note that where the secure container is to be broadcasted via for example a satellite the user home network management unit encrypts the secure container by using scramble key data Kor the like. Further scramble key data Kis encrypted by using work key data K and the work key data Kis encrypted by using master key data K.

Then the user home network management unit transmits scramble key data Kand the work key data Ktogether with the secure container to the user home network via the satellite.

Also for example it stores the master key data Kin the IC card or the like and distributes the same to the user home network off line.

Also when receiving the SP use purchase log data concerning the content data C distributed by the related service provider from the user home network the user home network management unit writes this into the storage unit .

The service provider refers to the SP use purchase log data when determining the service content in the future. Further the user preference filter generation unit analyzes the preference of the users of the SAMs to transmitting the related SP use purchase log data based on the SP use purchase log data to produce user preference filter data and transmits this via the user home network management unit to the CA module of the user home network .

In the flow of the data related to the communication with the EMD service center in the service provider is shown.

Note that as the prerequisite of performing the following processing the interested party of the service provider performs registration processing at the EMD service center off line by using for example its own ID card and a bank account for performing the settlement processing and acquires the global unique identifier SP ID. The identifier SP ID is stored in the storage unit .

First an explanation will be made of the processing where the service provider requests the certificate data CERfor certifying the legitimacy of the public key data Kcorresponding to its own secret key data Kat the EMD service center by referring to .

The service provider generates a random number by using the true random number generator to produce the secret key data Kproduces the public key data Kcorresponding to the related secret key data K and stores the same in the storage unit .

The identifiers SP ID and the public key data Kof the EMD service center management unit and the service provider are read out from the storage unit .

Then the EMD service center management unit transmits the identifier SP ID and the public key data Kto the EMD service center .

Then the EMD service center management unit receives as its inputs the certificate data CERand the signature data SIGthereof from the EMD service center in accordance with the related registration and writes the same into the storage unit .

Next an explanation will be made of the processing of the case where the service provider registers and authenticates the price tag data in the EMD service center by referring to .

In this case in the signature processing unit the hash value of a module Modshown in storing the price tag data read out from the storage unit and the content ID as the global unique identifier is found and signature data SIGis produced by using the secret key data K.

Then after encrypting a price tag registration request use module Modshown in by using the session key data Kobtained by the mutual certification between the mutual certification unit and the EMD service center in the encryption and or decryption unit it is transmitted from the EMD service center management unit to the EMD service center .

Note that it is also possible if the global unique identifier SP ID of the service provider is stored in the module Mod.

Also the EMD service center management unit writes a settlement report data received from the EMD service center into the storage unit .

Also the EMD service center management unit stores marketing information data received from the EMD service center in the storage unit .

The marketing information data is used as a reference when the service provider determines the content data C to be distributed from then on.

The EMD service center functions as the certificate authority CA key management authority and the rights clearing authority as mentioned before.

As shown in the EMD service center has a key server a key database a KF preparation unit a settlement processing unit a signature processing unit a settlement manager management unit a certificate and usage control policy management unit a CER database a certificate database a content provider management unit a CP database a SAM management unit a SAM database a mutual certification unit an encryption and or decryption unit a service provider management unit an SP database a content ID preparation unit a user preference filter generation unit and a marketing information data generation unit .

In the functional blocks given the same reference numerals as those of and have substantially the same functions as those of the functional blocks having the same reference numerals explained in the first embodiment.

Note that in the flow of the data related to the data transmitted and received between the EMD service center and the service provider in the flow of the data among the functional blocks in the EMD service center is shown.

Further in the flow of the data related to the data transmitted and received between the EMD service center and the content provider in the flow of the data among the functional blocks in the EMD service center is shown.

Further in the flow of the data related to the data transmitted and received between the EMD service center and the SAMs to shown in and the settlement manager in the flow of the data among the functional blocks in the EMD service center is shown.

The settlement processing unit performs the settlement processing based on the usage log data input from the SAMs to and the suggested retailer s price data SPR and the price tag data input from the certificate and usage control policy management unit as shown in . Note that at this time the settlement processing unit monitors the existence of dumping etc. by the service provider .

The settlement processing unit produces settlement report data and settlement claim data for the content provider as shown in by the settlement processing and outputs them to the content provider management unit and the settlement manager management unit .

Also by the settlement processing as shown in and the settlement report data and settlement claim data for the service provider are produced and are output to the service provider management unit and the settlement manager management unit .

Here the settlement claim data and are authenticated data enabling claim of payment of money to the settlement manager based on the related data.

Here the usage log data is used when determining the payment of the license fee related to the secure container in the same way as the usage log data explained in the first embodiment. In the usage log data for example as shown in the identifier of the content data C stored in the secure container that is the content ID the identifier CP ID of the content provider providing the content data C stored in the secure container the identifier SP ID of the service provider distributing the secure container signal parameter data of the content data C the compression method of the content data C in the secure container the identifier Media ID of the storage medium storing the secure container the identifiers SAM ID of the SAMs to receiving the distribution of the secure container the USER IDs of the users of the related SAMs to etc. are described. Accordingly in a case where the money paid by the user of the user home network must be distributed to the license owners of for example the compression method and the storage medium other than the owners of the content provider and the service provider the EMD service center determines the sum of money to be paid to the other parties based on the distribution rate table determined in advance and produces the settlement report data and settlement claim data in accordance with the related determination.

The certificate and usage control policy management unit reads out the certificate data CER certificate data CER the certificate data CERto CER etc. registered and authenticated in the certificate database and at the same time registers and authenticates the usage control policy data and content key data Kc of the content provider the price tag data of the service provider etc. in the CER database

At this time the certificate and usage control policy management unit obtains the hash values of the usage control policy data content key data Kc the price tag data etc. attaches the signature data using the secret key data K and produces the authenticated certificate data.

The content provider management unit has a function of communicating with the content provider and can access the CP database for managing the registered identifier CP ID etc. of the content provider .

The user preference filter generation unit produces user preference filter data for selecting the content data C in accordance with the preference of the users of the SAMs to transmitting the related usage log data based on the usage log data and transmits the user preference filter data to the SAMs to transmitting the related usage log data via the SAM management unit .

The marketing information data generation unit produces the marketing information data indicating the purchase situation etc. of the whole content data C distributed to the user home network by for example a plurality of service providers based on the usage log data and transmits this via the service provider management unit to the service provider . The service provider determines the content of the service to be provided from then on with reference to the marketing information data .

The distribution use key data KDto KDare transmitted from the EMD service center to the SAMs to in the same way as the case of the first embodiment.

Also the processing in the case where the EMD service center receives the issuance request of the certificate data from the content provider is the same as the first embodiment except for the point that the certificate and usage control policy management unit accesses the certificate database . Further the processing of registering the usage control policy data etc. is similar to the case of the first embodiment mentioned above except for the point that the certificate and usage control policy management unit stores the related data in the CER database

Next an explanation will be made of the processing in the case where the EMD service center receives the issuance request of the certificate data from the service provider by referring to .

In this case when receiving the identifier SP ID public key data Kand signature data SIGof the service provider given by the EMD service center in advance from the service provider the service provider management unit decrypts them by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in .

Then after confirming the legitimacy of the related decrypted signature data SIGat the signature processing unit it is confirmed whether or not the service provider issuing the issuance request of the related certificate data is registered in the SP database based on the identifier SP ID and the public key data K.

Then the certificate and usage control policy management unit reads out the certificate data CERof the related service provider from the certificate database and outputs the same to the service provider management unit .

Also the signature processing unit obtains the hash value of the certificate data CER produces the signature data SIGby using the secret key data of the EMD service center and outputs this to the service provider management unit .

Then the service provider management unit encrypts the certificate data CERand the signature data SIGthereof by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in and then transmits the same to the service provider .

Note that the processing where the EMD service center receives the issuance request of the certificate data from the SAMs to is similar to the first embodiment.

Further also the processing where the EMD service center receives the registration request of the usage control policy data and the content key data Kc from the content provider is similar to that of the first embodiment.

Further also the processing of preparing the key file KF in accordance with the registration use module Modreceived from the content provider by the EMD service center and transmitting the same to the content provider is similar to the first embodiment.

Next an explanation will be made of the processing where the EMD service center receives the registration request of the price tag data from the service provider by referring to .

In this case when the service provider management unit receives the price tag registration request module Modshown in from the service provider it decrypts the price tag registration request module Modby using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in .

Then after confirming the legitimacy of the signature data SIGstored in the related decrypted price tag registration request module Modin the signature processing unit the price tag data stored in the price tag registration request module Modis registered and authenticated in the CER database via the certificate and usage control policy management unit .

Next an explanation will be made of the processing where the settlement is carried out in the EMD service center by referring to .

When receiving as its inputs the usage log data and signature data SIGthereof from for example the SAM of the user home network the SAM management unit decrypts the usage log data and the signature data SIGby using the session key data Kobtained by the mutual certification between the mutual certification unit and the SAMs to verifies the signature data SIGby using the public key data Kof the SAM and then outputs the same to the settlement processing unit .

Then the settlement processing unit performs the settlement processing based on the usage log data input from the SAM and the suggested retailer s price data SRP and the price tag data input from the certificate and usage control policy management unit .

The settlement processing unit produces settlement report data and settlement claim data for the content provider and outputs them to the content provider management unit and the settlement manager management unit as shown in .

Also by the settlement processing as shown in and the settlement report data and the settlement claim data for the service provider are produced and are output to the service provider management unit and the settlement manager management unit .

Next the settlement manager management unit performs the mutual certification of the settlement claim data and and the signature data produced for them by using the secret key data Kand the decryption by the session key data Kand then transmits the same to the settlement manager via the payment gateway shown in .

By this the money of the sum indicated in the settlement claim data is paid to the content provider and the money of the sum indicated in the settlement claim data is paid to the service provider .

Next an explanation will be made of the processing in the case where the EMD service center transmits the settlement report data and to the content provider and the service provider .

When settlement is carried out in the settlement processing unit the settlement report data is output from the settlement processing unit to the content provider management unit .

When receiving as input the settlement report data from the settlement processing unit the content provider management unit encrypts this by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in and then transmits the same to the content provider .

Also when the settlement is carried out in the settlement processing unit the settlement report data is output from the settlement processing unit to the service provider management unit .

When receiving as input the settlement report data from the settlement processing unit the service provider management unit encrypts this by using the session key data Kobtained by the mutual certification between the mutual certification unit and the mutual certification unit shown in and then transmits the same to the service provider .

The EMD service center performs processing at the time of shipment of the SAMs to and the registration processing of the SAM registration list in the same way as the EMD service center of the first embodiment other than the above.

The network apparatus includes the built in CA module and the SAM . Further the A V apparatuses to include the built in SAMs to .

Note that it is possible if the AV apparatuses to have a network communication function or do not have the network communication function but utilize the network communication function of the network apparatus via the bus .

Also it is also possible if the user home network has only AV apparatuses not having network functions.

As shown in the network apparatus has a communication module CA module decryption module SAM decryption and or expansion module purchase and or usage form determination operation unit download memory reproduction module and external memory .

In components given the same reference numerals as those of are the same as the components of the same reference numerals explained in the first embodiment.

Concretely the communication module outputs the secure container received from the service provider by a satellite broadcast or the like to the decryption module . Also the communication module outputs user preference filter data received via a telephone line or the like at the service provider to the CA module and at the same time transmits SP use purchase log data input from the CA module to the service provider via the telephone line or the like.

As shown in the CA module has a mutual certification unit a storage unit an encryption and or decryption unit and an SP use purchase log data generation unit .

When transmitting and receiving the data between the CA module and the service provider via the telephone line the mutual certification unit performs the mutual certification with the service provider to produce the session key data Kand outputs this to the encryption and or decryption unit .

The storage unit stores the master key data Ksupplied from the service provider off line by using an IC card etc. after for example a contract is established between the service provider and the user.

The encryption and or decryption unit receives as its inputs the encrypted scramble key data Kand work key data Kfrom a decryption unit of the decryption module and decrypts the work key data Kby using the master key data Kread out from the storage unit . Then the encryption and or decryption unit decrypts the scramble key data Kby using the related decrypted work key data Kand outputs the related decrypted scramble key data Kto the decryption unit .

Also the encryption and or decryption unit decrypts the user preference filter data received by the communication module from the service provider via the telephone line or the like by using the session key data Kfrom the mutual certification unit and outputs the same to a secure container selection unit of the decryption module .

Also the encryption and or decryption unit decrypts the SP use purchase log data input from the SP use purchase log data generation unit by using the session key data Kfrom the mutual certification unit and transmits the same via the communication module to the service provider .

The SP use purchase log data generation unit produces the SP use purchase log data indicating the purchase log of the content data C inherent in the service provider based on the operation signal S in accordance with the purchase operation of the content data C by the user by using the purchase and or usage form determination operation unit shown in or the usage control status data from the SAM and outputs this to the encryption and or decryption unit

The SP use purchase log data includes for example the information to be collected from the user concerning the distribution service by the service provider the monthly base fee network rent contract update information and the purchase log information.

Note that the CA module communicates with a charge database a customer management database and a marketing information database of the service provider when the service provider has the charge function. In this case the CA module transmits the charge data for the distribution service of the content data to the service provider .

The decryption unit receives as its inputs the encrypted secure container scramble key data K and the work key data Kfrom the communication module .

Then the decryption unit outputs the encrypted scramble key data Kand work key data Kto the encryption and or decryption unit of the CA module and receives as its input the decrypted scramble key data Kfrom the encryption and or decryption unit .

Then the decryption unit decrypts the encrypted secure container by using the scramble key data Kand then outputs the same to the secure container selection unit .

Note that where the secure container is transmitted from the service provider by an MPEG2 Transport Stream method for example the decryption unit extracts the scramble key data Kfrom an ECM Entitlement Control Message in a TS Packet and extracts the work key data Kfrom an EMM Entitlement Management Message .

In the ECM other than the above for example program attribute information for every channel are contained. Further in the EMM other than this individual demo contract information different for every user listener etc. are contained.

The secure container selection unit filters the secure containers input from the decryption unit by using the user preference filter data input from the CA module selects the secure container in accordance with the preference of the user and outputs the same to the SAM .

Note that the SAM has basically the same function and structure as the SAM of the first embodiment mentioned before by using to except it performs the processing concerning the service provider in addition to the content provider for example it performs the signature verification processing for the service provider .

Namely the SAMs to are modules for performing charge processing in units of content and communicate with the EMD service center .

Note that in the flow of the data related to the processing when receiving as input the secure container from the service provider is shown.

As shown in the SAM has the mutual certification unit encryption and or decryption units and error correction unit download memory management unit secure container decryption unit decryption and or expansion module management unit EMD service center management unit usage monitor unit signature processing unit SAM management unit storage unit media SAM management unit stack memory a service provider management unit a charge processing unit a signature processing unit and the external memory management unit .

Note that the predetermined function of the SAM shown in is realized by executing a secret program in the CPU in the same way as the case of the SAM .

In functional blocks given the same reference numerals as those of are the same as the functional blocks having the same reference numerals explained in the first embodiment.

Also in the external memory shown in after the processing explained in the first embodiment and the processing mentioned later the usage log data and the SAM registration list are stored.

Also in the stack memory as shown in the content key data Kc usage control policy data UCP lock key data Kof the storage unit certificate data CERof the content provider certificate data CERof the service provider usage control status data UCS SAM program download containers SDCto SFDC the price tag data etc. are stored.

Below an explanation will be made of the functional blocks newly given reference numerals in among the functional blocks of the SAM .

The signature processing unit verifies the signature data in the secure container by using the public key data Kof the EMD service center public key data Kof the content provider and the public key data Kof the service provider read out from the storage unit or the stack memory .

The charge processing unit performs the charge processing in accordance with the purchase and or usage form of the content by the user based on the operation signal S from the purchase and or usage form determination operation unit shown in and the price tag data read out from the stack memory as shown in .

The charge processing by the charge processing unit is carried out based on the rights contents such as the usage permission condition indicated by the usage control policy data and the usage control status data under the monitoring of the usage monitor unit . Namely the user can purchase and use the content within the range according to the related rights content etc.

Also the charge processing unit produces the usage log data in the charge processing and writes this into the external memory via the external memory management unit .

Here the usage log data is used when determining the payment of the license fee related to the secure container in the EMD service center in the same way as the usage log data of the first embodiment.

Also the charge processing unit produces the usage control status UCS data describing the purchase and or usage form of the content by the user based on the operation signal S and writes this into the stack memory .

As the purchase form of the content there are for example outright purchase without restriction as to the reproduction by the purchaser or copying for use of the related purchaser and a reproduction charge for charging whenever the content is reproduced.

Here the usage control status data is produced when the user determines the purchase form of the content and used for control so that the user will use the related content within the range permitted by the related determined purchase form from then on. In the usage control status data the ID of the content purchase form outright purchase price SAM ID of the SAM for which the related content was purchased the USER ID of the user purchasing the content etc. are described.

Note that where the determined purchase form is a reproduction charge for example the usage control status data is transmitted from the SAM to the service provider in real time and the service provider instructs the EMD service center to take the usage log data from the SAM .

Also where the determined purchase form is outright purchase for example the usage control status data is transmitted to the service provider and the EMD service center in real time.

Also in the SAM as shown in the user preference filter data received via the EMD service center management unit from the EMD service center is output to the service provider management unit . Then in the service provider management unit among the secure containers input from the decryption module shown in the secure container filtered based on the user preference filter data and thus responding to the preference of the user is selected and the related selected secure container is output to the error correction unit . By this in the SAM the selection processing of the content data C based on the preference of the related user obtained from the purchase situation of the content data C by the related user becomes possible for all service providers contracting with the user of the related SAM .

The flow of the processing when storing the distribution use key data KDto KDreceived from the EMD service center in the storage unit is similar to that of the case of the SAM mentioned before.

Next an explanation will be made of the flow of the processing in the SAM when receiving as input the secure container from the service provider by referring to .

Mutual certification is carried out between the mutual certification unit and the mutual certification unit of the service provider shown in .

The encryption and or decryption unit decrypts the secure container shown in received from the service provider via the service provider management unit by using the session key data Kobtained by the related mutual certification.

Next the signature processing unit verifies the signature data SIGand SIGshown in and then verifies the legitimacy of the signature data SIG SIG SIG SIG and SIGby using the public key data Kand Kstored in the certificate data CERand CER.

Here by verifying the signature data SIGand SIG the legitimacy of the producer and transmitter of the content file CF is confirmed by verifying the signature data SIGand SIG the legitimacy of the transmitter of the key file KF is confirmed and by verifying the signature data SIG the legitimacy of the producer and the transmitter of the price tag data is confirmed.

Also by verifying the legitimacy of the signature data SIGstored in the key file KF shown in by using the public key data Kread out from the storage unit the signature processing unit verifies the legitimacy of the producer of the key file KF and whether or not the key file KF is registered in the EMD service center .

When the legitimacy of all signature data mentioned above is confirmed in the signature processing unit the service provider management unit outputs the secure container to the error correction unit .

The error correction unit corrects the error of the secure container and then outputs the same to the download memory management unit .

The download memory management unit performs the mutual certification between the mutual certification unit and the media SAM shown in and then writes the secure container into the download memory .

Next the download memory management unit performs the mutual certification between the mutual certification unit and the media SAM shown in and then reads out the key file KF shown in stored in the secure container from the download memory and outputs the same to the secure container decryption unit .

Then in the secure container decryption unit by using the distribution use data KDto KDof the corresponding period input from the storage unit the content key data Kc usage control policy data and the SAM program download containers SDCto SDCstored in the key file KF shown in are decrypted.

Then the decrypted content key data Kc usage control policy data and the SAM program download containers SDCto SDCare written into the stack memory .

Below an explanation will be made of the flow of the processing until the purchase form of the secure container downloaded on the download memory from the service provider is determined by referring to and .

Where the operation signal S indicating the demo mode is output to the charge processing unit by the operation of the purchase and or usage form determination operation unit shown in by the user the processing of step E is carried out. In other cases the processing of step E is carried out.

This is carried out where the operation signal S indicating the demo mode is output to the charge processing unit and for example the content file CF stored in the download memory is output via the decryption and or expansion module management unit to the decryption and or expansion module shown in .

At this time with respect to the content file CF the mutual certification between the mutual certification unit and the media SAM and the encryption and or decryption by the session key data Kand the mutual certification between the mutual certification unit and the mutual certification unit and the encryption and or decryption by the session key data Kare carried out.

The content file CF is decrypted in the decryption unit shown in by using the session key data Kand then output to the decryption unit .

Also the content key data Kc and the half disclosure parameter data read out from the stack memory are output to the decryption and or expansion module shown in . At this time after the mutual certification between the mutual certification unit and the mutual certification unit the encryption and decryption by the session key data Kare carried out with respect to the content key data Kc and the half disclosure parameter data .

Next the decrypted half disclosure parameter data is output to the half disclosure processing unit and under the control from the half disclosure processing unit the decryption of the content data C using the content key data Kc by the decryption unit is carried out in a half disclosure mode.

Next the content data C decrypted in the half disclosure mode is expanded at the expansion unit and then output to the electronic watermark information processing unit .

Next the user watermark use data is buried in the content data C in the electronic watermark information processing unit then the content data C is reproduced at the reproduction module and sound in accordance with the content data C is output.

When the user determines the purchase form by operating the purchase and or usage form determination operation unit the operation signal S indicating the related determined purchase form is output to the charge processing unit .

In the charge processing unit the usage log data and the usage control status data in accordance with the determined purchase form are produced the usage log data is written into the external memory via the external memory management unit and the usage control status data is written into the stack memory .

Thereafter in the usage monitor unit control monitor is carried out so that the content is purchased and used within the range permitted by the usage control status data .

Then by using the key file KF and the usage control status data stored in the stack memory a new key file KF with the purchase form determined therefor shown in is produced and the related produced key file KFis stored in the stack memory .

As shown in the usage control status data stored in the key file KFhas been sequentially encrypted by utilizing the CBC mode of the DES by using the storage key data Kand the media key data K.

Here the storage use key data Kis data determined in accordance with the type of apparatus for example an SACD Super Audio Compact Disc DVD Digital Versatile Disc apparatus CD R apparatus and MD Mini Disc apparatus and used for establishing one to one correspondence between the types of the apparatuses and the types of the storage medium. Also the media key data Kis data unique to the storage medium.

Also in the signature processing unit the hash value Hof the key file KFis produced by using the secret key data Kof the SAM and the related produced hash value His stored in the stack memory in correspondence to the key file KF.

The usage control status data is transmitted from the SAM to the EMD service center . The related usage control status data is transmitted whenever the purchase form of the content data is determined in the SAM .

Note that the usage log data is transmitted from the SAM to the EMD service center at predetermined time intervals of for example one month.

Next an explanation will be made of the flow of the processing in the case where the content data C for which the purchase form is already determined stored in the download memory is reproduced by referring to .

In this case under the monitoring by the usage monitor unit based on the operation signal S the content file CF stored in the download memory is output to the decryption and or expansion module shown in .

Also the content key data Kc read out from the stack memory is output to the decryption and or expansion module .

Then in the decryption unit of the decryption and or expansion module the decryption of the content file CF using the content key data Kc and the expansion processing by the expansion unit are carried out and the content data C is reproduced in the reproduction module .

At this time in the charge processing unit the usage log data stored in the external memory is updated in response to the operation signal S.

The usage log data is transmitted together with the signature data SIGproduced by using the secret key data Kvia the EMD service center management unit to the EMD service center at a predetermined timing.

Next as shown in an explanation will be made of the flow of the processing in the SAM in the case where for example the secure container shown in for which the purchase form has been already determined and downloaded on the download memory of the network apparatus is transferred via the bus to the SAM of the AV apparatus by referring to .

The user operates the purchase and or usage form determination operation unit to instruct to transfer the predetermined content stored in the download memory to the AV apparatus . The operation signal S in accordance with the related operation is output to the charge processing unit .

By this the charge processing unit updates the usage log data stored in the stack memory based on the operation signal S.

Also the download memory management unit outputs the content files CF and key files KF and KF shown in B and C read out from the download memory to the signature processing unit and the SAM management unit .

Then the signature processing unit produces the signature data SIGand SIGof the content files CF and the key files KF and at the same time produces the hash value Hof the key file KF and outputs them to the SAM management unit .

Also the SAM management unit reads out the price tag data and the signature data SIGthereof and the certificate data CERand the signature data SIGthereof shown in from the stack memory .

Also the SAM management unit reads out the certificate data CERand the signature data SIGthereof shown in from the storage unit .

Also the mutual certification unit outputs the session key data Kobtained by mutual certification with the SAM to the encryption and or decryption unit .

The SAM management unit encrypts the secure container shown in in the encryption and or decryption unit by using the session key data Kand then outputs the same to the SAM of the AV apparatus shown in .

Below as shown in an explanation will be made of the flow of the processing in the SAM when writing the secure container input from the SAM into a storage medium such as a RAM by referring to .

In this case the SAM management unit of the SAM receives as input the secure container shown in from the SAM of the network apparatus as shown in .

Then the mutual certification between the mutual certification unit of the SAM and the mutual certification unit of the SAM is carried out and the signature processing unit decrypts the secure container by using the session key data Kobtained by the related mutual certification.

Next in the signature processing unit by using the public key data Kread out from the storage unit the legitimacy of the signature data SIG SIG and SIGshown in is verified.

Then when the legitimacy of the signature data SIG SIG and SIGis confirmed in the signature processing unit by using the public key data K K and Kcontained in the certificate data CER CER and CER the legitimacy of the signature data SIG SIG SIG SIG SIG SIG and SIGshown in and the hash value His verified.

Then when the legitimacy of these signature data is confirmed the key files KF and KFand the price tag data are stored in the stack memory .

Also the content file CF is output from the SAM management unit to the storage module management unit .

Then the content key data Kc and the usage control status data stored in the key file KFshown in are read out from the stack memory to the encryption and or decryption unit and in the encryption and or decryption unit sequentially encrypted by using the storage use key distribution use data K media key data K and the purchaser key data Kread out from the storage unit and then output to the storage module management unit .

Also the key file KF read out from the stack memory is output to the storage module management unit .

Then after the mutual certification between the mutual certification unit and the media SAM of the RAM type storage medium the content file CF is stored in the unsecure RAM region of the RAM type storage medium and the key files KF and KFand the price tag data are written into the secure RAM region .

Note that it is also possible to store the key files KF and KFand the price tag data in the media SAM of the RAM type storage medium .

Note that among the processing in the SAM the flow of the processing in the AV apparatus when determining the purchase form of the ROM type storage medium with the purchase form of the content still undetermined and the flow of the processing when reading the secure container from the ROM type storage medium with the purchase form still undetermined in the AV apparatus transferring this to the AV apparatus and writing the same into the RAM type storage medium are the same as the case of the SAM of the first embodiment except for the point that the signature data is verified using the secret key data of the service provider and for the point that the price tag data is stored in the key file with the purchase form determined.

Here an explanation will be made by exemplifying the case where the secure container is transmitted from the service provider to the user home network on line.

Note that as the prerequisite of the following processing it is assumed that the registration of the content provider service provider and SAMs to to the EMD service center has been already finished.

Step S The EMD service center transmits the certificate CERof the public key data Kof the content provider together with the its own signature data SIGto the content provider .

Also the EMD service center transmits the certificate CERof the public key data Kof the content provider together with its own signature data SIGto the service provider .

Also the EMD service center transmits three months worth of the distribution use key data KDto KDeach having the expiration date of one month to the SAMs to of the user home network .

Step S After the mutual certification the content provider transmits the registration use module Modshown in to the EMD service center .

Then after the predetermined signature verification the EMD service center registers and authenticates the usage control policy data and content key data Kc.

Also the EMD service center produces six months worth of the key files KF shown in in accordance with the registration use module Mod and transmits this to the content provider .

Step S The content provider produces the content file CF and the signature data SIGthereof and the key file KF and the signature data SIGthereof shown in and provides the secure container storing them and the certificate data CERand the signature data SIGthereof shown in to the service provider on line and or off line.

Step S The service provider verifies the signature data SIGshown in and then verifies the signature data SIGand SIGshown in by using the public key data Kstored in the certificate data CERand confirms if the secure container was transmitted from a legitimate content provider .

Step S The service provider produces the price tag data and the signature data SIGthereof and produces the secure container shown in storing them.

Step S The service provider transmits the price tag registration request module Modshown in to the EMD service center .

Then the EMD service center registers and authenticates the price tag data after the predetermined signature verification.

Step S The service provider transmits the secure container produced at step S on line or off line to the decryption module of the network apparatus shown in in response to the request from for example the CA module of the user home network .

Step S The CA module produces the SP use purchase log data and transmits this to the service provider at the predetermined timing.

Step S In any of the SAMs to after verifying the signature data SIGshown in the signature data SIG SIGand SIGshown in B and C are verified by using the public key data Kstored in the certificate data CER and it is confirmed whether or not the predetermined data in the secure container was produced and transmitted in a legitimate service provider .

Step S After verifying the signature data SIGshown in in any of the SAMs to the signature data SIGand SIGshown in B and C are verified by using the public key data Kstored in the certificate data CER and it is confirmed whether or not the content file CF in the secure container was produced in a legitimate content provider and whether or not the key file KF was transmitted from a legitimate content provider .

Also by verifying the legitimacy of the signature data SIGin the key file KF shown in by using the public key data Kin any of the SAMs to it is confirmed whether or not the key file KF was produced by a legitimate EMD service center .

Step S The user operates the purchase and or usage form determination operation unit of and determines the purchase and or usage form of the content.

Step S Based on the operation signal S produced at step S in the SAMs to the usage log data of the secure container is produced.

The usage log data and the signature data SIGthereof are transmitted from the SAMs to to the EMD service center .

Also whenever the purchase form is determined the usage control status data is transmitted from the SAMs to to the EMD service center .

Step S The EMD service center determines calculates the charge content for each of the content provider and the service provider based on the usage log data and produces the settlement claim data and based on the result thereof.

Step S The EMD service center transmits the settlement claim data and together with its own signature data to the settlement manager via the payment gateway . By this the money paid by the user of the user home network to the settlement manager is distributed to the owners of the content provider and the service provider .

As explained above in the EMD system the secure container of the format shown in is distributed from the content provider to the service provider the secure container storing the content file CF and key file KF in the secure container as they are is distributed from the service provider to the user home network and the processing for the key file KF is carried out in the SAMs to .

Also the content key data Kc and usage control policy data stored in the key file KF have been encrypted by using the distribution use key data KDto KDand decrypted in only the SAMs to holding the distribution use key data KDto KD. The SAMs to are modules having tamper resistance. The purchase form and the usage form of the content data C are determined based on the handling content of the content data C described in the usage control policy data .

Accordingly according to the EMD system the content data C can be reliably purchased and used in the user home network based on the content of the usage control policy data produced by the interested party of the content provider irrelevant to the processing in the service provider . Namely according to the EMD system it is possible to prevent the usage control policy data from being managed by the service provider .

For this reason according to the EMD system even in a case where the content data C is distributed to the user home network via a plurality of service providers of different affiliations the rights clearing for the related content data C in the user home network can be performed based on the common usage control policy data produced by the content provider .

Also in the EMD system for the files and data in the secure containers and the signature data indicating the legitimacy of the producers and the transmitters of them are stored. Therefore in the service provider and the SAMs to the legitimacy of the producers and transmitters and whether or not the data has been tampered with can be confirmed.

Also in the EMD system by distributing the content data C from the service provider to the user home network by using the secure container in both of the cases of on line and off line in both cases common rights clearing of the content data C in the SAMs to can be performed.

Also in the EMD system when purchasing using recording and transferring the content data C in the network apparatus and the AV apparatuses to in the user home network by always performing the processing based on the usage control policy data common rights clearing rules can be employed.

For example as shown in no matter by what technique route the content data C provided by the content provider is distributed delivered from the service provider to the user home network such as package communication a digital broadcast Internet dedicated line digital radio and mobile communication in the SAMs of the user home networks and common rights clearing rules are employed based on the usage control policy data produced by the content provider .

Also according to the EMD system since the EMD service center has the certificate authority function key data management function and the rights clearing profit distribution function the money paid by the user accompanied with the usage of the content is reliably distributed to the owners of the content provider and the EMD service center according to the ratio determined in advance.

Also according to the EMD system the usage control policy data for the same content file CF supplied by the same content provider is supplied as is to the SAMs to irrelevant as to the service format of the service provider . Accordingly in the SAMs to the content file CF can be used according to the intention of the content provider based on the usage control policy data .

Namely according to the EMD system at the time of a service using the content and usage of the content by the user the rights and profit of the owner of the content provider can be reliably protected by technical means without depending on an inspection organization as in the conventional case.

Below an explanation will be made of a concrete example of the transport protocol such as the secure container employed in the EMD system of the above second embodiment.

As shown in the secure container produced in the content provider is provided to the service provider by using a content provider use transport protocol of the Internet TCP IP or dedicated line ATM cell .

Also the service provider distributes the secure container produced by using the secure container to the user home network by using the service provider use transport protocol of a digital broadcast XML SMIL on MPEG TS Internet XML SMIL on TCP IP or package circulation storage medium .

Also the secure container is transferred among SAMs in the user home networks and or between the user home network and by using the home EC distribution service XML SMIL on 1394 serial bus interface or storage medium.

Below an example of the transport protocol employed in the data transfer in the routes indicated by reference symbols A to G will be explained in detail in .

As shown in the secure container etc. are transported from the content provider to the service provider by a session using a common key in the IP IP SEC layer SSL Secure Sockets Layer XML Extensible Markup Language SMIL Synchronized Multimedia Integration Language layer and application layer.

As shown in the key file etc. are transported from the EMD service center to the content provider by a session using a common key in the IP IP SEC layer SSL layer and the application layer.

As shown in the price tag data etc. are transported from the EMD service center to the service provider by a session using a common key in the IP IP SEC layer SSL layer and the application layer.

As shown in the secure container etc. are transported from the service provider to the network apparatus of the user home network .

At this time the MPEG TS layer PES layer or DSM CC Data Carousel layer and MHEG Multimedia and Hypermedia Experts layer or http layer and XML SMIL layer are used as the service provider use commodity transport protocol for transferring the secure container between the service provider and the network apparatus .

Also between the network apparatus and a storage apparatus and between AV apparatuses HAVi XML is used as the user home network commodity transport protocol for transferring the secure container.

At this time where XML SMIL BML is utilized in the data broadcast method of a digital broadcast the content files CF and CF and the key files KF and KF and the demo sample of the secure container are stored in a BML XML SMIL layer on the HTTP layer and a monomedia data layer and transported as shown in .

Also where the MHEG is utilized in the data broadcast method of a digital broadcast the content files CF and CF and the key files KF and KF and the demo sample of the secure container are stored in the monomedia data layer on the MHEG layer and transported as shown in .

Also where the XML SMIL is utilized in the data broadcast method of a digital broadcast the content files CF and CF and the key files KF and KF and the demo sample of the secure container are stored in the XML SMIL layer on the HTTP layer and transported as shown in .

As shown in where the usage log data etc. are transferred from the network apparatus to the EMD service center a session using the session key data is carried out in the IP IP SEC layer SSL layer and the application layer.

Also where the network apparatus etc. transfer the usage log data usage control status data etc. to the EMD service center after the usage log data etc. are transferred from the storage apparatus to the network apparatus by a session in the IP IP SEC layer and the HAVi layer they are transferred from the network apparatus to the EMD service center as mentioned before.

As shown in the secure container is transported from the storage apparatus to the storage apparatus by a session using a common key in the IP IP SEC layer SSL layer XML SMIL layer and the application layer.

In components given the same reference numerals as those of are the same as the components having the same reference numerals explained in the first embodiment.

As shown in in the EMD system the same secure containers are supplied from the content provider to service providers and

The service provider offers a service providing for example a drama program as the content. In the related service a secure container storing the content data C related to the drama program and price tag data uniquely produced for the related content data C is produced and is distributed to the network apparatus .

Also the service provider provides for example a karaoke service. In the related service a secure container storing the content data C related to the karaoke service and price tag data uniquely produced for the related content data C is produced and is distributed to the network apparatus .

Here the formats of the secure containers and are the same as that of the secure container explained by using .

The CA modules and are receive the secure containers and in response to requests from them to the service providers and

Next the CA modules and produce SP use purchase log data and in accordance with the distributed secure containers and and transmit them to the service providers and

Also the CA modules and decrypt the secure containers and by the session key data Kand then output the same to the SAMs to .

Next in the SAMs to the key files KF in the secure containers and are decrypted by using the common distribution use key data KDto KD the processing concerning the purchase and or usage of the content in accordance with the operation from the user is carried out based on the common usage control policy data and the usage log data in accordance with that is produced.

In the EMD service center based on the usage log data the charge content is determined calculated for each of the content provider and the service providers and and the settlement claim data and corresponding to them are produced based on the results thereof.

The EMD service center transmits the settlement claim data and to the settlement manager via the payment gateway . By this the money paid by the user of the user home network to the settlement manager is distributed to the owners of the content provider and the service providers and

As mentioned above according to the EMD system when the same content file CF is supplied to the service providers and the usage control policy data for the related content file CF is encrypted by the distribution use key data KDto KDand supplied to the service providers and and the service providers and distribute the secure containers and storing the encrypted usage control policy data as it is to the user home network. For this reason in the SAMs to in the user home network no matter which of the service provider or the content file CF is distributed from the rights can be cleared based on the common usage control policy data .

Note that in the first modification the case where two service providers were used was exemplified but in the present invention any number of the service providers may be provided.

In components given the same reference numerals as those of are the same as the components having the same reference numerals explained in the first embodiment.

As shown in in the EMD system the key files KFa and KFb are supplied from the EMD service center to the content providers and and the secure containers and are supplied from content providers and to the service provider .

The service provider provides a service by using the content supplied by for example the content providers and produces the price tag data for the secure container and the price tag data for the secure container and produces a secure container storing them.

As shown in in the secure container the content data CFa CFb key files KFa and KFb price tag data and and the signature data by the secret key data Kof the service provider for each of them are stored.

The secure container is received at the CA module of the network apparatus of the user home network and then processed at the SAMs to .

In the SAMs to the key file KFa is decrypted by using the distribution use key data KDato KDa the processing concerning the purchase and or usage is carried out in accordance with the operation from the user for the content file CFa based on the usage control policy data and the log thereof is described in the usage log data .

Also in the SAMs to the key file KFb is decrypted by using distribution use key data KDbto KDb the processing concerning the purchase and or usage is carried out in accordance with the operation from the user for the content file CFb based on the usage control policy data and the log thereof is described in the usage log data .

In the EMD service center based on the usage log data the charge content is determined calculated for each of the content providers and and the service provider and settlement claim data and corresponding to them are produced based on the results thereof.

The EMD service center transmits the settlement claim data and via the payment gateway to the settlement manager . By this the money paid by the user of the user home network to the settlement manager is distributed to the owners of the content providers and and the service provider .

As mentioned above according to the EMD system as the usage control policy data and of the content files CFa and CFb stored in the secure container those produced by the content providers and are used as they are therefore in the SAMs to the rights for the content files CFa and CFb are reliably cleared based on the usage control policy data and according to the intention of the content providers and

Note that in the second modification shown in the case where two content providers were used was exemplified but any number of the content providers may be used.

In the second embodiment the case where the EMD service center performed the settlement for the content provider and the service provider at the settlement manager was exemplified but in the present invention for example as shown in it is also possible for the settlement claim data for the content provider and the settlement claim data for the service provider to be produced based on the usage log data in the EMD service center and for them to be transmitted to the content provider and the service provider .

In this case the content provider performs settlement at a settlement manager via a payment gateway by using the settlement claim data . Further the service provider performs settlement at a settlement manager via a payment gateway by using the settlement claim data

In the second embodiment the case where the service provider did not have a charging function as in for example the current Internet was exemplified but where the service provider has a charging function as in the current digital broadcast in the CA module a usage log data with respect to the service of the service provider concerning the secure container is produced and transmitted to the service provider .

Then the service provider performs charge processing based on the usage log data to produce the settlement claim data and performs settlement at the settlement manager via the payment gateway by using this.

On the other hand the SAMs to produce usage log data with respect to the rights clearing of the content provider concerning the secure container and transmit them to the EMD service center .

The EMD service center produces the settlement claim data based on the usage log data and transmits this to the content provider .

The content provider performs settlement at the settlement manager via the payment gateway by using the settlement claim data

In the embodiment as shown in the case where the user preference filter data was produced based on the usage log data received from the SAM etc. in the user preference filter generation unit of the EMD service center was exemplified but it is also possible to produce for example the user preference filter data in the user preference filter generation unit based on the usage control status data produced in the user monitor unit of the SAM shown in and transmitted to the EMD service center in real time.

The content provider the service provider and the SAMs to can register their secret key data K K and Kto Kin the EMD service center too other than their public key data Kand Kto K.

By doing this it becomes possible for the EMD service center to tap into desired communication among the communication between the content provider and the service provider the communication between the service provider and the SAMs to and the communication among the SAMs to in the user home network by using the secret key data K K and Kto Kin response to demands from the government or police organizations at the time of emergencies.

Further for the SAMs to it is also possible even if the secret key data Kto Kare produced by the EMD service center at the time of shipment and they are stored in the SAMs to and at the same time held registered by the EMD service center .

In the embodiment the case where when the content provider service provider and the SAMs to communicated with each other the certificate data CER CER and CERto CERwere acquired from the EMD service center in advance and were transmitted to the destination of communication by the in band method was exemplified but in the present invention various formats can be employed as the transmission format of the certificate data to the destination of communication.

For example when the content provider service provider and the SAMs to communicate with each other it is also possible if the certificate data CER CER and CERto CERare acquired from the EMD service center in advance and are transmitted to the destination of communication by the in band method preceding the related communication.

Further it is also possible for the content provider service provider and the SAMs to to acquire the certificate data CER CER and CERto CER from the EMD service center at the time of communication.

Note that in components given the same reference numerals as those of are the same as the components having the same reference numerals explained above. Further the user home network is the same as the user home network mentioned before. In a user home network SAMs to are connected via the IEEE1394 serial bus serving as the bus .

Where the content provider acquires the certificate data CER of the service provider there are for example a case where the certificate data CERis transmitted from the service provider to the content provider preceding the communication in and a case where the content provider orders the certificate data CERfrom the EMD service center in .

Also where the service provider acquires the certificate data CERof the content provider there are for example a case where the certificate data CERis transmitted from the content provider to the service provider preceding the communication in and a case where the service provider orders the certificate data CERfrom the EMD service center in .

Also where the service provider acquires the certificate data CERto CERof the SAMs to there are for example a case where the certificate data CERto CERare transmitted from the SAMs to to the service provider preceding the communication in and a case where the service provider orders the certificate data CERto CERfrom the EMD service center in .

Also where the SAMs to acquire the certificate data CERof the service provider there are for example a case where the certificate data CERis transmitted from the service provider to the SAMs to preceding the communication in and a case where the SAMs to order the certificate data CERfrom the EMD service center in etc. .

Also where the SAM acquires the certificate data CERof the SAM there are for example a case where the certificate data CERis transmitted from the SAM to the SAM preceding the communication in and a case where the SAM orders the certificate data CER from the EMD service center in etc. .

Also where the SAM acquires the certificate data CERof the SAM there are for example a case where the certificate data CER is transmitted from the SAM to the SAM preceding the communication in a case where the SAM orders the certificate data CERfrom the EMD service center by itself and a case where the SAM orders the certificate data CERvia the network apparatus with the SAM mounted thereon 7 and 8 in .

Also where the SAM acquires certificate data CERof the SAM there are for example a case where the certificate data CERis transmitted from the SAM to the SAM preceding the communication in a case where the SAM orders the certificate data CERfrom the EMD service center by itself in and a case where the SAM orders the certificate data CERvia the network apparatus in the user home network

Also where the SAM acquires the certificate data CERof the SAM there are for example a case where the certificate data CERis transmitted from the SAM to the SAM preceding the communication in a case where the SAM orders the certificate data CERfrom the EMD service center by itself in and a case where the SAM orders the certificate data CERvia the network apparatus in the user home network

In the second embodiment in order to prevent the content provider service provider and the SAMs to used for illegitimate action etc. from communicating with the other apparatuses in the EMD service center a certificate revocation list for invalidating the certificate data of the apparatus used for the related illegitimate action is produced. Then the related certificate revocation list CRL is transmitted to the content provider service provider and the SAMs to .

Note that it is also possible if the certificate revocation list CRL is produced in for example the content provider service provider and the SAMs to other than the EMD service center .

First an explanation will be made of the case where the EMD service center invalidates the certificate data CERof the content provider .

As shown in the EMD service center transmits a certificate revocation list CRLindicating the invalidation of the certificate data CERto the service provider in . When verifying the signature data input from the content provider the service provider decides the validity of the certificate data CERby referring to the certificate revocation list CRLperforms signature verification using the public key data Kwhere it decides that it is valid while invalidates the data from the content provider without the related signature verification where it decides that it is invalid. Note that it is also possible not to invalidate the data but reject the communication.

Also the EMD service center transmits the certificate revocation list CRLto for example the SAM in the user home network by utilizing circulation resources of the service provider by either the broadcast type or on demand type and in . When verifying the signature data of the content provider stored in the secure container input from the service provider the SAM decides the validity of the certificate data CERby referring to the certificate revocation list CRL performs signature verification using the public key data Kwhere it decides it as valid while invalidates the related secure container without the related signature verification where it decides it as invalid.

Note that it is also possible for the EMD service center to directly transmit the certificate revocation list CRLto the SAM via the network apparatus in the user home network in .

Next an explanation will be made of the case where the EMD service center invalidates the certificate data CERof the service provider .

As shown in the EMD service center transmits a certificate revocation list CRLindicating the invalidation of the certificate data CERto the content provider in . When verifying the signature data input from the service provider the content provider decides the validity of the certificate data CERby referring to the certificate revocation list CRL performs signature verification using the public key data Kwhere it decides it as valid while invalidates the data from the service provider without the related signature verification where it decides it as invalid.

Also the EMD service center transmits the certificate revocation list CRLto for example the SAM in the user home network by utilizing the circulation resources of the service provider by either the broadcast type or on demand type in . When verifying the signature data of the content provider stored in the secure container input from the service provider the SAM decides the validity of the certificate data CERby referring to the certificate revocation list CRL performs signature verification using the public key data Kwhere it decides it as valid and while invalidates the related secure container without the related signature verification where it decides it as invalid.

In this case in the service provider the module for transmitting and receiving the certificate revocation list CRLmust have tamper resistance. Further in the service provider the certificate revocation list CRLmust be stored in a region where tampering by an interested party of the service provider is difficult.

Note that it is also possible for the EMD service center to directly transmit the certificate revocation list CRLto the SAM via the network apparatus in the user home network in .

Next an explanation will be made of a case where the EMD service center invalidates for example the certificate data CERof the SAM .

As shown in the EMD service center transmits a certificate revocation list CRLindicating the invalidation of the certificate data CERto the content provider in . The content provider transmits the certificate revocation list CRLto the service provider . The service provider transmits the certificate revocation list CRLto for example the SAM in the user home network by utilizing its own circulation resources by either the broadcast type or on demand type in . When verifying the signature data of the SAM added to the data input from the SAM the SAM decides the validity of the certificate data CERby referring to the certificate revocation list CRL performs signature verification using the public key data Kwhere it decides it as valid while invalidates the related data without the related signature verification where it decides it as invalid.

In this case in the service provider the module for transmitting and receiving the certificate revocation list CRLmust have tamper resistance.

Further in the service provider the certificate revocation list CRLmust be stored in a region where tampering by an interested party of the service provider is difficult.

It is also possible for the EMD service center to transmit the certificate revocation list CRLto the SAM via the service provider and in .

Further it is also possible for the EMD service center to directly transmit the certificate revocation list CRLto the SAM via the network apparatus in the user home network in .

Also the EMD service center produces and stores the certificate revocation list CRLindicating the invalidation of for example the certificate data CERof the SAM .

Also the user home network produces a SAM registration list SRL of the SAMs connected to the bus and transmits this to the EMD service center in .

The EMD service center specifies the SAMs for example SAM for which invalidation is instructed by the certificate revocation list CRLamong the SAMs to indicated in the SAM registration list sets revocation flags corresponding to the related SAMs in the SAM registration list SRL so as to indicate the invalidity and produces a new SAM registration list SRL.

The SAM determines the existence of the verification of the signature data and whether or not communication is permitted by referring to the revocation flags of the SAM registration list SRL when communicating with another SAM.

Also the EMD service center produces the certificate revocation list CRLand transmits this to the content provider in .

Next the service provider transmits the certificate revocation list CRLto the SAM by either the broadcast type or on demand type by utilizing its own circulation resources in .

The SAM specifies the SAMs for example SAM for which invalidation is instructed by the certificate revocation list CRLamong the SAMs to indicated in the SAM registration list produced by itself and sets revocation flags corresponding to the related SAMs in the SAM registration list SRL so as to indicate the invalidity.

From then on the SAM determines the existence of verification of the signature data and whether or not communication is permitted by referring to the revocation flag of the related SAM registration list SRL when communicating with another SAM.

Also the EMD service center produces the certificate revocation list CRLand transmits this to the service provider in .

Next the service provider transmits the certificate revocation list CRLto the SAM by either the broadcast type or on demand type by utilizing its own circulation resources in .

The SAM specifies the SAMs for example SAM for which invalidation is instructed by the certificate revocation list CRLamong the SAMs to indicated in the SAM registration list produced by itself and sets revocation flags corresponding to the related SAMs in the SAM registration list SRL so as to indicate the invalidity.

From then on the SAM determines the existence of verification of the signature data and whether or not communication is permitted by referring to the revocation flag of the related SAM registration list SRL when communicating with another SAM.

In the related EMD system in the electronic settlement use clearinghouse settlement processing profit distribution processing is carried out based on the usage log data from the SAM of the user home networks and settlement claim data of the content provider and the service provider are produced and settlement is carried out at the settlement manager via the payment gateway .

Also the right management use clearinghouse produces the settlement reports of the content provider and the service provider in accordance with the settlement notification from the electronic settlement use clearinghouse and transmits them to the content provider and the service provider .

Also it performs the registration authentication etc. of the usage control policy data and the content key data Kc of the content provider .

Note that as shown in when the right management use clearinghouse and the electronic settlement use clearinghouse are accommodated in a single apparatus the EMD service center shown in is formed.

Also in the present invention for example it is also possible to provide the function of a right management use clearinghouse in the EMD service center perform the registration etc. of the usage control policy data in the right management use clearinghouse and at the same time produce the settlement claim data of the service provider based on the usage log data from the SAMs and transmit this to the service provider as shown in . In this case the service provider utilizes its own charge system as an electronic settlement use clearinghouse and performs settlement based on the settlement claim data from the right management use clearinghouse .

Also in the present invention for example it is also possible to provide the function of a right management use clearinghouse in the EMD service center perform the registration etc. of the usage control policy data in the right management use clearinghouse and at the same time produce the settlement claim data of the content provider based on the usage log data from the SAMs and transmit this to the content provider as shown in . In this case the content provider utilizes its own charge system as an electronic settlement use clearinghouse and performs settlement based on the settlement claim data from the right management use clearinghouse .

Also in the present invention for example it is also possible to provide the function of the right management use clearinghouse and the electronic settlement use clearinghouse mentioned above in the content provider as shown in .

In this case the content provider utilizes its own charge system as the electronic settlement use clearinghouse and performs settlement by itself at the settlement manager based on the settlement claim data produced in the right management use clearinghouse .

In the second embodiment the case where the secure container of the format shown in was provided from the content provider to the service provider and the secure container of the format shown in was distributed from the service provider to the user home network in the EMD system shown in was exemplified.

Namely in the second embodiment the case where a single content file CF and a single key file KF corresponding to the related content file CF were stored in the secure container and the secure container as shown in and was exemplified.

In the present invention it is also possible to store a plurality of content files CF and a plurality of key files KF corresponding to the related plurality of content files CF in the secure container and the secure container .

As shown in in the secure container content files CF CF and CF key files KF KF and KF certificate data CER and signature data SIG SIGSIG SIG SIG SIG and SIGare stored.

Here the signature data SIG SIG SIG SIGSIGand SIGare produced in the content provider by taking the hash values of the content files CF CF and CFand the key files KF KF and KF and using the secret key data Kof the content provider .

In the content file CF a header meta data Meta content data C an A V expansion use software Soft and a watermark module WMare stored.

Here the content data Cand the A V expansion use software Soft have been encrypted by using the content key data Kc and the meta data Meta and the watermark module WMhave been encrypted by using the content key data Kcaccording to need.

Also the content data Chas been compressed by for example the ATRAC3 method. The A V expansion use software Softis the software for the expansion of the ATRAC3 method.

Also in the header of the content file CFfor example as shown in directory structure data DSDindicating the linkage to the key file KFand the content file CFis contained.

In the content file CF the header meta data Meta content data C an A V expansion use software Soft and a watermark module WMare stored.

Here the content data Cand the A V expansion use software Softhave been encrypted by using the content key data Kc and the meta data Metaand the watermark module WMhave been encrypted by using the content key data Kcaccording to need.

Also the content data Chas been compressed by for example the MPEG2 method. The A V expansion use software Softis the software for the expansion of the MPEG2 method.

Also in the header of the content file CF for example as shown in directory structure data DSDindicating the linkage to the key file KFand the content file CFis contained.

In the content file CF the header meta data Meta content data C an A V expansion use software Soft and a watermark module WMare stored.

Here the content data Cand the A V expansion use software Softhave been encrypted by using the content key data Kc and the meta data Metaand the watermark module WMhave been encrypted by using the content key data Kcaccording to need.

Also the content data Chas been compressed by for example the JPEG method. The A V expansion use software Softis the software for the expansion of the JPEG method.

Also in the header of the content file CF for example as shown in directory structure data DSDindicating the linkage to the key file KFis contained.

In the key file KF the header content key data Kcencrypted by using the distribution use key data KDto KD usage control policy data the SAM program download container SDC and signature data SIGare stored.

In the key file KF the header content key data Kcencrypted by using the distribution use key data KDto KD usage control policy data the SAM program download container SDC and signature data SIGare stored.

In the key file KF the header content key data Kcencrypted by using the distribution use key data KDto KD usage control policy data the SAM program download container SDC and signature data SIGare stored.

When receiving the secure container shown in the service provider confirms the legitimacy of the signature data SIG SIGSIG SIGSIG and SIG that is the legitimacy of the producers and transmitters of the content files CF CF and CF and the legitimacy of the transmitters of the key files KF KF and KFby using the public key data Kstored in the certificate data CERafter confirming the legitimacy of the related certificate data CERby using the public key data Kof the EMD service center .

Also the content provider confirms the legitimacy of the signature data SIG SIG and SIGand the legitimacy of the producers of the key files KF KF and KFby using the public key data K.

Then the service provider produces price tag data and indicating the sales prices of the content files CF CF and CF.

Also the service provider produces the signature data SIG SIG and SIGof the price tag data and by using the secret key data K.

Also the service provider produces the signature data SIG SIG SIG SIG SIG and SIGof the content files CF CF and CFand KF KF and KFby using the secret key data K.

In the user home network in the SAMs to after confirming the legitimacy of all signature data stored in the secure container the rights for the content data C Cand Care cleared in accordance with the link state shown in the directory structure data DSDto DSDbased on the key files KF KF and KF.

Also in the eighth modification mentioned above in the secure container the case where the plurality of content files CF CF and CFprovided from the single service provider were stored in the single secure container and distributed to the user home network was exemplified. but as shown in it is also possible to store a plurality of content files CF provided from a plurality of content providers and in a single secure container and distribute the same to the user home network .

Also in the secure containers and for example as shown in it is also possible if a content file CFstoring music voice data compressed by the ATRAC3 a content file CFstoring video clip data compressed by the MPEG2 a content file CFstoring the jacket still image data compressed by the JPEG a content file CF storing the lyrics data in a text format and a content file CFstoring the liner note data in a text format and key files KF KF KF KFand KFcorresponding to them are stored.

Also in this case similarly by the directory structure data of the content files CFto CF the linkage among the content files CFto CFand the linkage between the content files CFto CFand the key files KFto KFare established.

Note that the concept of the data format in the case where a plurality of content data are stored in the secure container in the present embodiment case of composite type is shown in for example or .

Note that the format shown in can be similarly applied to also the case where the secure container is transmitted from the content provider to the user home network shown in .

In the above embodiment the case where the content files CF and the key files KF were stored in the secure containers and with the directory structures and transmitted from the content provider to the service provider and from the service provider to the SAMs to was exemplified but it is also possible to separately transmit the content files CF and key files KF from the content provider to the service provider and from the service provider to the SAMs to .

In the first technique as shown in the content files CF and the key files KF are separately transmitted from the content provider to the service provider and from the service provider to the SAMs to .

Also in the second technique as shown in the content files CF are transmitted from the content provider to the service provider and from the service provider to the SAMs to and the key files KF are transmitted from the EMD service center to the SAMs to . The related key files KF are transmitted from the EMD service center to the SAMs to when for example the users of the SAMs to are going to determine the purchase form of the content data C.

Where the first technique and the second technique are employed for example a link is established between related content files CF and between the content files CF and the key files KF corresponding to them by using the hyper link data HL stored in the headers of at least one of the content files CF and the key files KF. In the SAMs to the rights are cleared and the content data C is used based on the related link.

Also in the above second embodiment the case where the content data C and the key data such as the content key data Kc and the usage control policy data were transmitted from the content provider to the service provider and from the service provider to the SAMs to in the file format was exemplified but it is not always necessary to comprise them in the file format so far as the link among them can be established.

For example as shown in it is also possible to separately transmit the content data C meta data Meta A V expansion use software Soft watermark module WM key file KF price tag data and the certificate data CERand CERfrom the content provider and the EMD service center to the SAMs to .

In this case as shown in the content data C meta data Meta A V expansion use software Soft watermark module WM key file KF price tag data and certificate data CERand CERare linked by the hyper link data HL.

Here the hyper link data HL is encrypted by for example the distribution use key data KDto KDand transmitted.

Note that in the present modification as the formats of the content files CF and the key files KF for example those shown in are employed.

Also in this case preferably the signature data SIGand SIGof them are transmitted together with the content files CF and the key files KF.

In the above embodiment the case where the content files CF and the key files KF were separately provided in the secure container was exemplified but for example as shown in it is also possible to store the key files KF in the content files CF in the secure containers and .

In this case with respect to the content files CF storing the key files KF the signature data by the secret key data Kof the content provider and the signature by the secret key data Kof the service provider are attached.

In the above embodiment the case where the content data C was stored in the content files CF the content key data Kc and the usage control policy data were stored in the key files KF and they were transmitted from the content provider to the service provider and from the service provider to the SAM etc. was exemplified but it is also possible to transmit at least one among the content data C content key data Kc and usage control policy data from the content provider to the service provider and from the service provider to the SAMs etc. in a format not depending upon the communication protocol without employing the file format.

For example as shown in in the content provider the secure container storing the content data C encrypted by the content key data Kc and the key file KF containing the encrypted content key data Kc and the encrypted usage control policy data etc. is produced and the secure container is transmitted to the service provider in a format not depending upon the communication protocol. Then in the service provider it is also possible if the price tag data is added to the content data C and the key file KF stored in the secure container to produce the secure container and the secure container is transmitted to the SAM etc. in a format not depending upon the communication protocol.

Also as shown in the content data C encrypted by the content key data Kc and the key file KF containing the encrypted content key data Kc and the encrypted usage control policy data etc. are separately transmitted from the content provider to the service provider in a format not depending upon the communication protocol. Then from the service provider to the SAM etc. the content data C key file KF and the price tag data are separately transmitted in a format not depending upon the communication protocol. Namely the content data C is not comprised in the file format and is transmitted by the identical route to that for the key file KF.

Also as shown in the content data C encrypted by the content key data Kc is transmitted from the content provider to the service provider in a format not depending upon the communication protocol while the content data C and the price tag data are transmitted from the service provider to the SAM etc. in a format not depending upon the communication protocol. Also it is also possible if the key file KF containing the encrypted content key data Kc and the encrypted usage control policy data etc. is transmitted from the EMD service center to the SAM etc. Namely the content data C is not comprised in the file format and is transmitted by a different route from that for the key file KF.

Also as shown in the content data C encrypted by the content key data Kc the content key data Kc and the usage control policy data are transmitted from the content provider to the service provider in a format not depending upon the communication protocol. Also the content data C content key data Kc usage control policy data and the price tag data are transmitted from the service provider to the SAM etc. Namely the content data C content key data Kc usage control policy data and the price tag data are transmitted not in the file format and by the same route.

Also as shown in the content data C encrypted by the content key data Kc is transmitted from the content provider to the service provider in a format not depending upon the communication protocol. Then the content data C and the price tag data are transmitted from the service provider to the SAM etc. in a format not depending upon the communication protocol. Also the content key data Kc and the usage control policy data are transmitted from the EMD service center to the SAM etc. Namely the content data C content key data Kc and the usage control policy data are transmitted not in the file format and by different routes.

In the EMD system shown in mentioned above for example as shown in the user home network can distribute a secure container A in accordance with the secure container received from the service provider to the user home network in response to a request Sfrom a SAM of the user home network too.

In this case it can be considered that the SAM of the user home network functions in the same way as the service provider explained in the second embodiment.

Then the purchase form of the content data C is determined in the SAM of the user home network and the usage log data etc. in accordance with that are transmitted from the SAM of the user home network to the EMD service center .

In the EMD service center based on the usage log data the settlement processing for distributing the money paid by the user of the user home network to the user of the content provider service provider and user home network is carried out.

Note that the file inclusion size relationships of the secure containers in the present embodiment can be expressed as shown in .

In components given the same reference numerals as those used in the above first embodiment and second embodiment are the same as the components having the same reference numerals explained in these embodiments.

In the EMD system of the present embodiment the content provider sends the master source content data S etc. to the EMD service center and for example the content file CF shown in is produced in the EMD service center .

Also the content provider sends the content ID content key data Kc and the electronic watermark management information contents of the electronic watermark information buried in the content data of the content data S the identifier CP ID of the content provider the identifier SP ID of the service provider and the suggested retailer s price SRP of the content data to the EMD service center and the key file KF shown in is produced in the EMD service center .

Also the EMD service center stores the produced content file CF in the CF database attaches global unique content IDs to the individual content files CF and centrally manages them. Also the EMD service center stores the key file KF in the KF database and centrally manages also this by using the content ID.

The EMD service center stores the master source S received from the content provider in the content master source database .

Next in the electronic watermark information addition unit the electronic watermark information indicated by the electronic watermark management information received from the content provider is buried in the master source S read out from the content master source database to produce the content data S.

The content data S is expanded at the expansion unit and then checked audially in the audial check unit . If necessary the electronic watermark information is buried again by the electronic watermark information addition unit .

Next in the encryption unit the content data S is encrypted by using the content key data Kc to produce the content data S.

Next in the CF preparation unit the content file CF shown in storing the content data S etc. is produced and the content file CF is stored in a CF database

Also in the EMD service center in the KF preparation unit the key file KF shown in is produced and the key file KF is stored in a KF database

Next in the secure container preparation unit a secure container storing the content file CF read out from the CF database and the key file KF read out from the KF database is produced and the secure container is stored in the secure container database .

Thereafter the secure container database is accessed by the service provider and the secure container is supplied to the service provider .

Next the service provider produces a secure container storing the content file CF and key file KF stored in the secure container and the price tag data indicating the sales price of the content data.

Then the service provider distributes the secure container to the user home network by using the predetermined communication protocol and in a format not depending upon the related communication protocol or by storing the same in a storage medium.

In the user home network in the case of on line the secure container is provided to the SAM etc. via the CA module in the SAM etc. the content key data Kc usage control policy data etc. stored in the key file KF are decrypted by using the distribution use key data KDto KDor the like and the handling such as the purchase form of the content data stored in the content file CF is determined based on the decrypted usage control policy data .

Also in the SAM etc. the usage log data indicating the purchase log etc. of the content data is produced and the usage log data is transmitted to the EMD service center .

Also where the secure container is distributed from the SAM of the user home network to the SAM of the user home network processing similar to that in the SAM is carried out in the SAM and the usage log data is transmitted from the SAM to the EMD service center .

Note that the processings with respect to the secure container in the user home networks and are the same as the processings in the user home networks and in the first embodiment and second embodiment mentioned above.

Also in the example shown in the case where the secure container storing the content file CF and the key file KF was transmitted from the EMD service center to the service provider and from the service provider to the user home network the case of in band was exemplified but it is also possible to separately transmit the content file CF and the key file KF by the same route the case of out of band .

Also as shown in it is also possible if the content file CF produced in the EMD service center is supplied to the service provider the service provider supplies the content file CF to the user home network and at the same time the key file KF produced in the EMD service center is supplied from the EMD service center to the SAM and SAM of the user home networks and

In the EMD system of the present embodiment the content provider produces for example the content file CF shown in and sends this to the EMD service center .

Also the content provider sends the content ID of the content data content key data Kc electronic watermark management information contents of the electronic watermark information to be buried in the content data and the burial position information identifier CP ID of the content provider identifier SP ID of the service provider providing the content data and the suggested retailer s price SRP of the content data to the EMD service center and the key file KF shown in is produced in the EMD service center .

Also the EMD service center stores the content file CF in the database attaches the global unique content IDs to individual content files CF and centrally manages them. Also the EMD service center stores the produced key file KF in the KF database and centrally manages it by using the content ID.

Also in the EMD service center the secure container storing the content file CF read out from the CF database and the key file KF read out from the KF database is produced and the secure container is stored in the secure container database.

Thereafter the secure container database is accessed by the service provider and the secure container is supplied to the service provider .

Next the service provider produces a secure container storing the content file CF and key file KF stored in the secure container and the price tag data indicating the sales price of the content data.

Then the service provider distributes the secure container to the user home network by using a predetermined communication protocol in a format not depending upon the related communication protocol or by storing the same in a storage medium.

In the user home network in the case of on line the secure container is provided to the SAM etc. via the CA module in the SAM etc. the content key data Kc and usage control policy data etc. stored in the key file KF are decrypted by using the distribution use key data KDto KD and the handling such as the purchase form of the content data stored in the content file CF is determined based on the decrypted usage control policy data .

Also in the SAM etc. the usage log data indicating the purchase log etc. of the content data is produced and the usage log data is transmitted to the EMD service center .

Also where the secure container is distributed from the SAM of the user home network to the SAM of the user home network processing similar to that of the SAM is carried out in the SAM and the usage log data is transmitted from the SAM to the EMD service center .

Note that the processings with respect to the secure container in the user home networks and are the same as the processings in the user home networks and in the first embodiment and second embodiment mentioned above.

Also in the example shown in the case where the secure container storing the content file CF and the key file KF was transmitted from the EMD service center to the service provider and from the service provider to the user home network the case of in band was exemplified but it is also possible to separately transmit the content file CF and the key file KF by the same route the case of out of band .

Also as shown in it is also possible if the content file CF is supplied from the EMD service center to the service provider the service provider supplies the content file CF to the user home network and at the same time the key file KF produced in the EMD service center is supplied from the EMD service center to the SAM and SAM of the user home networks and

In the EMD system of the present embodiment the content provider produces for example the content file CF shown in .

Also the content provider sends the content ID of the content data content key data Kc electronic watermark management information contents of the electronic watermark information to be buried in the content data and the burial position information identifier CP ID of the content provider identifier SP ID of the service provider providing the content data and the suggested retailer s price SRP of the content data to the EMD service center and the key file KF shown in is produced in the EMD service center .

Also the EMD service center stores the key files KF in the KF database and centrally manages the key files KF by using the content ID allocated to individual content data. At this time the content ID is produced by for example the EMD service center and globally uniquely determined for all of the content data provided by a plurality of content providers .

Next in the content provider a secure container storing the produced content files CF and the key files KF received from the EMD service center is produced and the secure container is stored in a common database .

In the common database secure containers provided by a plurality of content providers are centrally managed by using the content ID.

The service provider browses searches through the common database by using for example the content ID receives the intended secure container from the common database produces a secure container obtained by further storing the price tag data indicating the sales price of the content etc. in the secure container and distributes the secure container to the user home network .

In the user home network the secure container is provided to the SAM etc. via the CA module in the case of on line in the SAM etc. the content key data Kc and the usage control policy data etc. stored in the key files KF are decrypted by using the distribution use key data KDto KDor the like and the handling such as the purchase form of the content data stored in the content files CF is determined based on the decrypted usage control policy data .

Also in the SAM etc. the usage log data indicating the purchase log etc. of the content data is produced and the usage log data is transmitted to the EMD service center .

Also where the secure container is distributed from the SAM of the user home network to the SAM of the user home network processing similar to that in the SAM is carried out in the SAM and the usage log data is transmitted from the SAM to the EMD service center .

Note that the processings with respect to the secure container in the user home networks and are the same as the processings in the user home networks and in the above first embodiment and the second embodiment.

Also in the example shown in the case where the secure containers storing the content files CF and the key files KF were sent from the content provider to the common database from the common database to the service provider and from the service provider to the user home network the case of in band was exemplified but it is also possible to separately transmit the content files CF and the key files KF by the same route the case of out of band .

Also as shown in it is also possible if the content files CF are stored in the common database from the content providers the service provider obtains the content files CF from the common database and at the same time the key files KF are sent from the EMD service center to the service provider . In this case the service provider produces the secure container by storing the content files CF obtained from the common database the key files KF obtained from the EMD service center and the price tag data .

The common database centrally manages the content files CF by using the content IDs globally uniquely attached to the content data provided by a plurality of content providers .

Also as shown in it is also possible if the key files KF produced by the EMD service center are sent to the SAMs etc. of the user home networks and . In this case the service provider distributes the content files CF to the user home network .

The price tag data may be distributed to the user home network by the service provider too or may be distributed to the user home networks and by the EMD service center too.

When compared with the EMD system shown in mentioned above the EMD system of the present embodiment is different in the characteristic features that a plurality of EMD service centers are provided and that the content provider performs the charge processing etc. with the corresponding EMD service centers but is substantially the same in points other than that.

Also the content provider sends the content ID of the content data content key data Kc electronic watermark management information contents of the electronic watermark information to be buried in the content data and the burial position information identifier CP ID of the content provider identifier SP ID of the service provider providing the content data and the suggested retailer s price SRP of the content data to one EMD service center selected by itself or determined in advance among a plurality of EMD service centers and the key file KF shown in is produced in the EMD service center .

Also the EMD service center stores the key files KF in the KF database and centrally manages the key files KF by using the content IDs allocated to individual content data. At this time the content IDs are produced by for example the EMD service center and globally uniquely determined for the content data corresponding to all secure containers stored in the common database .

Next in the content provider a secure container storing the produced content files CF and the key files KF received from the EMD service center is produced and the secure container is stored in a common database .

In the common database secure containers provided by a plurality of content providers are centrally managed by using the content IDs.

The service provider browses searches through the common database by using for example the content ID receives the intended secure container from the common database produces a secure container obtained by further storing for example the price tag data indicating the sales price of the content in the secure container and distributes the secure container to the user home network .

In the user home network the secure container is provided to the SAM etc. via the CA module in the case of on line in the SAM etc. the content key data Kc and the usage control policy data etc. stored in the key files KF are decrypted by using the distribution use key data KDto KDor the like and the handling such as the purchase form of the content data stored in the content files CF is determined based on the decrypted usage control policy data .

Also in the SAM etc. the usage log data indicating the purchase log etc. of the content data is produced and the usage log data is transmitted to the EMD service center .

Also where the secure container is distributed from the SAM of the user home network to the SAM of the user home network processing similar to that in the SAM is carried out in the SAM and the usage log data is transmitted from the SAM to the EMD service center .

Note that the processings with respect to the secure container in the user home networks and are the same as the processings in the user home networks and in the above first embodiment and the second embodiment.

Also in the example shown in the case where the secure containers storing the content files CF and the key files KF were sent from the content provider to the common database from the common database to the service provider and from the service provider to the user home network the case of in band was exemplified but it is also possible to separately transmit the content files CF and the key files KF by the same route the case of out of band .

Also as shown in it is also possible if the content files CF are stored in the common database from the content providers the service provider obtains the content files CF from the common database and at the same time the key files KF are sent from the EMD service center to the service provider . At this time the key file KF is sent to the content provider from the EMD service center corresponding to the content provider produced the content file CF obtained by the service provider .

The service provider stores the content file CF obtained from the common database the key file KF obtained from the EMD service center and the price tag data to produce the secure container .

The common database centrally manages the content files CF by using the content IDs globally uniquely attached to the content data provided by a plurality of content providers .

Also as shown in it is also possible if the key files KF produced by the EMD service center are sent to the SAMs etc. of the user home networks and . Also at this time the key files KF are sent to the SAMs etc. from the EMD service center corresponding to the content providers preparing the content files CF provided to the SAM etc.

Also the service provider distributes the content files CF to the user home network . The price tag data may be distributed by the service provider to the user home network too or may be distributed by the EMD service center to the user home networks and

The EMD system of the present embodiment is different when compared with the EMD system shown in mentioned above in the point that the master source of the content data is sent from the content provider to the EMD service center and the content file CF is produced in the EMD service center . The points other than that are substantially the same.

The content provider sends the master source S of the content data to one EMD service center selected by itself or determined in advance among a plurality of EMD service centers and the content file CF shown in is produced in the EMD service center .

Also the content provider sends the content ID of the content data content key data Kc electronic watermark management information contents of the electronic watermark information buried in the content data identifier CP ID of the content provider identifier SP ID of the service provider providing the content data and the suggested retailer s price data SRP of the content data to the above one corresponding EMD service center and the key file KF shown in is produced in the EMD service center .

Also the EMD service center stores the content files CF in the CF database stores the key files KF in the KF database and centrally manages the content files CF and the key files KF by using the content IDs allocated to the individual content data. At this time the content IDs are produced by for example the EMD service center and globally uniquely determined for the content data corresponding to all secure containers stored in the common database .

Next in the content provider a secure container storing the content file CF and the key file KF received from the corresponding EMD service center is produced and the secure container is stored in the common database .

In the common database secure containers provided by a plurality of content providers are centrally managed by using the content ID.

The service provider browses searches through the common database by using for example the content ID receives the intended secure container from the common database produces a secure container obtained by further storing for example the price tag data indicating the sales price of the content in the secure container and distributes the secure container to the user home network .

In the user home network the secure container is provided to the SAM etc. via the CA module in the case of on line in the SAM etc. the content key data Kc and the usage control policy data etc. stored in the key files KF are decrypted by using the distribution use key data KDto KDor the like and the handling such as the purchase form of the content data stored in the content files CF is determined based on the decrypted usage control policy data .

Also in the SAM etc. the usage log data indicating the purchase log etc. of the content data is produced and the usage log data is transmitted to the EMD service center .

Also where the secure container is distributed from the SAM of the user home network to the SAM of the user home network processing similar to that in the SAM is carried out in the SAM and the usage log data is transmitted from the SAM to the EMD service center .

Note that the processings with respect to the secure container in the user home networks and are the same as the processings in the user home networks and in the above first embodiment and the second embodiment.

Also in the example shown in the case where the secure containers storing the content files CF and the key files KF were sent from the content provider to the common database from the common database to the service provider and from the service provider to the user home network the case of in band was exemplified but it is also possible to separately transmit the content files CF and the key files KF by the same route the case of out of band .

Also as shown in it is also possible if the content files CF are stored in the common database from the content providers the service provider obtains the content files CF from the common database and at the same time the key files KF are sent from the EMD service center to the service provider . At this time the key files KF are sent to the content provider from the EMD service center corresponding to the content providers preparing the content files CF obtained by the service provider .

The service provider stores the content file CF obtained from the common database the key file KF obtained from the EMD service center and the price tag data to produce the secure container .

The common database centrally manages the content files CF by using the content IDs globally uniquely attached to the content data provided by a plurality of content providers .

Also as shown in it is also possible if the key files KF produced by the EMD service center are sent to the SAMs etc. of the user home networks and . Also at this time the key files

KF are sent to the SAMs etc. from the EMD service center corresponding to the content providers preparing the content files CF provided to the SAMs etc.

Also the service provider distributes the content files CF to the user home network . The price tag data may be distributed by the service provider to the user home network too or may be distributed by the EMD service center to the user home networks and

In the EMD system of the present embodiment for example the content file CF shown in produced by the EMD service center by using the master source provided from the content provider to the EMD service center or the content file CF shown in produced by the content provider and provided to the EMD service center and the key file KF shown in produced by the EMD service center are distributed by the EMD service center via the service provider or directly to the SAM of the user home network .

Here the service provider sends the price tag data indicating the sales price of the content file CF to the user home network and at the same time registers and authenticates the price tag data in the EMD service center .

In the EMD system of the present embodiment for example the SAM of the user home network becomes the distribution business for distributing the content files CF and key files KF obtained from the service provider or the EMD service center to the SAM in the user home network and or SAM etc. in the user home network

Note in this case for example the EMD service center prohibits selling redistributing the purchased content data C while adding a certain sales margin to obtain a profit after the SAM purchases the content data C stored in the content file CF.

In the EMD system of the present embodiment it is permitted to the SAM to copy the content data C to another SAM under the condition that content data for which the purchase form is not determined or content data C for which reproduction charge is determined as the purchase form is redistributed without a sale profit margin. Note that this will be referred to as inter apparatus redistribution.

Also in the EMD system of the present embodiment inter apparatus trade in a form without a sale profit margin is permitted for a content file CF or secure container distributed from the service provider to the SAM .

Also in the present embodiment where the SAM performs sells distributes the content data C in a form taking a sales profit margin the SAM registers itself in the EMD service center as distribution business and receives permission and at the same time registers the price tag data indicating the sales price of the content data C in the EMD service center . Then it directly receives the content file CF and the key file KF from the CF database and the KF database in the EMD service center not via the service provider .

In the EMD system of the present embodiment the characteristic feature resides in that each of the content providers functions as an EMD service center in addition functioning as a content provider.

In this case where there are a plurality of content providers each content provider functions as an EMD service center .

A content provider distributes a secure container storing the content file CF and the key file KF to the service provider .

The service provider further adds the price tag data to the content file CF and the key file KF stored by the secure container to produce a secure container and distributes this to the user home network .

In the user home networks and the purchase form etc. of the content file CF are determined based on the usage control policy data stored in the key file KF the usage log data in accordance with that is produced and this is transmitted to the EMD service center in the content provider .

The EMD service center of the content provider distributes the profit paid by the users of the SAMs and with the corresponding service provider based on the usage log data .

Also the log data concerning the distribution service is sent from the CA module of the user home network to the corresponding service provider whereby the charge processing with respect to the distribution service is carried out in the service provider .

In the above embodiments the case where audio data was used as the content data was exemplified but it is also possible to use video data audio and or video data text data and a computer program or the like as the content data.

Also in the above embodiments the case where the key files KF were produced in the EMD service centers and was exemplified but it is also possible to produce the key files KF in the content providers and .

In this case the format of the key file KF corresponding to becomes as shown in . As shown in the related key file KF has basically the same information as the key file KF shown in except that signature data produced by using the secret key data Kof the content providers and are used.

Also in the above embodiments the case where the usage control status data is transmitted from the user home networks and to the EMD service centers and in real time was exemplified but it is also possible if the usage control status data is transmitted to the content providers and and or service provider . By this the content providers and and the service provider can quickly grasp the purchase situation of the contents provided and distributed by themselves and can reflect the same in their service thereafter.

Below effects by the EMD system of the above embodiments will be explained again while mentioning the related art and the problems thereof.

With the ROM type storage media which had been used as the means for distributing digital content content data in the days when digital broadcasts data broadcasts and the Internet and other digital networks were not so developed the digital content was stored and distributed in an unencryped state. In the days when the digital network was not so developed it was enough to consider methods for preventing casual copying by users on the user home network for the protection of the copyrights of these contents.

In recent days where the digital network has been developed however since ROM type storage media carrying unencrypted content can be obtained by general citizens anytime and everywhere any individual can purchase one and easily compress and upload the data on the network. Particularly the Internet is a network connecting the entire world. Therefore it becomes possible to freely upload the unencrypted content on the Internet and for people to download it on their own personal terminals. Accordingly there has arisen a possibility of serious infringement of the copyrights of the owners of the content content providers .

Further it also becomes possible for people not to upload the content in the unencrypted state but to bury electronic watermark information of their own in that content encrypt the data and charge for the data on their own and thereby deliberately sell the digital content on the Internet behind the scenes without the permission of the copyright owner. At this time since a share of the sales is not returned to the owner of the content the copyright of the owner of the content content providers will be seriously infringed.

Also by getting the permission of the copyright owner and concluding a contract for returning part of the sales to the owner of content content provider in advance it becomes possible to offer a distribution service capable of generating profit by distributing the digital content but basically the content provider does not favor circulation by such a secondary usage of content. Rental secondhand sale etc. are other types of business by secondary usage of the content.

When a distribution service by secondary usage appears the problem of infringement of copyrights is sure to occur so a long time is taken for setting up the service in the right direction. The distribution service ends up being first started without establishing a contract with the content provider. After the problem of infringement of copyrights occurs the distribution of profit to the owners and protection of the copyrights start to be considered and permission as the distribution service is obtained. The rental CD and the rental video businesses correspond to this. The secondhand sale of game software etc. is a serious problem. In the secondhand sale of game software part of the profit from the sales is not returned to the owners of the content. The owners have brought court actions against this but these have been dismissed. This is very hard on the owners. Secondhand game software is sold in large volumes with a price of half or less of new software therefore the market is very attractive for the users and a large influence is exerted upon the sale of new software.

Secondary usage of content means when a user who purchases a ROM type storage medium on which digital content has been already stored by the owner of the content using the ROM type storage medium distributed as a circulating means to obtain a profit further circulates the product. The fact that the purchasing user obtains a profit is not considered desirable from the standpoint of the content provider owner even if part of the profit is returned to it. With movie content etc. the owner of the content is protected by law in the form of recording rights distribution rights. When purchasing content which an owner circulates in the public the assumption is that it not be circulated further from the purchasing user. Groups of owners of game software have raised suits at courts to suppress secondary usage businesses attempting to apply such distribution right to game software as well.

Owners of content want to get distributors distributing digital content which they hold copyrights to under their control they would like to know to whom the content is being distributed to . When there is a distributor desiring to distribute digital content to which one holds a copyright so as to provide a distribution service and make a profit a system is desirable by which the owner of the content can directly supply the digital content.

Note that the distributor spoken of here designates a business that obtains a profit by collecting the profit margin of a few percent with respect to the price of the digital content.

A case where a profit margin is collected when delivering digital content to another apparatus storage medium is defined as a content trade session distribution service while a case where a profit margin is not collected is defined as inter apparatus redistribution. The latter is legal under the principle of supra distribution.

In the current system for management of distribution of digital content over the network where the service provider authors the content of its own distribution service from a ROM type storage medium storing unencrypted content circulated by the content provider for a distribution service when considering the situation where one digital content owned by the content provider is distributed by a plurality of service providers irrespective of the fact that it is identical content authoring is carried out so that the rights are cleared by a CA module electronic settlement tool employed by each service provider. Therefore the formats of the encryption key content key data to be used and the licensing conditions of the content usage control policy data are different according to each service provider so common rights clearing rules cannot be provided on the user home network. In such a case by settling up for all of the key data used by the CA modules electronic settlement tools by the CA modules electronic settlement tools of the network apparatuses and then following the SCMS rules common rights clearing rules can be realized on the user home network.

Also even if the content encrypted by the key of a CA module electronic settlement tool and the key data are passed through the network apparatus as they are and stored on a storage medium of the storage apparatus via the user home network bus IEEE1394 or the like and the purchase and settlement processing of the content can be performed remotely through the network apparatus from an apparatus connected to the 1394 bus since there is a descrambler for decrypting the encrypted content in the network apparatus in the end reproduction cannot be carried out unless the content and the key data are returned back to the network apparatus at the time of reproduction network CA .

As explained above the existence of the ROM type storage medium storing unencrypted content which has been widely circulated in the world up to the present is at the root of the problem for current digital content network distribution services. This is a system where the form of the digital content can be produced by a person other than the content provider and where a person selling the content to a user can obtain payment for it. Therefore the profit of the content provider is illegitimately infringed by secondary usage of the content. Also the distribution of the authored digital content is not strictly managed by the content provider therefore it is difficult to monitor all profits earned by the digital content which it holds a copyright to and if its share of the profits is being returned to it.

Namely in the EMD system of the present embodiment the digital contents authored by the content provider are all managed in a database on the content provider side by preparing content format and usage control policy data on the content provider side. The usage control policy data of the content is further authenticated and registered in the EMD service center clearinghouse as a third party reliable authority manager.

By doing this the interested parties of the content provider can place the rights clearing rules of the digital content completely under their control and manage the distribution channels at the content provider side. Also in the present case steps are taken so that a distributor interposed between the user cannot see the content of the data of the usage control policy produced at the content provider side.

Also in the EMD system of the present embodiment the ROM type storage medium is considered as one means of distribution and the existence of the digital content stored there is freed from the ROM type storage medium. A content format having value of existence by solely digital content without regard as to means of distribution and channels of distribution is proposed. The digital content is managed in a certain prescribed format on the content provider side. Therefore by considering the mounting of the digital content of that format in a ROM type storage medium whether the content is circulated as a ROM type storage medium or circulated over a digital network it becomes possible to provide common rights clearing rules for ROM RAM and for network RAM on the user home network. This is provided so that sale sessions of the digital content are all defined and managed by the content provider. Due to this common rights clearing not depending on the means of distribution or the channel of distribution becomes possible. Also by stipulating this format of content defined at the content provider side as the minimum unit for trading the digital content common rights clearing rules can be provided without regard as to the type of the content format used in the subsequent distribution process. By returning the charge information produced at the time of purchase at the user home network not to the service provider but to the EMD service center as a third party reliable authority manager and returning it therefrom to the service provider the problems of the business of secondary usage of content were solved.

As explained above according to the present invention it becomes possible to handling data in the data processing device of the content data provided by the data providing apparatus based on the usage control policy data of the data providing apparatus.

As a result it becomes possible to suitably protect profit according to the content data by the interested party of the data providing apparatus and at the same time the load of the inspection by the related interested party can be reduced.

