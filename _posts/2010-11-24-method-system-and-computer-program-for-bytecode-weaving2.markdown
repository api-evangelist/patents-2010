---

title: Method, system and computer program for bytecode weaving
abstract: A method, computer apparatus and computer program product for bytecode weaving is described herein. The method includes determining when a code module such as an OSGi bundle that requires bytecode weaving becomes available for loading into a system. Code associated with the code module is loaded. This code may be part of the module itself or part of a separate entity, such as an OSGI bundle fragment, but does not require weaving. Responsive to loading the code associated with the code module, a reference is received to the entity responsible for loading the code associated with the code module. A code entity (which does require weaving) within the code module is identified and a woven set of bytes are provided to the code loading entity identified via the returned reference. Consequently, the woven set of bytes represents a transformed version of the identified code entity.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09652205&OS=09652205&RS=09652205
owner: International Business Machines Corporation
number: 09652205
owner_city: Armonk
owner_country: US
publication_date: 20101124
---
This application claims priority under 35 U.S.C. 119 a to European Patent Application Serial Number 09177088.3 filed Nov. 25 2009 entitled A METHOD SYSTEM AND COMPUTER PROGRAM FOR BYTE CODE WEAVING the entirety of which is incorporated herein by reference.

Bytecode weaving is the process of transforming a class file conformant to the Java programming language and transforming the class file into something potentially more complicated. Typical uses of bytecode weaving include adding code to address some cross cutting concern for example to add method level logging to a set of classes or to initiate and complete global transactions around methods that write to a database. Bytecode weaving can take place at compile time at package deployment time or at load time. Java and all Java based trademarks and logos are trademarks of Sun Microsystems Inc. in the United States other countries or both. 

Load time bytecode weaving is generally perceived as the most flexible. It allows generic code to be created that will run on a variety of platforms. Such generic code can then be woven at the last possible moment in order to make it appropriate to for example a particular platform.

In order to perform bytecode weaving at class load time it is necessary to intercept the class bytecode and modify it before it is first loaded into the runtime system. This is however not easily achievable in all environments.

The OSGi Alliance formerly known as the Open Services Gateway Initiative is a standards organisation which has defined a framework for remotely managing the modularity and integration of Java applications. The OSGi environment is an example of an environment in which it is not easily possible to obtain access to code before it is loaded at runtime.

The concept of an OSGi application is not standardised but commercially available products have defined an application as a collection of OSGi bundles code modules . The concept of a bundle is standardised in OSGi and bundles may specify dependencies on other bundles packages or services.

Each OSGi bundle has its own class loader which is responsible for loading and defining the classes contained inside the bundle into the runtime. In order to weave a class at load time it is necessary to gain access to the class loader for the bundle that will load that class and modify its behaviour. The difficulty with the OSGi environment is that the class loader is intentionally hidden and not easily accessible.

One example of where this is particularly problematic is in relation to the Java Persistence application programming interface API also known as JPA . The JPA is an object relational mapping specification that allows client code to transparently persist Java Objects to a Relational Database and retrieve them at a later time. The JPA specifies a number of performance optimisations which are designed to reduce the amount of data that should be retrieved from the database. This is particularly noticeable when one JPA entity the name for objects that can be persisted by JPA references one or more other entities.

In order to support this type of optimization without requiring complex configuration or coding by clients JPA specifies an integration point for the use of bytecode weaving. This strategy allows a JPA provider to rewrite the bytecode of an entity class so that internal state can be lazily loaded on a just in time basis.

In order to perform bytecode weaving the JPA provider provides a container implementer with a ClassTransformer. This can be used by the container to transform the bytecode before it is loaded by the application s ClassLoader. In JEE this is a relatively simple task as the JEE Application Server has complete control over the Application ClassLoader. In other environments such as OSGi the ClassLoader is not controlled by the container and is not easily available to the runtime. At this point it is very difficult for the container to weave any classes at load time.

