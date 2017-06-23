---

title: Smartcard file system and file selection method thereof
abstract: The invention provides a Smartcard file system and its method for selecting file. Said file system, including MF as well as a variety of DFs and Efs in the MF, wherein application root directory (ADF) is added in the MF; the tile attributes of said ADF, DF and EF of the tile system include the Application Identifier (AID); when visiting with HTTP protocol, the AID is understood as a long file name. External entities accessing said file system with the HTTP protocol, namely locating the application and file managed with CWS via URL; in URL, AID of directory or file identities its long file name, so that Smartcard file system also can support long file system and the way of selecting file of URL, which makes Smartcard to support the WEB services easier and more accepted by the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08977658&OS=08977658&RS=08977658
owner: China Unionpay Co., Ltd.
number: 08977658
owner_city: Shanghai
owner_country: CN
publication_date: 20101108
---
The present invention relates to the technical field of Smartcard and relates to a file system of the Smartcard.

Smartcard is also named as Integrated Circuit card i.e. IC card. Smartcard including an Integrated Circuit chip embedded in a plastic substrate is packaged as a form of card and its shape is similar to a magnetic card covered with magnetic stripe. A concept of Smartcard came forth in 1970s. In 1976 BULL corporation in France firstly contrived a Smartcard product and further applied this technology to multi fields such as finance traffic medical treatment identity certificate and the like. The Smartcard chip has the capability of writing data and storing data. When necessary contents stored in the memory of the Smartcard can be conditionally provided for outer reading interior information process and determination.

The Smartcard file system is analogous to a tree like file system of DOS. ISO7816 supports two kinds of file Dedicated File named as DF and Elementary File named as EF . DF is in some wise similar to DOS directory while EF is in some wise similar to data file. DF s in the DF which of course could further include DF s is similar to DOS subdirectory. Similar to file system of DOS the Smartcard file system also must include a root file that is a DF and this root file is called as Master File named as MF that is similar to the root directory of DOS. 

In structure of the Smartcard file system it can but has one MF and number of DF is optional. MF and DF play the role of managing and forming the structure of tree like file system and the file for storage data is EF.

MF is the root of Smartcard file system and all kinds of DF and EF can be created in the MF. Although the file system permits to directly generate all sorts of application file of EF the best method for organizing file lies in allotting one DF to every kind of application and further organizing all kinds of application data of EF in the corresponding DF.

DF in which all kinds of DF and EF can be created contains information of file control and distributable storage area. Generally one DF is used to storing all data corresponding to one application. DF occupies a block of SRAM in the user memory once the DF is created the size of DF s SRAM is invariable. For EF in this DF however the size of memory used by EF can be redistributed and also can be deleted. After deleting the DF DF s and EF s in the deleted DF is also deleted simultaneously the block of memory released by deleting can be used by other DF s .

The existing Smartcard file system follows defining of ISO7816 4. As shown in wherein MF indicates the logic root directory of the file system which has only one MF DF Dedicated File usually is the root directory of the Smartcard application similar to subdirectory which exists in the MF or other DF EF Elementary File usually is used to store cipher keys or application data and it exists in the MF or DF.

Wherein MF s attribute lies in File Identifier named as FID of two bytes 3F00 hex and same to hereinafter 

As can be seen for supporting WEB service it is necessary to re define the structure of file system such that the file system can support WEB service namely it is necessary to define a new directory node for supporting WEB service which mainly means that the file system defined by ISO7816 4 employs DF as root directory of application and the DF can be embedded but lack of characteristic in giving prominence to application root directory. Moreover for supporting long file name it is necessary to re define characteristic for every directory node in file system and it is necessary to add the way of selecting file namely the way of selecting file need to support selecting way of URL as Smartcard is required to support WEB service and it is necessary to support creating temporary file 

The propose of the invention is to provide a new Smartcard file system for supporting WEB service and long file name.

In accordance with one aspect of the invention A Smartcard file system is provided it includes MF Master File as well as a variety of DFs Dedicated Files and Efs Elementary Files in the MF wherein application root directory ADF is added in the MF said ADF in which DF s or EF s is set is the main directory of Smartcard application.

Application directory file EFdir and Smartcard WEB server configuration information directory DFcws and WEB server basic configuration information file EFcfg and WEB server authorizing user information file EFuser configured in the DFcws are added in the MF.

The EFdir records all applications and its associated information installed in the file system and said EFdir is a directory entry file which records the entries pointing to certain said ADF of the applications installed on the Smartcard.

Further File Identifier FID of attributes of said ADF and DF is 2 bytes that can not be 3F00 or 0000 or FFFF and Application Identifier AID up to 16 bytes and at least 5 bytes is understood as a long file names when accessing with the HTTP protocol. Attributes of said EF include storage type identifying that the file is volatile or nonvolatile Application Identifier AID up to 16 bytes and at least 5 bytes is understood as a long file names when accessing with the HTTP protocol. If the storage type of the file is identified as nonvolatile then its storage area is located in a nonvolatile storage area typically EEPROM or FLASH if the storage type of the file is identified as volatile its storage area is located in the volatile storage area typically RAM.

