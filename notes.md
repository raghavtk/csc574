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


### which is the most important? depends on your security model, i.e., the context.

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
- can be intentional or accidental

a potential for violation of security, which


## Vulnerability: a flaw that exposes the user, data or system to a threat.
Eg. Buffer overflows, WEP key leakage etc.
where do they come from? bad software or hardware.
Poor understanding of requirements/bad design
bady policy/configuration
system misuse
unitended purpose or environment

- vulnerability: can be latent and may be protected by other code
so a vulnerability still exists,

Vulnerability exists if it can be exploited.


## Attack: occurs when adversary attempts to exploit a vulnerability.
Compromise: Occurs when an attack is successful. The data can be used in some way.

## Risk:
Risk is often defined as:

R = T*V*C, where
T= threat information(probability instantiated at a given time)
V= existence of vulnerabilities
C= cost of impact

sometimes R = P*C
p = probability attacker is successful

Threat model: Systematic identification of the threats a systems faces
Capability + Motive

Attack archetypes:

Attacks 
- Interception: Unauthorize access to an asset
- Modification: Unauthorized changes to an asset
- Fabrication: Creation of fake objects: files, messages etc.
- Interruption: Asset is "lost, unavailable, unusable

Defenses:

- Prevention: Block the attack or close the vulnerability(P&P)
- Deterrence: Make attack harder
- Deflection:Make target less desirable
- Detection: Detect attack in progress and try to do something
- Recovery: Assume attack and just plan to fix things later

Conferences for Cyber Security for ideas
blackhat, defcon, bsides

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

A trustworthy system or component is one that won't fail.


The greater your risk, the more mechanisms you require to ensure your system is trustworthy.

Conservation of trust principle:

as much trust into the system as possible

not all trusted systems are trustworthy
All trustworthy systems are trusted

Security model = trust + threat

1. What are the risks? Threats?
2. Who are our adversaries
3. who do we trust and to do what
4. the "security requirements" use to develop some cogent and comprehensive design
5. What are the assets?
6. Are the defenses adequate to the value of the assets?

Every design must have a security model

It's not easy because,
1. threats and adversaries change over time.
2. New attacks emerge
3. very hard to retrofit - adding new functionality is always a pain


## Cost:
- Could be economic, engineering time, user time, usability, services, 
-

## Principle of Adequate Protection:

- Systems must be protected to a degree consistent with their value.
- Systems must be protected only until they lose their value.
- basic microeconomics: Decide something which maximizes the resources you have
- unlikely attacks probably won't merit protection
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

- It can't solve buffer overflows, worms, viruses, trojan horses, SQL injection attacks, cross-site scripting, bad programming practices etc.
- It is a tool, not a solution

- None of us can make ciphers, we can design a basic protocol on top of it at the end of the class
- use pre existing things

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
- Kirchoffs principle: assume the enemy knows the system so if they get your cipher, they can reverse engineer it.

- Easier to change a key
- Harder to keep an algorithm secret
- Easy to develop one algorithm used by everyone
- If public, weak systems will be quickly broken.

### Key management: Tough problem, no perfect answer.
- Who gets which keys?
- How do they securely get the keys?
- How do they store them?

### Security of a cryptosystem:
- recovering the key, the plaintext(full) or partial, being able to produce a valid ciphertext, and being able to decipher an existing ciphertext.
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

## Ciphers

### Caesar Cipher

- Shift cipher
- ROT-13 - Shifts everything by 13 places
- Easy to do by hand
- Easy to break as well

## One-time pad guarantees

- offers "perfect secrecy"
- after message is sent, key material is destroyed
- you XOR anything twice, you reverse the operation. ((A xor B) xor B) = A)

- The encruption is to XOR the data with the secret bit string.