One existing solution to this problem is to use a Java Agent. These Java Agents allow container code to interpose in the class loading process and to force class redefinition after a class has been loaded. Unfortunately Java agents can severely impact the performance of a Java virtual machine JVM as they are invoked during the loading of every single class. Further to this Java agents can expose serious security risks as they can be used to redefine any class in the runtime including parts of the container.

This problem is not however limited to the scope of JPA but applies generally to the case where a container needs to apply known or dynamically generated aspects to an application class at class load time in an OSGi framework.

One implementation of the OSGi environment known as Equinox and provided by the Eclipse Foundation has provided a workaround for the problem described above. The Equinox implementation specifies an exit point called a ClassLoadingHook which provides a mechanism to replace an original set of bytes with a new transformed or bytecode woven set of bytes. This is described in Thorsten Keuler and Yury Kornev in NAOMI 08 Proceedings of the 2008 workshop on Next generation aspect oriented middleware 2008 .

The solution described in the aforementioned document is however very specific to the Equinox OSGi environment rather than being more generally applicable.

According to a first aspect there is provided a method for bytecode weaving comprising determining when a code module that requires bytecode weaving becomes available for loading into a system loading code associated with the code module said code having been identified as not requiring weaving responsive to loading said code associated with the code module receiving a reference to the entity responsible for loading the code associated with the code module identifying a code entity within the code module wherein the code entity requires weaving and providing a woven set of bytes to the code loading entity identified via the returned reference wherein the woven set of bytes represents a transformed version of the identified code entity.

The code identified as not requiring weaving may be code that exists within the code module itself. In a preferred embodiment however an enhancing entity is generated which comprises code identified as not requiring weaving. This enhancing entity is then associated with the code module.

Code weaving dependencies are preferably added to the enhancing entity and the step of loading code associated with the code module preferably comprises loading code within the enhancing entity.

A code entity that requires weaving e.g. a class is preferably selected from a plurality of code entities that require weaving. In one embodiment code entities requiring weaving are selected according to a predefined order.

In a preferred embodiment the bytes representing the code entity that requires weaving are loaded and transformed into the woven set of bytes.

In a preferred embodiment it is determined when a code module that requires bytecode weaving becomes available for loading into a system by using a listener to detect when the code module resolves any dependencies specified by the code module.

According to a second aspect there is provided an apparatus for bytecode weaving comprising a component for determining when a code module that requires bytecode weaving becomes available for loading into a system a component for loading code associated with the code module said code having been identified as not requiring weaving a component responsive to loading said code associated with the code module for receiving a reference to the entity responsible for loading the code associated with the code module a component for identifying a code entity within the code module wherein the code entity requires weaving and a component for providing a woven set of bytes to the code loading entity identified via the returned reference wherein the woven set of bytes represents a transformed version of the identified code entity.

According to a third aspect there is provided a computer program comprising program code means adapted to perform a method for bytecode weaving when said program is executed on a computer the method comprising determining when a code module that requires bytecode weaving becomes available for loading into a system loading code associated with the code module said code having been identified as not requiring weaving 

responsive to loading said code associated with the code module receiving a reference to the entity responsible for loading the code associated with the code module identifying a code entity within the code module wherein the code entity requires weaving and providing a woven set of bytes to the code loading entity identified via the returned reference wherein the woven set of bytes represents a transformed version of the identified code entity.

OSGi framework comprises a number of bundles code modules and with a set of bundles typically making up an application. As discussed previously it is sometimes desirable to transform the classes in a bundle at load time via the process of bytecode weaving.

A SynchronousBundleListener bundle listener is registered with the OSGi framework by bundle to detect installation events step . Bundle listener therefore determines when a bundle is being installed e.g. bundle within the framework step .

The listener then determines whether the bundle will require bytecode weaving at step . If no weaving is required then the process loops round to detect the next time a bundle is installed.

