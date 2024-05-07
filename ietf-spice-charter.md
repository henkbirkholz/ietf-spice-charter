# Introduction

A digital credential intends to link claims regarding a subject and their cryptographic keys. Various sets of claim names that can represent credential attributes have already been defined by the IETF (per RFC 7519 and RFC 8392) and other standards development groups, such as the OpenID Foundation.

Digital credentials typically involve at least three entities: issuer, holder, and verifier. An issuer constructs and secures a digital credential for a holder. Holders may be willing either to partially disclose some values of their attributes or to demonstrate some properties about their attributes without disclosing their values. Holders disclose credentials, attributes, or proofs regarding attributes in what is called a "digital presentation" to a verifier.

Some holders may wish to carry more than one digital credential. These credentials, together with associated key material, can be stored in an identity digital wallet.

# Goal

The SPICE WG shall analyze existing and emerging IETF technologies and address any remaining gaps to facilitate their application in digital credentials and presentations.

* The JOSE WG is currently standardizing a token format for unlinkability and selective disclosure as specified in JWP/CWP (draft-ietf-jose-json-web-proof). The SPICE WG shall profile these token formats for application in digital credentials.
* The OAUTH WG is currently standardizing a token format for unlinkability and selective disclosure in the form of SD-JWT/SD-JWT-VC (draft-ietf-oauth-selective-disclosure-jwt and draft-ietf-oauth-sd-jwt-vc). The SPICE WG shall define SD-CWT/SD-CWT-VC, which are analogous to these JWT-based tokens, but based on CWT.

The SPICE WG shall coordinate with RATS, OAuth, JOSE, COSE, and SCITT working groups that are involved in developing documents pertinent to the identity and credential space. The SPICE WG shall build build upon existing cryptographic primitives and shall not define novel cryptographic schemes.

The SPICE WG shall develop digital credential profiles that support various use cases. Requirements for proposed standards in the program of work shall be established in coordination with the aforementioned working groups. The profiles developed by the SPICE WG shall enable digital credentials to leverage existing IETF technologies.

Privacy by design, confidentiality, and consent will be considered, and implementation guidance will be given for each proposed standard in the program of work.

Privacy and security considerations concerning the impact of confidential computing, remote attestation, trusted execution environments (TEE), and hardware security modules (HSM) on digital credentials shall be developed in coordination with relevant IETF WGs (e.g., TEEP) and incorporate feedback from experts on the mailing list.

Privacy and security considerations regarding redaction, linkability and selective disclosure will be developed for proposed standards in the program of work.

SPICE will be inspired by the conceptual data model of the W3C VC but will not work on the Resource Description Framework (RDF) data models.

# Out of Scope

* General Key discovery is out of scope for this WG. There are several mechanisms for distributing or discovering key material (e.g., https://openid.net/specs/openid-connect-discovery-1_0.html).

# Program of Work

* An informational Architecture that defines the terminology (e.g., Issuer, Holder, Verifier, Claims, Credentials, Presentations) and the essential communication patterns between roles, such as credential issuance, where an issuer delivers a credential to a holder, and presentation, where a holder delivers a presentation to a verifier.
* Proposed Standard documents for digital credential profiles covering JWP and CWP (from JOSE) that enable digital credentials with unlinkability and selective disclosure. This work will include registering claims that are in the JWT and CWT registries to enable digital credentials to transition from one security format to another (i.e., JSON/CBOR).
* Proposed Standard document defining SD-CWT, a profile of CWT inspired by SD-JWT (from OAuth) that enables digital credentials with unlinkability and selective disclosure.
* A Proposed Standard Metadata & Capability Discovery protocol shall be developed for JWT, CWT, SD-JWT, SD-CWT, CWP and JWP using HTTPS/CoAP. This protocol, intended for CBOR-based digital credentials shall enable the three roles —issuers, holders and verifiers— to discover supported capabilities, protocols, and formats for keys, claims, credential types and proofs. The design shall be inspired by the OAuth "vc-jwt-issuer" metadata work (draft-ietf-oauth-sd-jwt-vc), which supports ecosystems using JSON serialization.
