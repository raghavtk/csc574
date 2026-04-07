# Computer Network Security: CSC574

# Lecture 1: 13/01 

# Notes

## What do you hope to learn in this course?

1. Learn the fundamentals of security, layer by layer
2. Learn good practices and writing secure code
3. Different kinds of attacks and how the design should have been better to ensure those didn't happen
4. How do you design systems that are secure maybe use of AI in mobile network security stuff?
5. How do mobile networks work i guess?
6. Systems attacks and defences

- Reading is 10% of the grade
- Project

## What does it mean for a system to be secure?

- The data that flows through the system cannot be stolen at any point.

- The system should be able to handle load(large number of requests)

- The data in a particular part of the system does not provide infor about the entire system.

## Important definitons:

- Security: If it can maintain well-specified properties despite the actions of well-specified adversaries. - IMPORTANT

- The set of properties we assume to be correct is called the trust model

- The set of adversaries and their capabilities we assume to be correct is called the threat model

- Trust model + threat model = security model


# Lecture 2: 15/01 
# Notes: 


## What we'll be tested on:
1. Definitions of security
2. Define adversary, trust and security model
3. Create and critique security models for familiar systems
4. Go through the slides and figure out questions.


# Fundamentals: Today is terminology day

## CIA Triad:

1. Confidentiality: Protect against unauthorized disclosure.
2. Integrity: Protect against unauthorizedmodification.
Eg. Social media or something, where you want the identity to be verified, but data is out
3. Availability: Protect and maintain authorized access: Shouldn't be able to just turn it off

- When integrity over confidentiality? social media, open-source code, your signature on a public form, etc. 


### Which is the most important? depends on your security model, i.e., the context.

#### Guesses from the class:  
Privacy  
P - Authorization  
Attack surface - hmm  
Cost - hmm  

Extra in the list:  
resiliency  
non-repudiation  
Resiliency - Availability
I - Auditability  
Accounting  
Non-repudiation  

Anonymity is completely different from privacy

## Assets: What we protect:

1. Hardware resources,
2. Network access, 
3. Operating systems, 
4. Software, 
5. Data. The first five are common.
6. Users can be considered as assets that deserve protection on their own.
7. User Time: if you're a bank and you're being attacked and you keep the system up and a click takes 5 mins to process. User Time is wasted, literally.
8. Reputation. (some password manager are better than ours, once reputation gone, value gone)
9. Money managed by system

## Participants: 
- Computers, agents, people, enterprises. 
- Sometimes referred to as: principals, servers, clients, users, entities, hosts, routers
- Expected systems, entities.
- Security is defined and analyzed w.r.t these entities.
- Every party may have unique view.

#### A trusted third party = trusted by all parties for some set of actions, often used as introducer or arbiter.


## Adversaries:
Anyone attempting to violate your trust model: circumvent the security infrastructure.

Fundamental difference between security and safety/reliability/quality is because of the notion of an adversary.

Adversaries are aware, motivated and adaptive.

## Characterizing adversaries:

### Capabilities:

1. Generally clueless
2. Script kiddies
3. Engineers
4. Insiders
5. Military/intelligence agencies

### Motivation:
- Curiosity or social credit   
- Hacktivism  
- Industrial espionage  
- Financial gain
- Weaken geopolitical adversary
- Foreign or domestic espionage

## Threat: A potential for violation of your security.
- Can be intentional or accidental
- A circumstance, capability, action, or event that could breach security and cause harm.
- Threats are impotent without a vulnerability to exploit.
- Can be caused by bad design causing it to be inadequte

## Vulnerability: A flaw that exposes the user, data or system to a threat.

- Vulnerabilities can be latent and may be protected by other code
so a vulnerability still exists,
- It is a vulnerability if it can be exploited to lead to a compromise.

Eg. Buffer overflows, WEP key leakage etc.

Where do they come from? 
- Bad software or hardware.
- Poor understanding of requirements/bad design
- Bad policy/configuration
- System misuse
- Unitended purpose or environment


## Attack:
- Occurs when adversary attempts to exploit a vulnerability. Taking over/altering resources.
## Compromise:
- Occurs when an attack is successful. The data can be used in some way.

## Risk:
Risk is often defined as:

R = T*V*C, where
T = Threat information(probability instantiated at a given time)
V = Existence of vulnerabilities
C = Cost of impact

Sometimes, R = P*C
p = Probability attacker is successful

- When we talk about risk, we talk about likelihood and impact.
- It is always more qualitative than quantitative.

## Threat model:
- Systematic identification of the threats a systems faces
- Capability + Motive

## Attack archetypes:

### Attacks
- Interception: Unauthorize access to an asset
- Modification: Unauthorized changes to an asset
- Fabrication: Creation of fake objects: files, messages etc.
- Interruption: Asset is "lost, unavailable, unusable

### Defenses:

