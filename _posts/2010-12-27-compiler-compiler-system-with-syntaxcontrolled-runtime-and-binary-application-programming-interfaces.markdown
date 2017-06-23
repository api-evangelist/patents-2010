---

title: Compiler compiler system with syntax-controlled runtime and binary application programming interfaces
abstract: A compiler compiler system with a design paradigm different from traditional compiler compiler systems in many aspects. First, instead of parsing tree, compiler compiler runtime and binary are designed according to compiler compiler parsing model. Second, any semantics processing is totally separated from syntax processing. Third, the whole compilation process is defined as syntax processing and semantics processing followed by syntax processing performed under compiler compiler management supervision. Fourth, syntax processing has two phases: building compiler compiler runtime, and converting compiler compiler runtime into compiler compiler binary with available option to convert back compiler compiler binary to compiler compiler runtime. Fifth, compiler compiler runtime and binary syntax-controlled APIs are defined in terms of syntax. Sixth, there are formal methods de-compiling compiler compiler runtime and/or binary into original program text accordingly to syntax. Seventh, compiler compiler runtime and binary with their syntax-controlled APIs serve as a multiplatform for obfuscation, security, binary files processing, and program-to-program communication.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08464232&OS=08464232&RS=08464232
owner: 
number: 08464232
owner_city: 
owner_country: 
publication_date: 20101227
---
The present invention relates to information technology and more specifically to the generation of source code from formal descriptions that can be compiled and linked creating an executable program.

In applications performing compiler constructions those formal descriptions are defined in terms of context free grammars. Such tools take a definition of context free grammar usually in Backus Naur Form BNF and generate a source code of compiler components and that compiler is able to process source code according to the input grammar definition. Such tools are called compiler compilers or compiler generators. One of the earliest and still most common form of compiler compiler is a parser generator. In this case the compiler compiler takes a grammar definition and generates parser source code. Also a traditional compiler compiler generating parser source code from a grammar specification has another component that takes regular expressions and generates a tokenizer capable of processing specified tokens as a sequence of characters.

When a generated parser executes its actions during parsing a source program in accordance with a language grammar it builds some form of parsing tree. A developer who implements a compiler based on conventional compiler compiler technology is responsible for writing code in terms of a parsing tree and some attributes assigned to parsing tree nodes.

An ideal compiler compiler is supposed to take an input grammar specification and generate source code in automatic mode without any further manual procedures. Unfortunately this is far from what current information technology can offer in compiler compiler products available for developers.

According to one embodiment of the present invention a compiler compiler system includes compiler compiler executable program compiler compiler management compiler compiler runtime compiler compiler binary compiler compiler generator compiler compiler source grammar definition language and compiler compiler parsing model.

In another embodiment of the present invention parsing results processing is totally separated from any subsequent semantics processing parsing results are not represented in the form of any parsing tree and parsing results are represented in the form of compiler compiler runtime that can be formally converted into from compiler compiler binary.

In another embodiment of the present invention target language defined in compiler compiler source grammar definition language as a source file is compiled by compiler compiler executable program and a target parser and related source files are generated totally automatically providing to the target compiler a basic set of compile and de compile operations.

In another embodiment of the present invention the compiler compiler runtime and binary have a common compiler compiler parsing model that considers parsing results to be represented in the form of entities such as Context Name Symbol and Rule and their relationships. That model itself is another embodiment of the present invention i.e. an alternative view to a traditional parsing tree. The compiler compiler runtime implements the model in efficient form required by parser performing create update search and other low level operations in terms of Context Name Symbol and Rule classes and their relationships. The compiler compiler binary implements the model in efficient form providing read only operations having all data allocated in a vector of Tag instances but still is logically equivalent to the compiler compiler runtime.

In another embodiment of the present invention a compiler compiler binary is a multiplatform data exchange protocol that allows interaction between programs running on different platforms running on different operating systems and built using different programming languages such as C C C Java Objective C Ruby Pyton Perl and others.

In another embodiment of the present invention a compiler compiler system can be used for binary files processing. In this case a corresponding binary file format has to be designed in the form of compiler compiler source grammar definition language specification. After that a custom convertor from binary file format into compiler compiler runtime format is implemented. Having a compiler compiler runtime built for a binary file with a given format allows all other compiler compiler phases to work automatically without any extra code development.

