---

title: Method and device for countering fault attacks
abstract: The public exponent e of an RSA key is embedded in a RSA key object that lacks this exponent. During exponentiation, the public exponent e may be extracted and used to verify that the result of the exponentiation is correct. The result is output only if this is the case. The invention counters fault-attacks. Also provided are an apparatus and a computer program product.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08744074&OS=08744074&RS=08744074
owner: Thomson Licensing
number: 08744074
owner_city: Issy les Moulineaux
owner_country: FR
publication_date: 20100218
---
This application claims the benefit under 35 U.S.C. 119 of European Patent Application 09305162.1 filed Feb. 19 2009.

The present invention relates generally to cryptography and in particular to a fault attack countermeasure for RSA.

This section is intended to introduce the reader to various aspects of art which may be related to various aspects of the present invention that are described and or claimed below. This discussion is believed to be helpful in providing the reader with background information to facilitate a better understanding of the various aspects of the present invention. Accordingly it should be understood that these statements are to be read in this light and not as admissions of prior art.

A fault attack disturbs the expected behaviour of a security device and makes it work abnormally so as to infer sensitive data from the faulty output. Such attacks were introduced by Boneh et al. in On the Importance of Checking Cryptographic Protocols for Faults D. Boneh R. A. DeMillo and R. J. Lipton In W. Fumy editor Advances in Cryptology EUROCRYPT 97 volume 1233 of Lecture Notes in Computer Science pages 37 51 Springer Verlag 1997.

Fault attacks can be very powerful. For example a faulty RSA signature with a single random fault and evaluated using Chinese remaindering CRT can allow an attacker to recover the entire secret key from the faulty signature. It is thus clear that countermeasures must be taken.

RSA is based on the fact that it is difficult to factorize products of large primes. Let N pq be the product of two large primes. We let e and d denote a pair of matching public and private exponents satisfying ed 1 mod N with gcd e N 1 and being Carmichael s function. As N pq we have N lcm p 1 q 1 . Given x

Naturally several such countermeasures have been proposed. The initial countermeasure by Shamir is disclosed in U.S. Pat. No. 5 991 415 initially presented at the Rump Session of EUROCRYPT 97. Somewhat simplified this method introduces a random value j and calculates using mod j p instead of mod p and verifies that the expected value is arrived at as a given example if j is 32 bits long the chance of the two values matching after a fault is 2 1 4 294 967 296 so the risk is very slight. More specifically the values of x ymod j p and x ymod j are first calculated. It is verified that x x mod j and if so the calculation is assumed to be error free. The result of the exponentiation modulo p is then given by x x mod p. This same is done modulo q. The correctness of the countermeasure relies on the observation that x mod p x mod j p mod p for any positive integer j.

Another method mentioned by Kaliski and Robshaw in ftp ftp.rsasecurity.com pub pdfs bulletn5.pdf consists in performing the exponentiation in a usual manner to obtain x ymod N but before issuing x checking it is correct by checking that xis equal to y modulo N.

Of these it has been shown that the methods of Bl mer et al. and Ciet et al. do not offer full tamper resistance. Furthermore none of these methods guarantee a 100 detection of faults and they all impact performance running time and memory requirements and in some cases the personalization process.

It will therefore be appreciated that there is a need for a countermeasure against fault attacks on RSA that detects all faults. This invention provides such a solution.

In a first aspect the invention is directed to a method for calculating an exponentiation. The method is resistant against fault attacks. A RSA private key object being associated with a matching public exponent is obtained. A result of an exponentiation using the RSA private key object is obtained. It is verified using the matching public exponent that the result of the exponentiation is correct. In standard mode the RSA private key object comprises the RSA modulus N and the matching public exponent e is obtained from the RSA modulus N in CRT mode the RSA private key object comprises the factors of the RSA modulus N and the matching public exponent e is obtained from the at least one of the factors of the RSA modulus N.

In a first preferred embodiment the matching public exponent e is comprised in the leading bits of the binary representation of RSA modulus N.

In a second preferred embodiment in CRT mode the matching public exponent e is comprised in the leading bits of the binary representation of RSA modulus N the RSA modulus N being obtained by multiplication of its factors.

In a second aspect the invention is directed to a device for calculating an exponentiation the device being resistant against fault attacks. The device comprises means for obtaining a RSA private key object the RSA private key object being associated with a matching public exponent means for obtaining a result of an exponentiation using the RSA private key object and means for verifying using the matching public exponent that the result of the exponentiation is correct. The device further comprises means for obtaining the matching public exponent e in standard mode from a RSA modulus N comprised in the RSA private key object and in CRT mode from the at least one of factors of the RSA modulus N the factors of the RSA modulus N being comprised in the RSA private key object.

