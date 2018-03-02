---
layout: default
title: Federation Protocols
permalink: design/federation_protocols/
collection: design
pubDate: 
---

- Audience: Engineers/Architects
- Introduce the federation protocols - SAML, OIDC (igov), Kerberos and FPKI.
- Refer to Section 11 Examples of NIST SP 800-63C for SAML OIDC and Kerberos.
- Introduce FPKI and provide links to the FPKI Guides for more information.

=================================

The federation protocols are used to transfer data from the IdP to SP during a federation process. Though you will find different types of protocols used in federated identity systems, we will discuss the following protocols that relate to Federation in the Federal Government.

- [SAML](#security-assertion-markup-language-saml)
- [iGov For OIDC](#igov-for-oidc)
- [iGov For OAuth](#igov-for-oauth2)
- [Federal PKI](#federal-pki-fpki)

These pointers will help you understand the basic differences between them.
- SAML is **XML** based, while iGov for OIDC/OAuth protocols are built on **JSON** data format.
- SAML is mostly used for web applications.
- OIDC and OAuth are used in web or mobile apps.
- Federal PKI can be used in conjunction with SAML or iGov.
- SAML can utilize **XML data encryption** to secure data while in transit.
- OIDC and OAuth protocols rely on **TLS** for security while data is in motion.

## Security Assertion Markup Language (SAML)

SAML is an open-standards based XML data exchange framework for creating and exchanging authentication and attribute information between trusted entities over the internet. 

- SAML standards include secure exchange format to preserve message confidentiality and integrity.
- It can also be used for non-repudiation.
- Utilizes the XML Digital Signature envelopes to secure messages.
- Latest version is SAML 2.0 though SAML 1.1 is also used. 

SAML is widely used for sharing data securely between websites such as your bank. This is also known as '_Web Browser SSO Profile_'. It comprises of the following three components.

- The Assertions XML schema, which defines the structure of the assertion.
- The SAML Protocols, which are used to request assertions and artifacts.
- SAML can be transported over HTTP or SOAP.

SAML Assertions are encoded in an XML schema and can carry up to three types of statements:

- _Authentication statements_ include information about the assertion issuer, the authenticated subscriber, validity period, and other authentication information. For example, an Authentication Assertion would state the subscriber “John” was authenticated using a password at 10:32pm on 06-06-2004.
- _Attribute statements_ contain specific additional characteristics related to the subscriber. For example, subject “John” is associated with attribute “Role” with value “Manager”.
- _Authorization statements_ identify the resources the subscriber has permission to access. These resources may include specific devices, files, and information on specific web servers. For example, subject “John” for action “Read” on “Webserver1002” given evidence “Role”.

## iGov For OIDC

The iGov specifications are used to define the OpenID Connect (OIDC) profile for securing federated access in the government context.  OIDC builds on top of the **OAuth 2.0 (OAUTH)** authorization protocol to enable your agency users to authorize the SP to access the  identity and authentication information. The SP in both OpenID Connect and OAuth 2.0 is known as the client. 

In a successful OpenID Connect transaction, the IdP issues an ID Token, which is a signed assertion in JSON Web Token (JWT) format. The client parses the ID Token to learn about the subscriber and primary authentication event at the IdP. This token contains at minimum the following information about the subscriber and authentication event:

- iss - An HTTPS URL identifying the IdP that issued the assertion.
- sub - An IdP-specific subject identifier representing the subscriber.
- aud - An IdP-specific audience identifier, equal to the OAuth 2.0 client identifier of the client at the IdP.
- exp - The timestamp at which the ID Token expires and after which SHALL NOT be accepted the client.
- iat - The timestamp at which the ID Token was issued and before which SHALL NOT be accepted by the client.

In addition to the ID Token, the IdP also issues the client an OAuth 2.0 access token which can be used to access the UserInfo Endpoint at the IdP. This endpoint returns a JSON object representing a set of attributes about the subscriber, including but not limited to their name, email address, physical address, phone number, and other profile information. While the information inside the ID Token is reflective of the authentication event, the information in the UserInfo Endpoint is generally more stable and could be more general purpose. Access to different attributes from the UserInfo Endpoint is governed by the use of a specially-defined set of OAuth scopes, openid, profile, email, phone, and address. 

An additional scope, offline_access, is used to govern the issuance of refresh tokens, which allow the SP to access the UserInfo Endpoint when the subscriber is not present. Access to the UserInfo Endpoint is structured as an API and may be available when the subscriber is not present. Therefore, access to the UserInfo Endpoint is not sufficient for proving a subscriber’s presence and establishing an authenticated session at the RP.

## iGov For OAuth

The iGov specifications are used to define the OpenID Connect (OIDC) profile for securing federated access in the government context.  OIDC builds on top of the **OAuth 2.0 (OAUTH)** authorization protocol to enable your agency users to authorize the SP to access the  identity and authentication information. The SP in both OpenID Connect and OAuth 2.0 is known as the client. 

In a successful OpenID Connect transaction, the IdP issues an ID Token, which is a signed assertion in JSON Web Token (JWT) format. The client parses the ID Token to learn about the subscriber and primary authentication event at the IdP. This token contains at minimum the following information about the subscriber and authentication event:

- iss - An HTTPS URL identifying the IdP that issued the assertion.
- sub - An IdP-specific subject identifier representing the subscriber.
- aud - An IdP-specific audience identifier, equal to the OAuth 2.0 client identifier of the client at the IdP.
- exp - The timestamp at which the ID Token expires and after which SHALL NOT be accepted the client.
- iat - The timestamp at which the ID Token was issued and before which SHALL NOT be accepted by the client.

In addition to the ID Token, the IdP also issues the client an OAuth 2.0 access token which can be used to access the UserInfo Endpoint at the IdP. This endpoint returns a JSON object representing a set of attributes about the subscriber, including but not limited to their name, email address, physical address, phone number, and other profile information. While the information inside the ID Token is reflective of the authentication event, the information in the UserInfo Endpoint is generally more stable and could be more general purpose. Access to different attributes from the UserInfo Endpoint is governed by the use of a specially-defined set of OAuth scopes, openid, profile, email, phone, and address. 

An additional scope, offline_access, is used to govern the issuance of refresh tokens, which allow the SP to access the UserInfo Endpoint when the subscriber is not present. Access to the UserInfo Endpoint is structured as an API and may be available when the subscriber is not present. Therefore, access to the UserInfo Endpoint is not sufficient for proving a subscriber’s presence and establishing an authenticated session at the RP.

## Federal PKI (FPKI)

A core component of the Federal Trust Framework, FPKI provides a common, government-wide
infrastructure (e.g., policies, processes, server platforms, software, and workstations) for the
purpose of administering digital certificates and public-private key pairs, including the ability to
issue, maintain, and revoke public key certificates. 

Federal PKI Policy Authority (FPKIPA) and the Federal PKI Management Authority (FPKIMA) are the 
Federal Trust Framework governance bodies for PKI credentials. The policies of the FPKIPA and 
services of the FPKIMA help to create an environment in which different organizations can 
trust each other‘s PKI credentials. The creation and issuance of PKI credentials that can be trusted
across the Federal Government is governed by two Federal PKI components:

- Federal Bridge Certification Authority (FBCA)
> The FBCA maintains peerto-peer cross-certified relationships with Enterprise PKI implementations, including
federal agency legacy PKIs and commercially-operated PKIs. The FBCA and the entities/agencies it interacts 
with can maintain, issue and revoke public key certificates.

- Federal Common Policy Framework Certification Authority (FCPCA)
> The FCPCA is the Federal PKI Trust Root, which acts as the top of a hierarchy. The FCPCA also includes a
set of shared service providers from whom federal agencies can acquire PKI services that
comply with policy requirements outlined in Federal PKI Common Policy Framework282
(COMMON) and FBCA Certificate Policy.

By leveraging the FPKI certificates, an agency is provided with several benefits.
- Streamlined compliance with federal requirements.
- Enhanced ability to trust and leverage external PKI credentials.
- Increased ability to leverage stronger forms of authentication.

For more information on FPKI, visit the [FPKI Guide](https://fpki.idmanagement.gov).






