In another embodiment of the present invention an input compiler compiler binary can be formally transformed using a transformation algorithm into from an output compiler compiler binary providing generic operations for applications such as obfuscation security access control and content management. The transformation algorithm may be any suitable transformation algorithm typically used for obfuscation access control content management or any other suitable algorithm as appropriate to the application. Consider a credit card account number represented in compiler compiler source grammar definition language as a sequence of digits each of them represented as an integerToken. Then at the compiler compiler binary level the account number will be represented as a sequence of integerToken tokens. A simple obfuscation algorithm can transform those integerToken token values into different values in the output compiler compiler binary before transmitting output compiler compiler binary over the wire protecting the account number with subsequent de obfuscation on the receiving side. Those algorithms can be changed dynamically also. For security control compiler compiler binary can be transformed by adding user information with subsequent validation. Consider an audio or video file to be converted into compiler compiler binary. After that conversion any custom transformations are possible including security control and obfuscation for content protection. Also any kind of advertising incorporated into compiler compiler binary is possible with programmed options enabling disabling ads.

In another embodiment of the present invention compiler compiler management generator runtime and binary source code are compiled into a compiler compiler foundation library that is used in compiler compiler executable program and any other target compiler built by means of a compiler compiler system.

In another embodiment of the present invention for any compiler compiler source grammar language description the compiler compiler executable program generates code that is compiled into a generated library and a target compiler executable program is compiled and built with the compiler compiler foundation library and generated library. Built this way the target compiler executable program has default compile and de compile operations ready. All semantics processing can be done as independent subsequent operations implemented using a compiler compiler binary application programming interface API .

In another embodiment of the present invention the compiler compiler source grammar definition language is defined using the same source grammar definition language that allows a bootstrapping method to be used for implementing compiler compiler executable program using itself. In other words the compiler compiler generated code for a given meta grammar description is compiled into a generated library and a newly created compiler compiler executable program is compiled and built with compiler compiler foundation library and generated library. Built this way the newly created compiler executable program has compile and de compile operations ready. All semantics processing in this case is done as a code generation for parser and related generated source files implemented using compiler compiler binary API. If the abbreviation CCSGDL stands for compiler compiler source grammar definition language then meta grammar is CCSGDL for CCSGDL.

The input file for parser generator contains a grammar definition in the form of a few sections such as implementation language declarations compiler compiler declarations compiler compiler grammar rules specification and additional implementation language code. For YACC and GNU BISON the implementation language is C language.

The compiler compiler grammar rules specification is a sequence of individual grammar rules. Each grammar rule is defined as a non terminal on the left side and a potentially empty sequence of terminals and non terminals on the right side followed by actions. The grammar rule actions are specified as implementation language code with additional features the compiler compiler can understand and convert into implementation language code during generation. Those additional features are related to attributes attached to parsing tree nodes. Usually those attributes have a prefix and the compiler compiler acts like a specialized preprocessor that for each rule finds all occurrences of and generates corresponding implementation language code based on compiler compiler executing environment rules for processing parsing results.

For each grammar rule specified actions are executed every time the parser recognizes that the rule is supposed to be invoked during parsing.

The input file for the tokenizer generator mainly consists of language tokens definitions in the form of token name and token regular expression specifying a valid set of characters comprising the token.

To summarize the prior art compiler compiler system model forces a compiler developer to define compilation tasks in the form of individual grammar rule actions for the isolated parsing tree context identified with the given rule invocation. As a result when parsing is done a parsing tree is built along with a custom environment implemented by the compiler developer. Subsequent compilation phases followed by parsing are implemented in terms of that parsing tree and custom environment.

Compiler compiler executable program for meta grammar performs phase .generating compiler compiler binary for compiler compiler runtime . The phase .is implemented as a formal procedure that converts compiler compiler runtime into compiler compiler binary . Compiler compiler executable program has an option to de compile meta grammar from generated compiler compiler binary into a text file not shown containing meta grammar executing phase .. This newly de compiled meta grammar as a text is identical to meta grammar except for some differences related to supported indentation rules. Compiler compiler executable program has an option to re create a compiler compiler runtime that is identical to original compiler compiler runtime having compiler compiler binary executing phase .

Compiler compiler executable program performs phase . creating a compiler compiler generated code corresponding to meta grammar . The compiler compiler source grammar definition language consists of a grammar name section followed by a sequence of rules where the first rule is also a grammar axiom. As used herein the grammar name section consists of a single identifier that defines a name of grammar. As an example when C compiler compiler executable program takes the following meta grammar source file 