In this instance weaving is required as bundle has been configured to add method entry and exit trace calls to all classes in the package org.acme.my.application and bundle contains classes in that package. It should be noted that this is merely one example of when weaving might be required. The details of the mechanism for determining whether a bundle needs to be woven are not essential to the preferred embodiment and so will not be discussed herein in any detail.

As a result a bundle to be woven is detected at step . Bundle wants to weave bundle . Bundle need not realise that it needs to be woven or if bundle is aware that it needs to be woven bundle need not know which bundle will be responsible for doing the weaving.

 Note although bundle is shown in bundle has not yet been resolved the process of resolving is described later within framework . As a result it is not available to supply dependencies or load classes 

Each bundle in the framework has a bundle object associated with it. The bundle object represents the physical bundle in the runtime. It includes metadata about its associated bundle and also includes methods that can be used to interact with the bundle.

At step the bundle object is accessed for the bundle being installed. The bundle object can be used to determine the bundle s identifier and other metadata. This information is useful when determining whether the bundle needs to be modified. As previously described bytecode weaving can substantially modify a class. This can include adding external dependencies. In OSGi this can be problematic as a bundle must express any dependencies on code from other modules in its metadata prior to being resolved.

The metadata collected in step can be used to determine whether any additional external dependencies i.e. over and above those specified in the original metadata will be added to bundle by the weaving process.

At step in accordance with a preferred embodiment bundle uses the metadata from step to create a bundle fragment that can attach to bundle . Typically this bundle fragment will be created dynamically but in the case where the bundles to be woven are known in advance these fragments may exist statically. A bundle fragment is an OSGi concept typically comprising code and metadata.

Additional content is added to the bundle metadata using bundle fragment headers. These headers ensure that bundle can load the additional code dependencies that will be added by the weaving process.

Alternatively each bundle has an associated manifest which describes the bundle and its external dependencies. If the bundle can be intercepted before it is installed into the framework then this manifest can be rewritten to ensure that the additional code dependencies can be loaded. This solution is more complicated it either requires that bundle has non standard access to the internals of the framework or that any bundles to be woven are modified before they are installed into the framework. This pre modification essentially performs deployment time weaving and removes the many advantages of load time weaving.

The new fragment preferably also contains a dummy class. This class may be but does not have to be entirely empty. The presence of this dummy class ensures that bundle has access to a known class in bundle that can be loaded without causing any of the classes that need to be woven to be loaded.

A fragment may be generated dynamically using standard classes in the Java API. The fragment metadata including the intended host bundle and any additional dependencies is added to a java.util.jar.Manifest. This Manifest can then be written to a java.util.jar.JarOutputStream. This JarOutputStream may output data to a file on disk an in memory byte array or some other storage using the standard Java chaining mechanism for streams. In addition to the Manifest bundle may wish to add another entry containing a Java class file the dummy or other classes . This can be achieved by calling putNextEntry and writing out the bytes of the class file to be added. Once the fragment has been generated either as a byte array a file or in some other form one of the standard Java input classes may be used to obtain a java.io.InputStream that can load the fragment. Examples include java.io.ByteArrayInputStream or java.io.FileInputStream. The resulting InputStream can then be given to the framework to install.

Once the bundle fragment from step has been installed into the framework the listener has finished processing the installation event. The listener then returns to step until another bundle is installed.

At some time later the OSGi framework will attempt to resolve bundle . In step bundle registers to listen for these events either using a second BundleListener or using the same BundleListener that was registered in step . For simplicity it is assumed that the same BundleListener is used however use of a separate listener is equally appropriate.

The fragment to the identified bundle installed at step will be attached when the bundle is resolved within the framework. As previously specified a bundle may specify dependencies on other bundles that is to say a bundle may import or export packages services or other bundles. Resolution takes place when a bundle is appropriately wired to other components packages bundles within the framework via such imports and or exports.

In step the listener is notified that a bundle has resolved. The listener performs a simple check step to see if that bundle needs to be woven. As any bundles that need to be woven have already been identified in step it is simple to check whether the resolved bundle needs further processing. If the bundle does not require weaving then the listener returns to step and waits to be notified of another bundle resolving. In the case where a bundle does need to be woven the system proceeds to step .

