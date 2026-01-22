# Computer Network Security: CSC574

# Notes: 13/01

## What do you hope to learn in this course

1. Learn the fundamentals of security, layer by layer
2. Learn good practices and writing secure code
3. Different kinds of attacks and how the design should have been better to ensure those didn't happen
4. how do you design systems that are secure maybe use of AI in mobile network security stuff?
how do mobile networks

systems attacks and defences

reading is 10% of grade
project

## What does it mean for a system to be secure?

- The data that flows through the system cannot be stolen at any point.

- The system should be able to handle load(large number of requests)

- The data in a particular part of the system does not provide infor about the entire system.

## Important definitons

- If it can maintain well-specified properties despite the actions of well-specified adversaries. - IMPORTANT

- The set of properties we assume to be correct is called the trust model

- The set of adversaries and their capability we assume to be correct is called the threat model

- Trust model + threat model = security model


# Notes: 15/01


## What we'll be tested on:
1. Definitions of security
2. Define adversary, trust and security model
3. Create and critique security models for familiar systems
4. Go through the slides and figure out questions.

Today:

# Fundamentals: Today is terminology day

## CIA Triad:

1. Confidentiality: Protect against unauthorized disclosure.
2. Integrity: social media or something, where you want the identity to be verified, but data is out
3. Availability: Protect and maintain authorized access: Shouldn't be able to just turn it off

- When integrity over confidentiality? social media, open-source code, your signature on a public form,


### Which is the most important? depends on your security model, i.e., the context.

Guesses from the class:
Privacy
P-authentication
P-authorization
attack surface - hmm
cost - hmm

Extra in the list:
resiliency
non-repudiation

I - auditability
accounting
non-repudiation

anonymity is completely different from privacy

## Assets: What we protect:

1. Hardware resources, 2. network access, 3. operating systems, 4. software, 5. data
6. Users can be considered as assets that deserve protection on their own.
7. User Time: if you're a bank and you're being attacked and you keep the system up and a click takes 5 mins to process. User Time is wasted, literally.
8. Reputation.
9. Money managed by system

## Participants: computers, agents, people, enterprises. Sometimes referred to as: principals, servers, clients, users, entities, hosts, routers
- expected systems, entities.
- Security is defined w.r.t these entities.
- every party may have unique view.

## A trusted third party = trusted by all parties for some set of actions, often used as introducer or arbiter


## Adversaries:
Anyone attempting to violate your trust model: circumvent the security infrastructure.

fundamental difference between security and safety/reliability/quality is because of the notion of an adversary.

## Characterizing adversaries:

### Capabilities:

1. generally clueless
2. script kiddies
3. engineers
4. insiders
5. military/intelligence agencies

### Motivation:
- curiosity or social credit   
- hacktivism  
- industrial espionage  
- financial gain
- weaken geopolitical adversary
- foreign or domestic espionage

## Threat: some potential violation of your security model.
- Can be intentional or accidental
- Potential for violation of security, which


## Vulnerability: a flaw that exposes the user, data or system to a threat.
Eg. Buffer overflows, WEP key leakage etc.
where do they come from? bad software or hardware.
Poor understanding of requirements/bad design
Bad policy/configuration
System misuse
Unitended purpose or environment

- Vulnerabilities can be latent and may be protected by other code
so a vulnerability still exists,

- A vulnerability exists if it can be exploited.


## Attack:
- Occurs when adversary attempts to exploit a vulnerability.
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


# 01/20: Notes

## Authentication: Who are you
Specify our policies and security in terms of identity.

## Authorization: What are you allowed to do?
- Professor can change grades, students can't

- Access control is an implementation of authorization

- Most situations don't have a situation where everyone has equal privilege


## Trust: How much an entity is expected to behave
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

### Symmetric key cryptography: Enc. and Dec. keys are the same.
### Asymmetric key cryptography: Enc. and Dec. keys are different.

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


# Notes: 01/22

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
- - Knowledge of the ciphertext yields no information about what the plaintext might be
- - There is always a key that maps any message to any ciphertext(these are equivalent)

- One-time pad is impossible to break, you cannot do better than it for confidentiality
- Two-time pad is trivial to break; it's terrible
- Thinking using something too many things is better works

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
- - Uniform distribution of bits and
- - Independence
- Pseudorandomness is:
- - Approximately uniform distribution of bits
- - Cannot be independent since they are deterministically generated


## Block ciphers:

- Confusion hides the relationship between the ciphertext and the key.
- Diffusion hides the relationship between the plaintext and the ciphertext
- Distributive plaintext statistics over the ciphertext.
- Make statistical analysis hard
- Most of them is some function of the initial key.

### Types of block ciphers:
- Data encryption Standard(DES) was released in the 70s and was weak then.
- - 56 bit keys, 64 bit block size. 
- - Variant: 3DES, better than DES, but still deprecated.
- Advanced encryption standard: Newer(2001)
- - 128-, 192, and 256-bit key lengt. Nobody uses 192 because they either need the smallest or the biggest lol.
- - 128 bit blocks which is long enough
- - Widely used
- - This is the block cipher you should use for newer systems

- Principle for cipher design: 
- - Nothing up your sleeves - All your choices for function design are transparent and you can't do anything badly

- Confusion - Relationship between key and data
- Permutation - Hiding the underlying distribution of data, but they both work together.