Note that the meta prefix in file names corresponds to the grammar name the first section identifier in source grammar definition language. Note also that

are used as a special macro substitution actions defined in form of integer number followed by sequence of string literals enclosed in and . Further elements and rules are explained in the following paragraphs.

The compiler compiler source grammar definition language elements such as and are grammar terminals defined as a string literal with enclosed single quotes.

is BNF extension called iteration meaning that enclosed by and non terminal is actually may occur zero or any other number of times.

If phase . is performed for newly compiler compiler generated code corresponding to meta grammar then a new default version of compiler compiler executable program is created with default metaGenerator.cc that has empty implementation. When that default version of compiler compiler executable program is running it has all phase . phase . phase . phase . and phase .available to be executed.

The phase . is actually implemented in the Generator.cc file. In case of the C compiler compiler system mentioned above seven files are created automatically without any manual intervention from the developer not only for meta grammar but also for any other grammar defined in the compiler compiler source grammar definition language. In other words compiler compiler semantics processing is performed by phase . and it is done by the Generator.cc file. That code is actually implemented on top of the generated initial default version.

Compiler compiler executable program performs phase .generating compiler compiler binary for target language grammar compiler compiler runtime . The phase .is implemented as a formal procedure that converts compiler compiler runtime into compiler compiler binary . Compiler compiler executable program has an option to de compile target language grammar from generated compiler compiler binary into a text file containing compiler compiler source grammar definition language source text defining target language grammar executing phase .. This newly de compiled target language grammar as a text is identical to target language grammar except for some differences related to supported indentation rules. Compiler compiler executable program has an option to create compiler compiler runtime having compiler compiler binary executing phase .

Compiler compiler executable program performs phase . creating compiler compiler generated code corresponding to target language grammar directly from . When C compiler compiler executable program takes target language grammar source file the following C source files are generated 

Note that the prefix in file names corresponds to the grammar name the first section identifier in source grammar definition language.

If phase . is performed for newly compiler compiler generated code corresponding to target language grammar then a new default version of target language compiler executable program is created with a default Generator.cc that has empty implementation. When that default version of target language compiler executable program is running it has all phase . phase . phase . phase . and phase .available to be executed. The phase . is actually implemented in Generator.cc file corresponding to target language grammar . In the case of the C compiler compiler system mentioned above seven files are created automatically without any manual intervention from the developer not only for meta grammar but also for any other grammar defined in the compiler compiler source grammar definition language. In other words compiler compiler semantics processing is performed by phase . and it is done by the Generator.cc file corresponding to the target language compiler. That code is implemented on top of the generated initial default version with no manual actions. So phase . performs the same steps as phase . but phase . is related to semantics processing of the target language compiler.

Target language compiler executable program performs phase .generating compiler compiler binary for compiler compiler runtime . Phase .is implemented as a formal procedure that converts compiler compiler runtime into compiler compiler binary . Target language compiler executable program has an option to de compile source text from generated compiler compiler binary into a source text file in accordance with target language grammar executing phase .. This newly de compiled target language source text is identical to original target language source text except for some differences related to supported indentation rules. The target language compiler executable program has an option to create compiler compiler runtime having compiler compiler binary executing phase .

The target language compiler executable program performs phase . a target compiler semantics processing based on compiler compiler binary .

To summarize and compiler compiler management generator runtime and binary source code are compiled into a compiler compiler foundation library that is used when compiler compiler executable program compiles compiler compiler source grammar definitions and when target compiler executable program compiles target language programs.

Along with Tag UnsignedTag Real and TypeInstance are defined the same way. For 32 bit computer architecture all those types occupy a four byte word for 64 bit computer architecture all those types occupy an eight byte word. TypeInstance instance in many cases is represented as a Tag value with subsequent fields packing unpacking operations.

The Parser class instantiates some simple data members such as file name as a string class instance as well as Boolean flags such as debugging flag XML token indicator flag etc. . . . shown in .

The Parser class shown on also instantiates other important members such as runtime  of type SyntaxControlledRuntime a binary  of type SyntaxControlledBinary a tokenizer of type Tokenizer  and a generator  of type Generator.

As described in the following paragraphs with reference to the compiler compiler runtime syntax controlled API including various inner classes is designed to perform the following set of operations to be invoked from any parser generated by compiler compiler system 