A fragment is used by the preferred embodiment to obtain access to the hidden class loader. The way in which this is achieved will be described below. It should however be appreciated that the use of a fragment containing a dummy class is not essential. The key point here is that reference to the class loader should be obtained by loading a class inside bundle which is definitely not going to be woven by bundle . This is not something that can necessarily be easily discovered and thus an effective way forward is to use a fragment containing a dummy class.

At step the bundle object is accessed again in order to call loadClass on the dummy class within the bundle fragment . Calling loadClass returns an instance of java.lang.Class which contains a public method getClassLoader getClassLoader is called at step and this returns a reference to the previously hidden class loader responsible for loading classes contained within bundle .

It should be appreciated that java.lang.Class is part of core Java and the other methods mentioned are well known and will not be discussed in any more detail herein.

At step the bundle object is used to obtain the classes that are to be woven. Various known public methods may be specified by the bundle object as mechanisms for retrieving the relevant classes. One such method is getResource. This method is called whilst specifying the name of the resource to return. A URL is then returned which provides access to the resource and it is possible to open a stream to that URL in order to retrieve a set of bytes. findEntries is another example of a public and known method which may be used to return a list of the class resources within a bundle. This is useful when precise classes are not yet known for example when bundle wishes to weave every class in the org.acme.my.application package. Alternatively the ClassLoader using the reference returned at step itself could be used to find the class definitions and read their content.

It should also be appreciated that while the process describes accessing the bundle object multiple times this is not necessarily done. Information from the bundle object may instead be cached upon first access.

At step a class to be woven is selected. This selection step is important and should ensure that the classes are processed in an order that will not cause classes that have yet to be woven to be loaded. A simple algorithm to apply in this case is as follows. Separate the classes to be woven into two groups one group containing interface classes and one containing implementation classes. Start with the group of interface classes and process the classes in hierarchy order i.e. process the most general super interface first . Once all of the interfaces have been processed then perform the same selection with the group of implementation classes. If either of the groups contain two or more unrelated classes classes that do not share a direct inheritance hierarchy then these classes may be processed in any order. It should be noted that this algorithm is only an example any other algorithm that produces a suitable result may be used.

The bytes representing the selected class are loaded into a byte array step and the desired transformation is applied to those bytes at step . The transformation byte code weaving can be achieved via the java.lang.instrument package which contains the ClassFileTransormer interface. Again java.lang.instrument and the ClassFileTransformer interface are well known and are part of core Java.

Having transformed the bytes reflection is used at step to call the defineClass method on the bundle ClassLoader passing in the transformed bytes. The reference returned at step is used to access the ClassLoader. The defineClass method is the method that the ClassLoader calls in order to instantiate a runtime version of the Class within a Java Virtual Machine.

This mechanism modifies the operation of the ClassLoader by calling defineClass with the transformed bytes rather than with the original non transformed bytes that would otherwise be used.

It should be appreciated that defineClass can only be called once per class because subsequently the bytes are cached for retrieval. It is therefore important to use bundle listener to listen on resolve events and to eagerly load all classes that are to be woven.

It is then determined at step whether there is another class to weave and if so the process loops round to step and selects the next class to weave. If not the process ends and the listener waits for another bundle resolution event step .

As indicated above on occasion there will be multiple classes to weave. It is important that if these classes are within a hierarchy certain strict ordering is observed. In the standard Java class loading model there are two requirements 

It should be appreciated that although the present invention has been described within the context of OSGi it is not limited to such. Rather the invention is applicable to any environment where the code loading strategy is not readily available to the executing code for example in one of the other languages designed to run on the Java Virtual Machine. The invention should also not limited to Java.

While the term bytecode weaving may be seen as very Java specific it is not to be interpreted as such when used herein. The term bytecode should be taken to apply generically to any machine instructions generated by a developer or an automated tool. Weaving is the term used herein for modifying this code.