- Prevention: Block the attack or close the vulnerability(P&P)
- Deterrence: Make attack harder
- Deflection:Make target less desirable
- Detection: Detect attack in progress and try to do something
- Recovery: Assume attack and just plan to fix things later

# Conferences for Cyber Security for ideas
1. Blackhat
2. DefCon
3. Bsides


# Lecture 3: 01/20: 
# Notes

## Authentication: Who are you?
Specify our policies and security in terms of identity.

## Authorization: What are you allowed to do?
- Professor can change grades, students can't

- Access control is an implementation of authorization

- Most situations don't have a situation where everyone has equal privilege


## Trust: How much is an entity is expected to behave?
- Degree to which an entity is dependent on it to behave.
- If the trust is violated, the security model is violated

- Trusted system is one whose failure can break the security policy.

- Trusted Computing Base(TCB) is the parts of the system you trust.

- A trustworthy system or component is one that won't fail.


The greater your risk, the more mechanisms you require to ensure your system is trustworthy.

Conservation of trust principle:

As much trust into the system as possible

Not all trusted systems are trustworthy
All trustworthy systems are trusted

Security model = trust + threat

1. What are the risks? Threats?
2. Who are our adversaries
3. Who do we trust and to do what
4. The "security requirements" use to develop some cogent and comprehensive design
5. What are the assets?
6. Are the defenses adequate to the value of the assets?

Every design must have a security model

It's not easy because,
1. Threats and adversaries change over time.
2. New attacks emerge
3. Very hard to retrofit - adding new functionality is always a pain


## Cost:
- Could be economic, engineering time, user time, usability, services, 
- 

## Principle of Adequate Protection:

- Systems must be protected to a degree consistent with their value.
- Systems must be protected only until they lose their value.
- Basic microeconomics: Decide something which maximizes the resources you have
- Unlikely attacks probably won't merit protection
- Cost of deployment is less than the expected cost of compromise.

### Basic terminology is done

## Cryptography:

- Greek, art of secret writing

To learn this, we start with a threat model:

### Participants: Alice and Bob
Alice sends a message to Bob in a public place.
### Eve: adversary who can hear public messages.

### Confidentiality:
- Keep data and communication secret
### Integrity
- Maintain the contents of the data basically.
### Availability

- It can't solve buffer overflows, worms, viruses, Trojan horses, SQL injection attacks, cross-site scripting, bad programming practices etc.
- It is a tool, not a solution

- None of us can make ciphers, we can design a basic protocol on top of it at the end of the class
- Use pre-existing libraries, packages, any constructs, things like that while designing your own protocol, for instance. 

### Terminology:

1. Cryptosystem:
2. Cryptography: The study of developing/building cryptosystems
3. Cryptoanalysis: The study of breaking cryptosystems
4. Cryptology: The study of cryptography and cryptoanalysis
5. Cipher: Term for Encryption algorithm

### Cryptosystem:
- 6-tuple: (E, D, G, M, C, K)
- G(keygen algorithm)
- E and D are the encryption and decryption keys respectively.

#### Symmetric key cryptography: Enc. and Dec. keys are the same.
#### Asymmetric key cryptography: Enc. and Dec. keys are different.

### Key: 
- Input to a cryptographic algorithm used to maintain security in the presence of an adversary.
- Keyspace: Set of all possible keys in a cryptosystem.
- Easiest way for attackers is to get the keys, larger keyspace makes it harder, large keyspace doesn't guarantee security.
- Kirchoffs principle: Assume the enemy knows the system so if they get your cipher, they can reverse engineer it.

- Easier to change a key
- Harder to keep an algorithm secret
- Easy to develop one algorithm used by everyone
- If public, weak systems will be quickly broken.

### Key management: Tough problem, no perfect answer.
- Who gets which keys?
- How do they securely get the keys?
- How do they store them?

### Security of a cryptosystem:
- Recovering the key, the plaintext(full) or partial, being able to produce a valid ciphertext, and being able to decipher an existing ciphertext.
- 

### Cryptoanalysis:

1. ciphertext-only
2. known-plaintext
3. chosen-ciphertext
4. chosen-plaintext:

#### Approaches:
1. Brute force
2. Linear cryptanalysis: construct linear equations
3. Differential cryptanalysis: Study how diffs in input can affect the resultant difference in output.
4. Side channel attacks: attack against the environment or implementation, can
5. Rubber hose cryptanalysis: if I know you have the key, i beat you with a rubber hose and take it.
### Key recovery attacks:


# Lecture 4: Notes: 01/22

# Ciphers

## Caesar Cipher

- Shift cipher
- ROT-13 - Shifts everything by 13 places
- Easy to do by hand
- Easy to break as well

# One-time pad(OTP) guarantees

- Offers "perfect secrecy"
- After the message is sent, key material is destroyed
- You XOR anything twice, you reverse the operation. ((A xor B) xor B) = A)