Create new Rule instance for the current Context instance having SymbolID returning Tag instance actually mapped to TypeInstance class instance with packed symbolID and ruleID .

Return Rule instance for the current Context instance having Tag instance actually mapped to TypeInstance class instance with packed symbolID and ruleID .

Modify Rule instance dynamic part for the current Context instance having Rule instance reference and vector reference representing dynamic part.

Modify Rule instance fixed part for the current Context instance having Rule instance reference and vector reference representing fixed part.

Create identifier representation having string representing identifier and returning identifier index.

If a compiler builds a map from a string representing object name to object instance then it would be easy and efficient to manipulate those objects by finding them by name. However the original order of z a b w would disappear since in the map they are ordered differently. MapVectorContainer is designed to provide both effective operations by name and preserving original sequence in the way objects were originally defined having direct access by name object key and by index object sequential number .

On MapVectorContainer template class takes two formal arguments representing object type and representing object key type. MapVectorContainer defines three inner types such as MapVectorContainer Map MapVectorContainer Vector and MapVectorContainer Data. The MapVectorContainer Map type is defined as std map. The MapVectorContainer Vector Map type is defined as std vector. MapVectorContainer Data type is defined as std vector. MapVectorContainer template class instantiates name2index instance of type MapVectorContainer Map index2name instance of type MapVectorContainer Vector and index2data instance of type MapVectorContainer Data.

Logically each compiler compiler runtime context maintains its own collection of symbols ordered by symbolID with direct access by symbolID.

Logically each compiler compiler runtime symbol maintains its own collection of rules representing each rule invocation during parsing for a given symbol.

Actually compiler compiler runtime logical view and compiler compiler binary logical view are the same since compiler compiler runtime and compiler compiler binary are interchangeable. However compiler compiler runtime is designed to be an effective environment for processing parsing results during parsing itself and compiler compiler binary is designed to be an effective environment for processing final parsing results in read only mode serving as a multiplatform interchange format.

In other words shows one form of compiler compiler parsing model with entities such as Context Name Symbol and Rule with their relationships.

As described in the following paragraphs with reference to the compiler compiler binary syntax controlled API including various inner classes is designed to perform the following set of operations to be invoked from any application responsible for any semantics processing based on compiler compiler system 

Get pointer to SyntaxControlledBinary Context BinaryRule having SyntaxControlledBinary Context BinarySymbol instance pointer and rule instance number given for that symbol.

Populate SyntaxControlledBinary Context BinaryRuleContent by its reference having SyntaxControlledBinary Context BinarySymbol instance pointer and SyntaxControlledBinary Context BinaryRule instance pointer.

Get rule fixed part as a pointer to Tag having SyntaxControlledBinary Context BinaryRule instance pointer.

Get rule fixed part as a reference to TypeInstance having SyntaxControlledBinary Context BinaryRule instance pointer and rule instance number.

Get rule dynamic part as a pointer to Tag having SyntaxControlledBinary Context BinaryRule instance pointer.

Get rule dynamic part as a reference to TypeInstance having SyntaxControlledBinary Context BinaryRule instance pointer and rule instance number.

SyntaxControlledBinary shown in can be converted into a single binary object specified by the following Backus Naur Form BNF 

 13.7.1.2 BinaryContextRuleElementDynamic integerToken where memory data member of SyntaxControlledBinary BinaryContext class is represented by rule 13 SyntaxControlledBinaryContext.

Note that this BNF is extended by special extensions such as iteration when some non terminal is enclosed with and meaning that that non terminal can occur zero or unlimited number of times alternative when some non terminals are separated by meaning that one of them can occur integerToken is used to represent 4 bytes integer or 8 bytes integer stringToken is used to represent string literal properly aligned. So BinaryContextRuleElements BinaryContextRuleElement is equivalent to BinaryContextRuleElements BinaryContextRuleElement BinaryContextRuleElements BinaryContextRuleElements So BinaryContextRuleElement 

The LineReader class is an abstract base class. The FileLineReader and StringLineReader classes are derived from LineReader. The FileLineReader class provides implementation for reading source text of compiled program from a file it also maintains the corresponding listing as a file. The StringLineReader class provides implementation for reading source text of compiled program from a std string as a sequence of lines separated by a given delimiter it also maintains the corresponding listing. Any other line reader classes can be implemented as derived from LineReader abstract base class.

 start having const reference to string to be processed as a sequence of lines and boolean flag if listing is required.

