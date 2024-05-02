# Introduction

A digital credential links claims about a subject and their cryptographic keys. Some sets of claim names have already been defined by the IETF and other standards development groups (e.g., OpenID Foundation).

Digital credentials typically involve at least three entities: issuer, holder, and verifier. An issuer constructs and secures a digital credential for a holder. Holders may be willing either to partially disclose some values of their attributes or to demonstrate some properties about their attributes without disclosing their values. Holders disclose credentials, attributes, or proofs regarding attributes in what is called a "digital presentation" to a verifier.

Some holders may wish to carry more than one digital credential. These credentials, together with associated key material, can be stored in an identity digital wallet.

# Goal

The SPICE WG will analyze existing and emerging IETF technologies and address residual gaps that would enable their use in digital credentials and presentations.

* The JOSE WG is already standardizing a token format for unlinkability & selective disclosure in the form of JWP/CWP (draft-ietf-jose-json-web-proof). The SPICE WG will profile these token formats for use with digital credentials.
* The OAUTH WG is already standardizing a token format for unlinkability & selective disclosure in the form of SD-JWT/SD-JWT-VC (draft-ietf-oauth-selective-disclosure-jwt and draft-ietf-oauth-sd-jwt-vc). The SPICE WG will define SD-CWT/SD-CWT-VC, analogs for these JWT-based tokens but based on CWT.

The SPICE WG coordinates with RATS, OAuth, JOSE, COSE, and SCITT working groups that develop documents related to the identity and credential space. The SPICE WG builds on existing cryptographic primitives and does not define novel cryptographic schemes.

The SPICE WG develops digital credential profiles which can support a number of use cases. To help guide engineering decisions, requirements for proposed standards in the program of work will be created in coordination with the working groups listed above. The profiles developed by the SPICE WG will enable digital credentials to leverage existing IETF technologies.

Privacy by design, confidentiality, and consent will be considered, and implementation guidance will be given for each proposed standard in the program of work.

The privacy and security considerations related to the impact of confidential computing, remote attestation, trusted execution environments (TEE), and hardware security modules (HSM) on digital credentials will be developed in coordination with relevant IETF WGs (e.g., TEEP) and feedback from experts on the mailing list.

Privacy and security considerations regarding redaction, linkability and selective disclosure will be developed for proposed standards in the program of work.

SPICE will be inspired by the conceptual data model of the W3C VC but will not work on the Resource Description Framework (RDF) data models.

# Out of Scope

* General Key discovery is out of scope for this WG. There are several mechanisms for distributing or discovering key material (e.g., https://openid.net/specs/openid-connect-discovery-1_0.html).

# Program of Work

* An informational Architecture that defines the terminology (e.g., Issuer, Holder, Verifier, Claims, Credentials, Presentations) and the essential communication patterns between roles, such as credential issuance, where an issuer delivers a credential to a holder, and presentation, where a holder delivers a presentation to a verifier.
* Proposed standard documents for digital credential profiles covering JWP and CWP (from JOSE) that enable digital credentials with unlinkability and selective disclosure. This work will include registering claims that are in the JWT and CWT registries to enable digital credentials to transition from one security format to another (i.e., JSON/CBOR).
* Proposed standard document defining SD-CWT, a profile of CWT inspired by SD-JWT (from OAuth) that enables digital credentials with unlinkability and selective disclosure.
* A proposed standard Metadata & Capability Discovery protocol for JWT, CWT, SD-JWT, SD-CWT, CWP and JWP using HTTPS/CoAP for CBOR-based digital credentials to enable the 3 roles (issuers, holders and verifiers) to discover supported capabilities, protocols and formats for keys, claims, credential types and proofs. The design will be inspired by the OAuth "vc-jwt-issuer" metadata work (draft-ietf-oauth-sd-jwt-vc) which supports ecosystems using JSON serialization.