- The encryption is to XOR the data with the secret bit string.

- A system has perfect secrecy if,
    - Knowledge of the ciphertext yields no information about what the plaintext might be
    - There is always a key that maps any message to any ciphertext(these are equivalent)

- One-time pad is impossible to break, you cannot do better than it for confidentiality
- Two-time pad is trivial to break; it's terrible
- Thinking using something too many things is better works
- You need as much purely random keystream as the message you want to send.
- Don't use it because of key storage and key distribution

## Questions:
1. If you use it twice, it makes it a Legionnaire cipher.
2. One-time pad offers secrecy, but not integrity.
 So when it's decrypted, the message flips, you can change the message basically.
3. Malleable: An adversary can control the input and know that they have manipulated it
 We'll see how to prevent it also
4. Do we assume the adversary knows the length of the message? Yes.
5. Mayb

### Things about one-time pads:
- Smart
- Good-to-know
- Not used that much
- This comes under the category of unconditional or probabilistic security

# Symmetric key cryptography

## Conditional or Computational Security

- Cryptosystem is secure assuming a computationally bounded adversary, or under certain hardness assumptions, e.g., P<>NP
- Key sizes are much smaller, 128 bits.

## Block Ciphers vs Stream Ciphers

## Stream Ciphers:

- Generates a long keystream from a (short) key
- Acts like a random number generator with they key(and other info.) as the seed.
- The keystream can be used like the pad in a OTP
- No perfect secrecy
- Pseudorandom generation means not all keys are possible
- C{K} = pseudorandom stream produced using key K

- Countermeasure is to use IV(Initialization vector)
- IV is sent in clwar and is combined with K to produce pseudorandom sequence
- What if IV space is too small? IV space has to be same length as the key
- IV doesn't give away any info about the message

### Side notes on True and Pseudo-Randomness:

- True randomness is:
    - Uniform distribution of bits and
    - Independence
- Pseudorandomness is:
    - Approximately uniform distribution of bits
    - Cannot be independent since they are deterministically generated


## Block ciphers:

- fixed length input, fixed length output
- Confusion hides the relationship between the ciphertext and the key.
- Diffusion hides the relationship between the plaintext and the ciphertext
- Distributive plaintext statistics over the ciphertext.
- Make statistical analysis hard
- Most of them is some function of the initial key.

### Types of block ciphers:
- Data encryption Standard(DES) was released in the 70s and was weak then.
    - 56 bit keys, 64 bit block size. 
    - Variant: 3DES, better than DES, but still deprecated.
- Advanced encryption standard: Newer(2001)
    - 128-, 192, and 256-bit key lengt. Nobody uses 192 because they either need the smallest or the biggest lol.
    - 128 bit blocks which is long enough
    - Widely used
    - This is the block cipher you should use for newer systems

- Principle for cipher design: 
    - Nothing up your sleeves - All your choices for function design are transparent and you can't do anything badly

- Confusion - Relationship between key and data
- Permutation - Hiding the underlying distribution of data, but they both work together.


# Lecture 5

# Notes: 01/27

# Hashes and message authentication

## Objectives

- Create cryptographic constructions that provide integrity and authenticity
- Identify and explain the three properties of a cryptographic hash.
- Explain the significance of the birthday paradox to hash function security
- Explain how HMAC works and why it is needed
- Identify at least three applications of hash functions


## Encryption

- Confidentiality
- Cannot guarantee data integrity and doesn't provide source authentication
- Ensure that data is not altered from an authenticated source.

## Authentication vs Integrity

- Sometimes interchangeable. Getting one can give you the other.

### Integrity
- Data authentication is about ensuring that the data cannot be changed in an unauthorized way.
- Data has not changed on disk and the data has not changed on transit

### Authentication

- Ensuring that a message originated from a particular source.

## Message Authentication Codes (MACs)

- MACs provide message integrity AND authenticity.
- MACk(M) : MAC under some key K for a message M.
- Use symmetric encryption to produce short sequence of bits that depends on both the message (M) and the key (K)
- MACs should be resistant to *existential forgery*. Eve should not be able to produce a valid MAC for a message M' without the key K.
- To provide confidentiality, authenticity, and integrity of a message, Alice sends [EK(M), MACK(EK(M))] where EK(X) is encryption of X using key K
- This proves that M was encrypted(integrity and confidentiality) by someone who knew K(authenticity).
- In practice, you want to use different keys for E and MAC.
- Encrypt, then MAC.

## 3 Ways of combining encryption and MAC as discrete operations:

1. Encrypt-then-MAC(EtM) - IPSec. This is the best. Take the message, encrypt and then MAC of the encryption
2. Encrypt-and-MAC(E&M) - SSH. Bad. Leads tovulnerabilities. Take the message, encrypt it, and mac the message.
3. MAC-then-Encrypt(MtE) - Used in SSL/TLS: Prone to padding attacks

