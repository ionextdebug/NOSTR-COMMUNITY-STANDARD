This document describe the NIPs in a more formal way, being inspired by C++ Standard for Compiler vendors. You can contribute adding information about NIPs, and improving the clauses.

## GLOSSARY

**CLAUSE**: a requirement to well implement this step of the NIP.

**WARN**: an important commentary about the `CLAUSE`.

**INFO**: a informational commentary about the `CLAUSE`.

**GUIDE**: an external link of a free tutorial, guide, book, or practical content teaching how to implement the clause.

**Well-formed**: an implementation that follows the standard.

**Ill-formed**: an implementation that don't follows the standard.


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
