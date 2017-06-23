---

title: System and method for maximizing edit distances between particles
abstract: Embodiments of the invention disclose a system and a method for transforming a set of particles in an output set of particles representing a set of words suitable for use in an information retrieval system. The method generates, for each particle in the set of particles, combinations of parts of a particle, and replaces the particle in the set of particles with the parts of a combination maximizing a total minimum edit distance (MED) of the set of particles. For example, the method determines a MED of each particle in the set of particles, determines the total MED of the set of particles as summations of the MED of each particle, and then determines the combination maximizing the total MED of the set of particles.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08229965&OS=08229965&RS=08229965
owner: Mitsubishi Electric Research Laboratories, Inc.
number: 08229965
owner_city: Cambridge
owner_country: US
publication_date: 20100331
---
This application is a continuation in part of U.S. patent application Ser. No. 12 495 540 now U.S. Pat. No. 8 055 693 Method for Retrieving Items Represented by Particles from an Information Database filed by Ezzat et al. on Jun. 30 2009.

This invention relates generally to information retrieval and in particular to transforming of a set of particle using maximization of edit distances between particles.

Information retrieval IR systems typically include a large list of items such as geographic points of interest POI or music album titles. The list is accessed by an index. Input to the index is a query supplied by a user. In response to the query the IR system generates a result list that best matched the query. The result list can be rank ordered according various factors. The result list index query and result list are typically represented by words. The input list query and result list be textual or spoken.

Spoken queries are used in environments where a user cannot use a keyboard e.g. while driving or the user interface includes a microphone. In those environments an automatic speech recognizer ASR is used to convert speech to words.

The ASR uses two basic data structures a pronunciation dictionary of words and a language model of the words. Usually the IR system represents the words phonetically as phonemes e.g. RESTAURANT is represented as R EH S T R AA N T. Phonemes refer to the basic units of sound in a particular language. The phonemes can include stress marks syllable boundaries and other notation indicative of how the words are pronounced.

The language model describes the probabilities of word orderings and is used by the ASR to constrain the search for the correct word hypotheses. The language model can be an n gram. If the n grams are bigrams then the bigram lists the probabilities such as P BELL TACO which is the probability that the word BELL follows the word TACO. The language model can also be a finite state grammar where the states in the grammar represent the words that can appear at each state and the transitions between states represent the probability of going from one state to another state.

First important words for the IR are typically infrequent identifier words. For example in an item POI MJ S RESTAURANT the important identifier word is MJ S. Frequently these identifier words are proper nouns from other languages. For example the word AASHIANI in the item AASHIANI RESTAURANT is from the Hindi language. Another way these identifier words emerge is through combination as with GREENHOUSE. Modifying the roots of words also increases the size of the vocabulary. In general the number of infrequent but important identifier words is very large.

In addition important identifier words are often mispronounced or poorly represented by the language model. Accurate statistics for the n grams also are generally unavailable. Hence the probability of recognizing important infrequent words is low and the word sequences are often incorrect. This leads to poor recall performance by the IR system.

Second the computational load for word based IR systems increases with the size of the list and index and the performance of system becomes unacceptable for real time retrieval.

Embodiments of the invention provide a method for retrieving items in an information retrieval IR database represented by particles. The number of unique particles is much smaller than the number of unique words e.g. smaller by at least an order of magnitude. This improves the performance of an automatic speech recognition ASR system leading to a decrease in recognition time by as much as 50 . Surprisingly even though the number of particles is decreased dramatically when compared with the number of words and the throughput increases likewise the performance of IR system measured by the recall rate is improved by as much as 2 .

The embodiments of the invention are based on the realization that for the operations of the information retrieval IR systems it is advantageous to represent a set of words with the particles that are as different from each other as possible. For example having particles that are as different from each other as possible allows for accurate recognition during ASR. Moreover the embodiments are based on the further realization that the difference between the particles can be measured using edit distance.

One embodiment of the invention discloses a method for transforming a set of particles formed by at least part of a set of items in an output set of particles wherein the set of items represents a set of words suitable for use in an information retrieval system. The method generates for each particle in the set of particles combinations of parts of a particle and replaces the particle in the set of particles with the parts of a combination maximizing a total minimum edit distance MED of the set of particles. For example the method determines a MED of each particle in the set of particles determines the total MED of the set of particles as summations of the MED of each particle and then determines the combination maximizing the total MED of the set of particles.