- All three are used in real protocols, but E&M and MtE require protocol modifications to be strongly unforgeable


## Hash Functions

- A hash function is a function with a
    - Arbitrary and variable length input (called a “pre-image”)
    - Fixed length output (called a “hash” or “message digest”)
- Usually seen in a hash table where it helps in efficient searching

## Properties of Hash functions:

- Compression: Reduces arbitrary length string to fixed length hash. Typically very lossy, but still useful.
- Ease of computation: Given message M, h(M) is easy to compute. The hash function is easy to compute so it is fast.

## Cryptographic Hash Functions

A cryptographic hash function is a hash function with certain properties:

1. Preimage Resistance: 
- Given digest y, computationally infeasible to find preimage x' such that h(x')=y
- Also called "one-way property"
2. 2nd-Pre-Image Resistance: 
- Given preimage x, computationally infeasible to find preimage x' such that h(x)=h(x')
- Also called “weak collision resistance” and “target collision resistance"
3. Collision Resistance: 
- Computationally infeasible to find preimages i, j such that h(i) = h(j)
- Also called “strong collision resistance”


#### It's about whether the adversary can decide what value to collide against.

- SHA-4 = {0 , 0
            1, 0
            x, SHA-3(x)}

- Collision resistant doesn't mean they don't have collisions, it means that you can't find it
- Does SHA-4 have strong collision resistance? No, because they'll just pick 1 or 0 and get the collision
- Is SHA-4 have weak collision resistance? Yes, because you can select a number and tell them to find.

### Why is one of them strong and one of them weak?

- The adversary has more control over the process
- Find me two numbers that have the same hash for a million dollars vs find one
- Strong works against more adversaries or smn?
- Always try to select something that is stronger, obviously.

## Consequences of these Properties

- For a good cryptographic hash, if you change one bit of the input, the output should change drastically and unpredictably.
- Outputs are functionally unpredictable.
- If you need to know if a file has changed, hash it.

# Making and Breaking Hashes:

## Common Hash functions:

- No formal design basis (concern is backdoors)
- MD2, MD4, MD5 (128 bit). In MD5, they violate target MD5 resistance.
    - Broken, Broken, Broken
- SHA-1 (160 bit)
    - Theoretical weaknesses Practical Collisions Broken
    - Systems like Git still produce a SHA-1 hash of commits. Changing will cause issues in backward compatibility and security.

- SHA-2 (224, 256, 384, or 512 bit): OK for now. Offers 4 different length of outputs, 224, 256, 284 and 512
- SHA-3 (variable length): OK for now. Offers variable length output.
- Attacks only get better as time goes on. - QUOTE

## General structure of a hash:

- Merkle-Daamguard Structure? This gives the name for hash functions such as MD5 as well.
- Hash function takes an arbitrary length input and provides an output.
- Build this through using a fixed length input and a smaller fixed-length output. 
- Compression algorithm.
- Pre-image is broken into blocks, Y1, ..., Yn
- f is a compression algorithms
- After the first block, you carry forward the output of the compression algorithm and mix in the value from the next block of the pre-image.
-  Naturally leads to a simple design if there is a good compression function
- If the compression function is good, then the technique is going to be secure.
- LOOK AT THE DIAGRAM.

## Birthday Attack

- A birthday attack is a name used to refer to a class of brute-force attacks
- Birthday paradox: the probability that two or more people in a group of 23 share the same birthday is greater than 50%

- General formulation (How to estimate)
    - On repeated random inputs n={n1, n2, ..., nk},
    - Pr(ni = nj) > 0.5 => 1.2k1/2, for some 1 <= i, j <= k, 1 <= j < k, i != j

- E.g., 1.2(3651/2) ~= 23
- Implication: Collisions can be found in approximately square root of the hash output size
- Hash size is basically cut in half because of the birthday paradox

## How do you find collisions effectively?


## Simple Hash Uses:

Commitment Schemes
- Use a hash to show that I know a secret I don’t want to reveal
- 0x342c6b4d0e6cde59946ac7f7591c6797
Finding identical files
- If two files have the same hash, the odds are very high they are the same files
- Very good mark of authenticity, one-way property.

## Password Storage

- Problem: the system must have some way of checking a password
without revealing it to other users or even administrators
-  Solution:
    - Simply store the hash of the password
    - When the user gives their password to log-in, hash their input and compare to the stored hash

- What could go wrong?
    - Most passwords are bad, so search a pre-computed list of hash values of top 1 mil commond passwords or something and just check.
- The fix:
    - Slow hash functions (bcrypt, scrypt, repeated hashing)
    - Salting: i.e., store [salt, h(salt | password)]

## Using hashes as authenticators