In accordance with another aspect of the invention A Method for selecting file in a Smartcard file system is provided said Smartcard file system including MF Master File as well as a variety of DFs Dedicated Files and Efs Elementary Files in the MF in which also has application root directory ADF external entities accessing said file system with the HTTP protocol namely locating the application and file managed with the Card WEB Server CWS via URL. The external entities locating the application and file managed with the CWS via URL includes the following steps 

Step 1 the external entities send a service request message to the CWS according to HTTP protocol two parts information of path and query string identified in the message 

Step 2 the CWS locates requested application and path according to the content of two parts of path and query string.

Further the path of said URL contains the application name which is expressed with hexadecimal ASCII code of Application Identifier AID preceded by three characters of AID and is followed by the host name.

Further the directory file name is coded to the URL via its FID two byte FID encoded as four bytes ASCII strings between which using separator. The AID of directory or file identifies its long file name and its hexadecimal string is used to express the long file name and is encoded to the URL.

Further if the URL does not contain the AID the CWS parses the file path in current application if the context of current file does not contain current application the file path is parsed in the root directory of the MF. If the URL using reserved FID 7FFF in any file system it identifies a reference to the current application if the channel does contain the current application then an error status is returned.

Further if the URL does not contains the AID or identifier of 7FFF then the CWS matches requested path to the file in the current directory if lack of the current directory or the current application it returns an error status.

Further when the accessing the Smartcard with the HTTP protocol if the application path is not is not designated the CWS will automatically form the application list as return results according to the content of the application directory file EFdir 

The present invention makes the traditional Smartcard file system also can support long file system and the file selecting way of URL which makes the Smartcard supporting WEB service more easily and more acceptable by the user. Liking as a generalist the new Smartcard file system shows different characteristics and methods under different interfaces.

This proposal puts forward a new type of Smartcard file system and its key features lie in extending the traditional Smartcard file system defined by ISO7816 4 and making it compatible with long file name system similar to FAT16 or FAT32 which are indicated for Smartcard better meeting the usage habits in case of supporting WEB service.

According to technical problems to be solved described in the background a re defined structure of file system is shown in .

Note If the storage type identifier of file is identified as nonvolatile then its storage area is located in a nonvolatile memory area typically EEPROM or FLASH if the storage type identifier is identified as volatile then its storage area is located in a nonvolatile memory area typically RAM.

In the HTTP protocol terminals locate applications and documents managed with CWS via URL. For disk file system the definition of the URL refers to RFC 1738 according to RFC1738 provision the URL consists of several parts protocol name host name and file path is a typical URL structure including protocol name host name and file path.

 identifies domain name of the host or its IP address in form of four groups decimal number gather separated by . . The form of domain name is described in section 3.5 of RFC1034 13 and section 2.1 of RFC 1123 5 namely domain sign string separated by . domain signs use letter or number at its beginning and ending and may also contain character. The rightmost domain sign can not begin with a number so that the domain name is distinguished from IP address by grammatical structure.

 designates link port. It is used to assign a default port to the protocol. Port in decimal form also can be optionally assigned to a port that is separated with the host by a colon. If you neglect the port then the colon should also be neglected.

The URL path URL query string and in front of are optional. In case without both and then can also be omitted. and in and section are reserved characters. character in the HTTP can be used to indicate hierarchy.

External entities terminals access the file system with the HTTP protocol. External entities access the file system via the URL in the browser after the browser connecting with remote servers for the browser the CWS on Smartcard is also a remote Web server through the native network device a service request message http request message is sent to the remote server CWS according to the protocol such as http . Two parts information of path and query string are identified in the message CWS locates requested applications and path according to the content of two parts of path and query string. Except for two parts of path and query string parts before the two parts are possibly existed in the request message and the CWS can make the appropriate dispose may not.

The present invention requests that the file path should use full path and the file path may contain the application name application name is expressed with hexadecimal ASCII code of the AID preceded by three characters of AID and the application name followed by the host name. is a typical URL structure file path including the application of the AID.

If the URL contains the AID after CWS handling the operation of application selection would be carried out in accordance with the order front to back and the context of current file is set.

If the URL does not contain the AID the CWS parses the file path in current application if the context of current file does not contain current application the file path is parsed in the root directory of the MF.

Reserved FID 7FFF is used in . In any file system it identifies the reference to the current application if the channel does contain the current application then an error status is returned.

If the URL does not contains the AID or identifier of 7FFF then the CWS matches the request path to the files in the current directory. If lack of the current directory or the current application it returns an error status.

In general the CWS only parses file path part of the URL other parts is parsed outside the card. If the CWS receives the protocol name and host name a necessary check can be done.

There are no long file names only including two bytes of the FID in ISO7816 file system directories and files. In this case using encode format of the URL defined as follows 

The hexadecimal encode of the FID or also possible long file name ASCII encode in AID can be followed behind the AID. The CWS can automatic distinguish them based that the length of the FID must be 2 bytes and AID must be at least 6 bytes.

