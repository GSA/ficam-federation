#---
layout: default
title: Federation Assertion
permalink: design/federation_assertion/
collection: design
pubDate: 
#---

- Audience: Engineers/Architects
- Introduce what assertions are and why they are important in sharing data during federation.
- Sections 5, 6 Assertions of NIST SP 800-63C are good sections on Assertions.

An assertion used for authentication is a packaged set of attribute values or attribute references about or associated with an authenticated subscriber that is passed from the IdP to the RP in a federated identity system. Assertions contain a variety of information, including: assertion metadata, attribute values and attribute references about the subscriber, and other information that the RP can leverage (such as restrictions and expiration time). While the assertion’s primary function is to authenticate the user to an RP, the information conveyed in the assertion can be used by the RP for a number of use cases — for example, authorization or personalization of a website. These guidelines do not restrict RP use cases nor the type of protocol or data payload used to federate an identity, provided the chosen solution meets all mandatory requirements contained herein.

Assertions MAY represent only an authentication event, or MAY also represent attribute values and attribute references regarding the subscriber.

All assertions SHALL include the following assertion metadata:
1. Subject: An identifier for the party that the assertion is about (i.e., the subscriber).
2. Issuer: An identifier for the IdP that issued the assertion.
3. Audience: An identifier for the party intended to consume the assertion (i.e., the RP).
4. Issuance: A timestamp indicating when the IdP issued the assertion.
5. Expiration: A timestamp indicating when the assertion expires and SHALL no longer be accepted as valid by the RP (i.e., the expiration of the assertion and not the expiration of the session at the RP).
6. Identifier: A value uniquely identifying this assertion, used to prevent attackers from replaying prior assertions.
7. Signature: Digital signature or message authentication code (MAC), including key identifier or public key associated with the IdP, for the entire assertion.
8. Authentication Time: A timestamp indicating when the IdP last verified the presence of the subscriber at the IdP through a primary authentication event (if available).

Assertions MAY also include the following information:
1. Key binding: Public key or key identifier of subscriber-held key to demonstrate their binding with the assertion described in Section 6.1.2.
2. Attribute values and attribute references: Information about the subscriber.
3. Attribute metadata: Additional information about one or more subscriber attributes, such as that described in NIST Internal Report 8112 [NISTIR 8112].

Assertions SHOULD specify the AAL when an authentication event is being asserted and IAL when identity proofed attributes (or references based thereon) are being asserted. If not specified, the RP SHALL NOT assign any specific IAL or AAL to the assertion.

## Assertion Binding
Assertion binding can be classified based on whether presentation by a claimant of an assertion, or an assertion reference, is sufficient for binding to the subscriber, or if the RP requires additional proof that the assertion is bound to the subscriber.

### Bearer Assertions
A bearer assertion can be presented by any party as proof of the bearer’s identity. If an attacker can capture or manufacture a valid assertion or assertion reference representing a subscriber and can successfully present that assertion or reference to the RP, then the attacker could be able to impersonate the subscriber at that RP.
Note that mere possession of a bearer assertion or reference is not always enough to impersonate a subscriber. For example, if an assertion is presented in the back-channel federation model (described in Section 7.1), additional controls MAY be placed on the transaction (such as identification of the RP and assertion injection protections) that help further protect the RP from fraudulent activity.

### Holder-of-Key Assertions
A holder-of-key assertion contains a reference to a key possessed by and representing the subscriber. The key referenced in a holder-of-key represents the subscriber, not any other party in the system including the browser, IdP, or RP. Note that the reference to the key is asserted (and signed) by the issuer of the assertion.

In proving possession of the subscriber’s key to the RP, the claimant also proves with a certain degree of assurance that they are the rightful subject of the assertion. It is more difficult for an attacker to use a stolen holder-of-key assertion issued to a subscriber, since the attacker would need to steal the referenced key material as well.

The following requirements apply to all holder-of-key assertions:
1. The subscriber SHALL prove possession of that key to the RP, in addition to presentation of the assertion itself.
2. An assertion containing a reference to a key held by the subscriber for which key possession has not been proven SHALL be considered a bearer assertion by the RP.
3. Reference to a given key SHALL be trusted at the same level as all other information within the assertion.
4. The assertion SHALL NOT include an unencrypted private or symmetric key to be used with holder-of-key presentation.
5. The key MAY be distinct from any key used by the subscriber to authenticate to the IdP.
6. The key MAY be a symmetric key or a public key that corresponds to a private key.
7. The RP MAY verify the claimant’s possession of the key in conjunction with the IdP, for example, by requesting that the IdP verify a signature or MAC calculated by the claimant in response to a cryptographic challenge.







