Another embodiment discloses a method for generating an output set of particles representing a set of words comprising the steps of determining a set of particles from the set of words generating combinations of parts of a particle in the set of particles replacing the particle in the set of particles with the parts of a combination maximizing a total minimum edit distance MED of the set of particles and repeating the generating and the replacing for each particle in the set of particles to generate the output set of particles wherein the steps of the method are performed by a processor.

Yet another embodiment discloses a system for transforming a set of particles in an output set of particles representing a set of words comprising a transformation module configured to determine for each particle in the set of particle a combination of parts of the particle maximizing a total minimum edit distance MED of the set of particles and a processor configured to replace the particle in the set of particles with the parts of the combination.

One variation of this embodiment includes means for determining a MED of each particle in the set of particles means for determining the total MED of the set of particles and means for determining the combination maximizing the total MED of the set of particles.

As shown in embodiments of our invention provide a method for retrieving items from a database in an information retrieval IR system . The steps of the method operate in a processor as known in the art. The processor includes memory and I O interfaces.

The IR system includes a list of items represented by words. From the word based list we generate a list of items represented by particles. The correspondence between the items in the word based list and the items in the particle based list can be one to one or one to many when alternative pronunciations of the words are possible.

Particles are well known in the field of speech recognition. As defined herein a particle represents a concatenated phoneme sequence. A string of particles represents the phoneme sequence for a word see Whittaker et al. Particle based language modelling International Conference on Speech and Language Processing ICSLP 2000.

Up to now particles have only been used to recognize words in an automatic speech recognizer ASR system. In contrast the invention uses particles to perform information retrieval IR .

We apply an indexer to the list to produce a particle based index . To retrieve items a particle based query is acquired from a user . The query can be derived from words in text or speech using the ASR.

The query is used to look up the index constructed from the particle based list . The output in response to the query is a result list of items from the word based list that correspond to the best matching items in the particle based list .

To generate the particle based list in a preprocessing step we maintain a set of unique words in the list . We convert the word based set to a set of unique particles . After we obtain the particle based set we can translate the words for the items in the list to the corresponding particle based items to generate the particle based list .

If an item in the word based list has multiple pronunciations then a Cartesian product of all possible partitioning into particles for all the words is formed and enumerated in the particle based list. For example if AASHIANI can be partitioned into particles as AA SH IY AA N IY or as AA SH Y AE N IH and RESTAURANT into particles as R E S T R AA N T or as R E S T ER R AA N T then all possible partitionings are enumerated in the particle based index 

Our language model includes particles e.g. an n gram language model that includes statistics on particle n grams.

Embodiments of the invention are based on the realization that for the operations of the information retrieval IR systems it is advantageous to represent a set of words with the particles that are as different from each other as possible. For example having particles that are as different from each other as possible allows for accurate recognition during ASR. Moreover the embodiments are based on the further realization that the difference between the particles can be measured using edit distance.

Accordingly the embodiments transform a set of items in an output set of particles. In various embodiments of the invention the set of items represents a set of words suitable for use in the IR system. For example one embodiment determines for each word in the set of words all possible partitionings of the word into particles and forms the set of items from unique particles derived from the set of words. In other embodiments items in the set of items are selected from at least one of the set of words a set of phonetic strings derived from the set of words a set of particles derived from the set of words and a combination thereof.

A transformation module generates combinations of parts of a particle in the set of particles. For example in one embodiment the combinations include only two parts i.e. a prefix and a suffix of the particle. Additionally the combinations are all possible combinations of the particle. In alternative embodiment the combinations include more than two parts.

The particle is replaced in the set of particles with the parts of a combination maximizing a total minimum edit distance MED of the set of particles. The transformation is repeated for all particles in the set of particles thus transforming the set of particles in the output set of particles.

The replacing is repeated for all combinations of the particle. Specifically the parts of the combination are removed from the set of particles and replaced with the parts of another combination of the particles and the MED and the total MED are determined using the parts of the another combination. Finally the parts of the combination corresponding to a maximum value of the total MED are added into the set of particles.

One embodiment preserves only unique particles in the set of particles. For example of a part of the combination identical to a particle in the set of particles this part is not added into the set.

During the transformation the set of particles and accordingly the output set of particles are indexed according to the set of words. For example one embodiment creates an index map of indexes between the set of items and the set of words. The index map tracks the partitioning of the words into the particles. During the transformation the index map becomes a tree map indexing the parts of the particles replacing the particles.

Although the invention has been described by way of examples of preferred embodiments it is to be understood that various other adaptations and modifications may be made within the spirit and scope of the invention. Therefore it is the object of the appended claims to cover all such variations and modifications as come within the true spirit and scope of the invention.