Consider the following scenario
– Prof. Smart E. Pants has not decided if she will cancel the next lecture.
– When she does decide, she communicates to Bob the student through Mallory, her
evil TA.
– She does not care if Bob shows up to a cancelled class, but she does not want
students to not show up if the class hasn’t been cancelled
– Prof. Pants does not trust Mallory to deliver the message.
• Prof. Smart E. Pants and Bob use the following protocol:
– Prof. Pants invents a secret t
– Prof. Pants gives Bob h(t), where h() is a crypto hash function
– If she cancels class, she gives t to Mallory to give to Bob
– If does not cancel class, she does nothing
– If Bob receives the token t, he knows that Prof. Pants sent it

### Why is this protocol secure?
- t acts as an authenticated value (authenticator) because
Mallory could not have produced t without inverting h()
- Note: Mallory can convince Bob that class is occurring
when it is not by simply not delivering t (but we assume
Bob is smart enough to come to that conclusion when the
room is empty)

- Note that it is important that Bob gets the original value h(t)
from Alice directly (was provably authentic)

### What is happening here?
- Check it against the hash I gave you previously, and use that authenticated value to validate and know what is happening

## Hash Chain

- Now, consider the case where Alice wants to do the same protocol, only for all 26 classes
(the semester)
- Alice and Bob use the following protocol:
    - Alice invents a secret t
    - Alice gives Bob H26(t), where H26() is 26 repeated uses of H().
    - If she cancels class on day d, she gives H(26-D)(t) to Mallory, e.g., • If cancels on day 1, she gives Mallory H25(t)
- If cancels on day 2, she gives Mallory H24(t)
- .......
- If cancels on day 25, she gives Mallory H~1~(t)
- If cancels on day 26, she gives Mallory t
- If Alice does not cancel class, she does nothing
- If Bob receives the token t, he knows that Alice sent it

## Merkle Hash Tree

## Creating a MAC from a Hash

- Consider the following simple hash-based MAC
    - MACk(M) = h(k|M)
- Suppose Eve wanted to append M’ to M?
    - Goal: compute h(k|M|M’) without knowing k

- Solution: Use h(k|M) as IV for next f iteration in h()
- Known as a Message Extension Attack

- When we do MEA, it's like we're concatenating on the input, like adding an m2. H(K||H(k||m) || m2)

- HMAC(m1 || m2) = H(k || H(K || m1 || m2))
- your adversary has failed to convince you is to, figure out the second term and do it backwards or get the key value, and do it forwards.
- But because of the one-way property, they can do neither.
- Difference between simple hmac and real hmac is the xor.
- The ipad and opad values are constant EVERYWHERE. Only purpose is to make sure the key on the inside and outside are different. Key values should be different for different purposes. Can break otherwise.

- Bitmasks are orthogonal? something
- Keys for different purposes should have different values. If you don't do it, it's fine, it might not break, but you should do it and it can def break. More info later in the class :D

- Q: Why does it 
- A: You can compute a value that extends simple HMAC, as in, the m2 value, can be computed. In the inner one, it's not possible to do. Basically, H(k|| m1 || m2) which is the inner one is not possible

## A Better MAC

### Objectives
- Use available hash functions without modification
- Easily replace embedded hash function as more secure ones are found
- Preserve original performance of hash function
- Easy to use

## To be continued

# Lecture 6

# Notes Online class

## Objectives

- Explain common uses of RSA
- Explain the components of RSA public and private keys and their relationship
- Given a small public/private key, encrypt/decrypt a message using RSA
- Identify and explain the hard problem underlying RSA
- Explain digital signatures, common uses, and compute a digital signature given a small RSA public/private key pair
- Explain the differences between a digital signature and an HMAC

## Asymmetric Crypto

Separate keys for encryption and decryption
- Public key: anyone can know this
- Private key: kept confidential
- Alice and Bob no longer have to have a priori shared a secret key
    - Anyone can encrypt a message to you using your public key
    - The private key (kept confidential) is required to decrypt the communication

- Is there still a problem? – Stay tuned for next class

- Each key pair consists of a public and private component: k+
(public key), k- (private key)

- Public keys are distributed (typically) through public key certificates
    - Anyone can communicate secretly with you if they have your correct certificate

- don't worry about rsa key gen stuff. why we care about factoring
- diffie hellman

# Lecture 8 - 02/10

# Key Management

## Key distribution
- process where we assign and transger keys to a participant
- Out of band(passwords) , during authentication(kerberos)

## Key agreement
- two parties negotiate a key
- two or more participants
- Occurs in conjunction with authentication

### How do we distribute keys?
- Secure key distribution without asymmetric cryptography is difficult.
- Simple approach: send key through an out-of-band channel
- It's a weird problem, you need security for the thing that helps us secure things, i.e., keys, that's why the out-of-band channel is simple.
### Cons
- it doesn't always work, you can't do this going there approach
- It's slower, and it's easy(to describe)


NC2 keys are required for pairwise key distribution

### What if there is no channel?

- Alice and Bob are gonna form a secret while Eve is listening and Eve is not going to know about it.

