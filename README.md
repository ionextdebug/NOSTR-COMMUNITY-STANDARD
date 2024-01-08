# WARN | MOVED TO

To better organize the standard I moved this repository to new address below, please follow and collaborate in the new repository:

https://github.com/Notes-Machine/NOSTR-Community-Standard

-----

The NOSTR Community Standard is a standard created for community, with MIT license, to introduce a more formal and dynamic way to transform the NIPs in a set of human-readable and software developer friendly set of rules.

You can contribute adding clauses, warnings, and guides.

This is inspired in C++ ISO Standard and ECMA specifications for EcmaScript (JavaScript).

The output value of your contribution is a document to software developers easy understand the protocol and implement new tools for the community according to the community standard.


All the clauses need to be based on NIPs.

## GLOSSARY

**CLAUSE**: a requirement to well implement this step of the NIP.

**WARN**: an important commentary about the `CLAUSE`.

**INFO**: a informational commentary about the `CLAUSE`.

**GUIDE**: an external link of a free tutorial, guide, book, or practical content teaching how to implement the clause.

**ERROR_TAG**: a stable string naming a type of violation of one specific clause or subclause. Please, increment new `ERROR_TAG`s in the document "error_tags.json".

**Well-formed**: an implementation that follows the standard.

**Ill-formed**: an implementation that don't follows the standard.

**Component**: the same as "user", "client", or "relay" (or combination of them).

## HOW TO CONTRIBUTE

You can contribute creating pull requests after changed this document.

**WARN**: Add new clauses or new subclauses, don't try to change the sequence of main/head clauses. Maintaining the order of the clauses' number is important to future references, e.g., debugging tools. We need to work on stable tags to referencing clauses' violations.

## HOW TO USE (EXAMPLE)

You can do references to the main/head clauses, not for subclauses, following the pattern `/NIP-[0-9]+\-CLAUSE-[0-9]+/`, e.g.: `ERROR NIP-100-CLAUSE-11` or `ERROR NIP-01-CLAUSE-11`.

**WARN**: You can use any pattern to do your references, but only referecing to clauses is safe, referecing to subclauses is not safe. Subclauses' number can be incremented and eventually changed.

**INFO**: In near future we will has `tag` to identify each clause or subclause violation, then you will can refer using the stable tags.


# THE NOSTR COMMUNITY STANDARD



***CLAUSE 0***. NOSTR is a federation of relays, users, and clients ruled by the mandatory NIP-01 and other optional NIPs.


## NIP-01 


> “This NIP defines the basic protocol that should be implemented by everybody.”

***CLAUSE 1***: A component that does not implement the mandatory NIP-01, or respect the requirements to implement an optional NIP, is classified as an ill-formed component.



> “New NIPs may add new optional (or mandatory) fields and messages and features to the structures and flows described here.”


***CLAUSE 2***. A well-formed component (relay, client, user) that implements an optional NIP needs to implement it, if implemented any, according to the requirements of each optional NIP.


> “Each user has a keypair.”


***CLAUSE 3***.  A user has a key pair consisting of a public key and a private key.


> “Signatures, public key, and encodings are done according to the Schnorr signatures standard for the curve secp256k1”


***CLAUSE 4***. Signatures, public key, and encodings are done according to the BIP 340 entitled as “Schnorr Signatures for secp256k1”.


> “The only object type that exists is the event”


***CLAUSE 5***. The only standard object type defined in the mandatory NIP-01 is the event; all components must support this type. An optional NIP can define a custom subtype.


> “which has the following format on the wire:”


***CLAUSE 6***. The type event is a key-value dictionary with the following properties: "id", "pubkey", "created_at", "kind", "tags", "content", and "sig". Each property has a defined steady format.

***WARN***: consult the NIP-01.

CLAUSE 6.1. The property event.id is generated according to the NIP-01 specification.

***WARN***: consult the NIP-01.

CLAUSE 6.2. The property event.tags is a multi-dimensional array (array of arrays) with N optional subarrays. Each optional subarray has two required elements: “name” (also called “key”), and “value”; and can have context-based optional elements.

> “This NIP defines 3 standard tags that can be used across all event kinds with the same meaning. “


***CLAUSE 7.*** The NIP-01 defines three standard tag types. The components to be well-formed need to support these three tag types according to the specifications in NIP-01. These tag types are: “e”, “p”, “a”.

***WARN***: consult the NIP-01.

> “Kinds specify how clients should interpret the meaning of each event and the other fields of each event”


***CLAUSE 8.*** The property event.kind defines the context of the event, and the event interpretation is context-based. Then, other event’s properties are interpreted according to the event.kind.


CLAUSE 8.1. The NIP-01 defines two standard kinds, the “0” (metadata) and the “1” (text note).

***WARN***: consult the NIP-01.

CLAUSE 8.2. The range [1000, 40000) needs to be used according specified in NIP-01.

***WARN***: consult the NIP-01.

***CLAUSE 9.*** The NIP-01 defines three types of client messages: “EVENT”, “REQ”, and “CLOSE”.

***WARN***: consult the NIP-01.

CLAUSE 9.1. “EVENT” is used to publish events.

CLAUSE 9.2. “REQ” is used to request or subscribe to events.

CLAUSE 9.3. “CLOSE” is used to unsubscribe from events.


***CLAUSE 10.*** The NIP-01 defines four types of relay messages: “EVENT”, “OK”, “EOSE”, “CLOSED”, and “NOTICE”.

***WARN***: consult the NIP-01.

CLAUSE 10.1. “EVENT” is used to send request events to the clients.

CLAUSE 10.2. “OK” is used to indicate if a “EVENT” message was accepted or denied.

CLAUSE 10.3. “EOSE” is used the end of stored events and the start of real-time events.

CLAUSE 10.4. “NOTICE” is used to send human-readable messages.