In a first preferred embodiment the means for obtaining a RSA private key object the means for obtaining a result of an exponentiation using the RSA private key object the means for verifying using the matching public exponent that the result of the exponentiation is correct and the means for obtaining the matching public exponent e are implemented in at least one processor.

In a third aspect the invention is directed to a computer program product having stored thereon instructions that when executed by a processor performs the method of the first aspect.

There is a difference between key and key object in RSA. A key is an entity such as a public key N e or a private key N d respectively p q d d i in CRT mode that may be used for cryptographic calculations while a key object may be said to be a representation of a key.

In existing Application Programming Interfaces APIs such as for example that provided by JavaCards a RSA private key object is initialized from p q d d i in CRT mode and from N d in standard mode.

It is worth noting that the corresponding public exponent e is not available. Because of this many proposed countermeasures already mentioned herein check whether or not the computation y xmod N is error free. However if the value of e were available it would be easy to check the correctness of y by verifying if y x mod N in standard mode or if y x mod p q in CRT mode. This is especially true as the value of e is almost always chosen small typically 3 or 2 1.

In order to allow this in the preferred embodiment the value of e is made available by embedding its value in the RSA private key object.

A main inventive idea is thus to embed a representation of the public RSA exponent e in the RSA key. By representation is meant a way of unambiguously denoting value. For example commonly used public RSA exponents are 3 and 2 1. Examples of representations of these values are their binary values their length in bytes followed by their values or indeed 1 for 3 and 2 for 2 1 if this has been agreed upon beforehand.

As mentioned such a key object is obtained from p q d d i in CRT mode and from N d in standard mode. When computing y xmod N it is checked whether the public exponent e is embedded in the representation of the RSA key. If this is the case the public exponent e is recovered. Then it is verified if y x mod N in standard mode or if y x mod p q in CRT mode. Only upon successful verification is y returned.

The skilled person will appreciate that a RSA modulus appears as a random string of bits. It is thus preferable to allow an application to distinguish between regular RSA moduli i.e. moduli that do not embed the public exponent e and moduli according to the present invention. To do this it is preferable to insert an indicator S of for instance 64 bits such as for example 5A5A5A5A5A5A5A5A before or indeed after public exponent e which preferably is inserted in L V length value format where L denotes the length e.g. in words or bits of the value V of the public exponent e.

Given the public exponent e and a length l a l bit RSA modulus N pq may be generated with a predetermined portion comprising S L and V. Such a modulus may be generated by any suitable method such as the ones described in M. Joye RSA Moduli With a Predetermined Portion Techniques and Applications. In Information Security Practice and Experience ISPEC 2008 vol. 4991 of Lecture Notes in Computer Science pages 116 130 Springer 2008 and A. Lenstra. Generating RSA Moduli With a Predetermined Portion. In Advances in Cryptology ASIACRYPT 98 vol. 1514 of Lecture Notes in Computer Science pages 1 10 Springer 1998.

From such a modulus N it is easy to recover the value of the public exponent e. Correspondingly in CRT mode the value of the public exponent e is recovered from the product pq where p and q denote the private factors of N.

In other words in order to calculate an exponentiation the RSA private key object is obtained either by e.g. extracting the private key object from one or more stored data fields by calculation from values in one or more stored data fields or by a combination thereof. The RSA private key object is associated with a matching public exponent which is to say that there exists a corresponding public exponent that for example can be used for verification of exponentiations and signatures. The result of an exponentiation using the RSA private key object e.g. y xmod N is obtained for example by calculation or by receiving it from a further device. It is then verified using the matching public exponent that the result of the exponentiation is correct for example by checking that y x mod N . Depending on the implementation the matching public exponent e is obtained in different ways. In standard mode it is obtained from the RSA modulus N and in CRT mode it is obtained from the at least one of the factors of the RSA modulus N. Obtained means extracting the public exponent e which is embedded in a further entity. For example in standard mode the public exponent e may be formed a series of binary digits in the binary representation of N and in the CRT mode the public exponent e may be formed a series of binary digits in the binary representation of p or q or even in the product of p and q. In the latter case the product has to be calculated before the e can be extracted.

It will be appreciated that the present invention enables detection of all faults or errors. It will also be appreciated that the present invention is fully compatible with existing implementations so there is no need to change the APIs. Finally a further advantage is that the method of the invention is very efficient typically it only requires a few additional modular multiplications so the verification step for a typical 2048 bit application only represents about 0.09 to 0.5 of the overall calculations.

Each feature disclosed in the description and where appropriate the claims and drawings may be provided independently or in any appropriate combination.

Features described as being implemented in hardware may also be implemented in software and vice versa. Connections may where applicable be implemented as wireless connections or wired not necessarily direct or dedicated connections.

Reference signs appearing in the claims are by way of illustration only and shall have no limiting effect on the scope of the claims.