The Language class is an abstract base class. The LanguageMeta and LanguageXML classes are derived from the Language class. The LanguageMeta class implements tokens set and Language interface for compiler compiler source grammar definition language. The LanguageXML class implements tokens set and Language interface for XML type of languages.

The Language abstract class comprises the following pure virtual functions or their equivalents from the set of functions defining the ILanguage interface 

 getNumeric populating Tokenizer currentDoubleValue or currentIntegerValue depending on token value and Tokenizer currentKeyWord .

In addition the Language class comprises generic functions common to all languages as derived classes from the Language class those generic functions are 

 populateTerminals populating SymbolID for each token defined in terminalTokens  terminalKeyWords  and nonTerminals  .

 isDefinedToken returning true or false depending on check of all tokens defined in terminalTokens  if that token matches the sequence of characters starting from Tokenizer currentCharacter .

 isKeyWord returning true or false depending on check if a given formal parameter is defined in corresponding name to index container of terminalKeyWords  .

 setNextToken setting Tokenizer currentKeyWord by performing loop for each token size k starting from maximum size while k greater than zero reducing k by one

checking if k equals to token t size and token t is Token predicate is true then executing token t flushToken function see description of the Token class below setting Tokenizer currentKeyWord as token t SymbolID .

 getToken having a formal argument as an input with token SymbolID returning corresponding reference to Token class instance.

 skipToken having a first formal argument as an input with token SymbolID and a second formal argument as an output with token reference to Tag actually mapped to TypeInstance class instance with token SymbolID and token RuleID performing call to getToken with the first formal argument as an input with token SymbolID getting reference t to Token class instance performing call to method skipToken with the first formal argument as an input with token SymbolID and the second formal argument as an output with token reference to Tag performing call to getNextToken .

 getTerminalString setting Tokenizer currentTerminalStringValue and related Tokenizer data members processing sequence of input characters enclosed with single quotes representing language defined terminal as a sequence of characters enclosed with single quotes.

The Token class is an abstract base class that is derived from abstract base class IToken that consists of a set of pure virtual functions defining its interface. The Token class has a reference tokenizer  to Tokenizer class instance. The Token class has a data member symbol  that is actually corresponds to SymbolID of Symbol related to the given Token. The Token class has data members token  and name  of std string type.

The Token class comprises pure virtual functions or their equivalents from the set of pure virtual functions defining the IToken interface such as 

 isToken predicate returning true or false depending on if Tokenizer sequence of characters starting from Tokenizer currentCharacter matches given token token  data member.

 flushToken checking if isToken predicate returns true then advancing Tokenizer currentCharacter to the next one beyond the given token sequence of characters and executing Tokenizer flushBlanks function skipping white space characters such as blank tabulation etc.

 generateFromRuntime having file name as a formal argument that is used to generate output based on runtime content.

 generateFromBinary having file name as a formal argument that is used to generate output based on binary content.

The Generator class implements IGenerator interface i.e. implements the foregoing functions or their equivalents. The Generator class has a reference parser  to the Parser instance. The Generator class has a data member tokenizerSet  of enumerated type LanguageTokenizerSet. The Generator class instantiates runtime  as GeneratorRuntime and binary  as GeneratorBinary . Pointer to GeneratorRuntime GeneratorRuntime and Pointer to GeneratorBinary GeneratorBinary will be replaced by std shared ptr and

std shared ptr when std shared ptr will be widely available as C standard library class. The GeneratorBinary class is a base class derived from IBinaryGenerator abstract base class that consists of a set of pure virtual functions defining its interface. The GeneratorRuntime class is a base class derived from IRuntimeGenerator abstract base class that consists of a set of pure virtual functions defining its interface.

The IBinaryGenerator abstract base class consists of the following pure virtual functions or their equivalents 

The IRuntimeGenerator abstract base class consists of the following pure virtual functions or their equivalents 

The IRuntimeGeneratorStyle abstract base class consists of the following pure virtual functions or their equivalents 

The IBinaryGeneratorStyle abstract base class consists of the following pure virtual functions or their equivalents 

While the invention has been described with respect to certain preferred embodiments as will be appreciated by those skilled in the art it is to be understood that the invention is capable of numerous changes modifications and rearrangements and such changes modifications and rearrangements are intended to be covered by the following claims.