## Diffie-Hellman(DH) Key Agreement:

- This forming of the secret is called DH and the paper was revolutionary.
- Negotiate a secret over an insecure media
- Take two primes and multiply them, finding the factors of the product is very hard.

### Natural Log problem:

- log g(x) = i
- Given g and x, it is easy to find i such that g^i = x

### Discrete Log Problem

- Diffie-Hellman starts with this problem.
- dlog g,p(x) = i
- 

## DH Key Agreement

- System chooses g(base) and p(prime)
- Eve cannot compute K without knowing either a or b, even if she passively intercepts all comms.
- if he tries to find a or b, he hits the discrete log problem and with a p that is big enough, it is computationally infeasible.
- A = g^a mod p; B= g^b mod p; K = A^b mod p; K = B^a mod p
- g is generator
- p has to be prime

- g = 4; p = 13; x is less than p-1; 2-11
- cooked against powerful adversaries


x = 6; 
### Elliptic curve dh

- works under modular arithmetic normally
- over the set of functions called ellptic curves
- nobody understands it, leave it.

### On-path attacks on DH

- This is key agreement, not authentication.
- Mallory intercepts messages from both and gets the values

- Definitely not the only thing vulnerable to this.
- Not sure if the adversary is in a position to know the keys or not.

### Authenticated DH
- Alice and Bob sign the shares.

### Perfect forward secrecy
- K is valid just for the session
- Cannot be computed later if the adversary obtains
    - all network traffic
    - either or both private keys.
- you have future problems, not past problems.
`
## Why not use a DB?
- Every user has a public/private key.
- A trusted third party runs it.
- PGP: Pretty good privacy
- PGP Key server: look up the key on the server, put it in your client app.
- Can they maintain avalability? and not replace them or something
- Key signing.

# Lecture 9 - 02/12

## Web of Trust Model

- A trusts B, B trusts C, C trusts D, so A trusts D? and so on.
- Everyone is a certain number of hops away(6 degrees of kevin bacon)
- Used for PGP/GPG key management.

## Solving the turtles problem
- Need to have a recursive base case
- Root of trust needs to be decided which is the recursive base case.
- If you don't have that, you recurse forever, 
- the turtles problem means that the turtle carries the earth on its back. What's under the turtle, another turtle and so on? Old folklore.

## Certificates

- A certificate is a data structure that contains identity information, a public key and is signed by a Certificate Authority(CA).
- Signed by some Certificate Authority(CA)
- Bind identities to public keys.
- Identity may have been vetted by a registration authority
- Has a validity period.
- People trust a CA to vet identity.
- HTTPS is an example of this where S is the word secure and that validates against it. Caches, checks.
- Anything in your root certificate list is, gets to decide who the actual entity is. Decides which CA you can trust, and which is the real Amazon, for instance.

## Questions
- Every time you set up a new TLS connection, you set up a certificate check. 
- Can cache that info, lookup a few KB of data basically.
- The root certificate list changes only when the system update for it happens.
- Who authorizes the CAs? The companies themselves
- Are they regulated? No.
- Difference between RA and CA? 
- Netscape was working on TLS, 
- Mike Rider
- Didn't know whether the people who check identities and issues the certificates are the same.


### Public Key Infrastructure - PKI

- Any CA may sign any certificate.
- Browser weighs all root CAs equally.
- Caused DigiNotar.
- Cert pinning

## CA Pinning

## Certficate Transparency

- Monitor and audit certificates
- Allows efficient

## Revocation of Certificates

- Lost private key, compromised or owner no longer authorized.

- Revocation is hard, the verifiers need to check revocation state
- Revocation state must be authenticated.
- If you can change a system clock(difficult), you can use an expired CA.


## Getting HTTPS is hard
- Use "Lets encrypt", which was a developed CA, and Certificate Issuance and Renewal Protocol called ACME and will issue certificates.
- Getting it is hard, and have to pay someone 20$. Changed about 10 years ago.
- Build phishing sites at scale with a valid TLS certificate.



## Digtal Signatures
- ONLY sign and verify
- encrypt and decrypt is the opposite.
- Anyone with verification key can verify.
- Nobody can create a dfferent message-signature pair
- Cannot modify or fabricate them.
- Decryption key should be private, verify key should be public.


## Obtaining a certificate

- Alice has some identity document A 

# Lecture 10
# Notes

# Authentication protocols


## Definitions

1. Use cryptography to evaluate a protocol
2. To provide proof-of-knowledge of a cryptographic 

## Goals

1. (Always) verify the identity of "initiator" or "client"
2. (Usually) Verify identity of "server"
3. (Usually) Ensure "session" remains restricted to authorized parties.
4. (Usually) Establish "session key" or other mechanism to preserve confidentiality/integrity

## Part 2: Setting + Security Model

- Participants: A - "Alice", "client" or "init"
                B- "Bob","server" or "responder"
- Adversaries: E - "Eve", passive adversary
               M - "Mallory", active adversary


## Dolev Yao Threat Model

1. M can read, drop, modify or fabricate ANY me
ssage to/from ANY channel.
2. M can run multiple sessions serially or concurrently.
3. M knows the system/protocol + Cryptographic primitives, param, protocols
4. At the start of an evaluation, M doesn't know the keys and the cryptographic assumptions hold.

- Referred to as Dolev Yao adversaries

- Question: Adversary v attacker: Attacker is currently attacking, adversary has potential to attack
- for all intents and purposes, there's not much of a difference.

# Lecture 11?

# Notes

## Network Security Definitions:

## Properties of who?
- Network infrastructure
- Network services
- Network users

## Adversaries

- Passive eavesdroppers
- Active Dolev-Yao Attackers(aspiration for every attacker)
- compromised endpoints/servers
- small-scale DoS-er
- Bulk-scal DoS-er

## CIA Properties Again

## Ping-of-death



# Lecture 13

# Notes

## Objectives

- IP message spoofing, sequence number guessing, port scanning and ARP spoofing
- define and compare stateles and stateful firewalls
- Write a firewall

## ARP Spoofing

## MAC address

- Unique identifier for hardware
- Bound to the physical network interface, port or antenna
- Do VMs have MACs? Yes, as low as one per VM, as high as wahtever
- A value that some entity claims as identity
- MAC addresses are in the Data Link Layer, 
- IPs in Network layer, port numbers in Transport Layer
- Switches and switching
- L3 Switch
- Networks route, networks help you get across multiple links through a route
- The Link layer, learn the diff between routing and switching

## Address Resolution Protocol(ARP)

- How does Alice communicate with Bob over a LAN? ARP
- Protocol: Alice broadcasts, who has this IP?
- Bob responds, "I do!!"

## Defenses


## Network Scanning

- 
# Lecture 17

# Notes

## Wireless Security

- CIA Triad
- Convenience and mobility(leads to location)
- Authentication
- Privacy
- Location(touches on privacy)
- Identities

- In wireless, you are always a Dolev-Yao adversary
- Read, intercept, fabricate is easy.
- Modification is tricky, but doable(even 4G/5G)

## Confidentiality:

1. Traffic
- User plane content- If you connect to WiFi to send something, the bits you send
- Metadata and control plane content
- Transmission patterns; side channels, tracking

#### How packet streams can determine what content you are doing.
- You can understand the type of content obtained based on the packet stream coming in.
- Cellular is worse, because the pushes are scheduled.
- Privacy, censorship and anonymity- mess up the thing
- why not introduce randomness from the host.

2. Identities in network
- HW Addr, IP Addr, MAC Address, 
- Link identities, for eg. hardware Address, to packet information or something
- MAC Address Randomization- They are not static, or
- It is a privacy issue. 


3. Source/destination of messages
3. Location of entities in the network
4. Maybe: Reflected waveforms
- UHF and mmWave bands can be used for sensing
- Those machines in the airport are mmWaves 
- 5G is also waves
- 


### Authentication:

- Analog jamming
- Digital jamming

# Lecture 20?

# Notes

## Intrusion Detection/Prevention

## Old school

1. NIDS
2. HIDS
3. Anti-virus
4. Intrusion Prevention System
5. Honeypot/Honeynet

## Problems leading to the new world

1. Silos
2. Encryption
- "TLS everywhere" breaks payload inspection
- Detection moves to the endpoint
3. Mobility: 
- Starting moving to CDNs,
- People have their own devices even at universities
- No single chokepoint
- No idea what the perimeter of the network actually is.
- Zero Trust Architectures
4. Convergence
- HIDS + AV + Host firewall: 
- - EDR(Endpoint Detection & Response)
- EDR + NIDS + CLoud Telemetry: Crowdstrike uses this
- - XDR: Extended Detection and Response

Security Operation Center(SOC)
Security Information and Event Management(SIEM)- aggregate and correlate alerts

Security orchestration, automation, and response (SOAR)- automates the triage


## Signature detection

- if it can be described as a satisfiable language, you can do signature detection


## Anomaly detection

1. Underlying assumption, malicious will look different from non-malicious

2. Paradigm

## Evaluating an IDS

1. Confusion matrix
2. Precision Recall shi


## Tuning an IDS

- Most detectors are tunable
- Making these decisions in an arbitrary way is not ideal.

### ROC Curve(AUC)

- TPR(y) vs FPR(x)
- 

## Base rate fallacy

# Lecture 22?

# Notes

# Access Control

## Protection Principles:

### Saltzer Schroeder Principles

1. Economy of Mechanism
- keep the design as simple and small as possible
- fewer bugs, lower maintainability, harder to verify if it's correct(auditability)
- 
2. Fail-safe defaults
- Default settings should deny access unless explicitly granted.( Default deny)
- Minimizes risk of accidental exposure or modification
3. Complete Mediation
- Every access to a resource must be checked against the access control policy.
- Prevents unauthorized access through cached permissions or other shortcuts.
- Very difficult to implement, can't add security later.
4. Open Design
- The design of the system should be open to scrutiny and not rely on secrecy for security.
- Kirckhoff's principles: The enemy knows the system, should not rely on the ignorance of potential attackers.
5. Separation of privilege
6. Least privilege
- Every program and user should operate using the least set of privileges necessary to complete the task.
- Minimizes damage from attacks
- web server doesn't need administrative privileges
7. Least common mechanism
- Minimize the amount of mechanism cmmon to more than one user and depended on by all users. (prevent shared resource)
- Every shared mechanism represents a potential information path between users and must be designed carefully.
- Two processes that share the same filesystem cache may inadvertently share sensitive information.
- Isolation is very important in system security.
8. Psychological acceptability
- Security mechanisms should not make the resource more difficult to access than if the mechanism were not present.

## Access policy enforcement

- Protection State: Defines what each subkect can do to each object, or the access control policy.
- Reference monitor: Enforces the protection state.

- A correct reference monitor implementation meets the following guarantees
1. Complete mediation
2. Tamper-proof: The reference monitor cannot be modified or bypassed.
3. Verifiable: The reference monitor must be small enough to be verified
 
- A protection system is the protection state, the operations to protect that state, and the reference monitor that enforces the protection state.

## Access control matrix

- An access control matrix is a table that defines the access rights of subjects to objects.
- Rows represent subject S, columns represent obkects O, and entries represent the rights R.
- A matrix is not used that much, because it is SPARSE.
- Use an adjacency list instead.

## Approaches of adjacency list:

- Two common approaches:
1. Access control list: Store a list of subjects and their rights for each object.
2. Capability list(C-List)- Store list of objects and their rights for each subject.

What is capability: 

- Which one should you use?

- One consideration is where the reference monitor is, if it's closer to the subjects or objects.

## Discretionary access control(DAC)

- In a DAC system, the owner of an object determines who can access that object and what rights they have.
- The owner can modify the access control policy for their objects at their discretion.

- Filesystems are DACs.
- The Unix file permission models is a classic example of DAC.
- Each file has an owner, a group, and a set of permissions for the owner, group. and others.
- Permissions include read(r), write(w), and execute(x).

## Unix file permissions

- You need to have execute rights to parent directories to access a file.
- A user can delete a file if they have write access to the directory containn the file,
- Access rights are determined on a first-match-wins order,

## Mandatory Access Control (MAC):

- In a MAC system, the system enforces a fglobal access control policy that cannot be modified by users.
- In contrast to DAC systems where subjects are users and objects are files, in MAC systems, both subjects and objects are labels.
- Concrete subjects and objects are marked as labels.

Example: SE Linux

# Lecture 23

# Notes

## Integrity Models

## Role-based Access Control(RBAC)

- A role is a collection of privileges/permissions associated with some function or affiliation.
- In contrast to groups, the role

## Attribue Based Access Control (ABAC)

- Uses attributs of users, objects, and the environment to make access control decisions.
- Attributes can include user roles, object classifications, time of access, location, and more.
- Often expressed as logical rules.

## Next Generation Access Control(NGAC):

- Combines the concepts of roles, attributs, and policies to create a more flexible and powerful access control model.
- It organizes object

## Objectives

- unix environment deputies
- sandboxing, reference monitors
- virtualization
- containers

## UNIX Security

- classic DAC system
- anything that is a subject is a user
- any object is a file, and access control policy is spcified on files.
- Communicate to kernel with a system interrupt or write to certain files and the kernel will get the message.

### Filesystem namespace

- The filesystem defines a namespace that converts a name to a system resource
- The same file can be accessed via different paths.
## Attacks on Name resolution
### Improper binding attack:

- Adversar

### TOCTOU: Time Of check to Time of Use
- Race condition that exploits non-atomicity in "check" and "use" of resource to conduct improper resource and binding attacks.

## Sandboxing:
- An execution environment for programs that contains a limited set of rights
- - a subset of your permissions
- - cannot be changed by a running program

## UNIX chroot

- Creates a domain in which a process is confined


## Multics

- was created in 1960s by MIT, Bell Labs,
- High point in scure system design
- hierarchical filesystems, dynamic linking
- Secrecy: multi-level security
- Integrity: rings of protection
- Reference monitoring: mediats segment access, ring crossing.


# Lecture 24

# Notes

## Vulnerabilities

- Thinking: Fast & Slow

- System 1: Stress
- - Time pressure
- - Fight or flight
- - Strong emotions
- - Hunger

- Routine
- Consistency Bias

### Relational/ Social

- Authority bias
- Liking/ rapport bias
- Conformity & Social Proof

### Incentives

- Needs