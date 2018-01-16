---
layout: default
title: Federation Protocols
permalink: /federation_protocols/
---

-- Section 11 Examples of NIST SP 800-63C --

Three types of assertion technologies are discussed below: SAML assertions, OpenID Connect tokens, and Kerberos tickets. This list is not inclusive of all possible assertion technologies, but does represent those commonly used in federated identity systems.

## Security Assertion Markup Language (SAML)

SAML is an XML-based framework for creating and exchanging authentication and attribute information between trusted entities over the internet. As of this writing, the latest specification for SAML is SAML v2.0, issued 15 March 2005.
The building blocks of SAML include:

- The Assertions XML schema, which defines the structure of the assertion.
- The SAML Protocols, which are used to request assertions and artifacts (the assertion references used in the indirect model described in Section 7.1).
- The Bindings, which define the underlying communication protocols (such as HTTP or SOAP), and can be used to transport the SAML assertions.

The three components above define a SAML profile that corresponds to a particular use case such as “Web Browser SSO”.
SAML Assertions are encoded in an XML schema and can carry up to three types of statements:

- Authentication statements include information about the assertion issuer, the authenticated subscriber, validity period, and other authentication information. For example, an Authentication Assertion would state the subscriber “John” was authenticated using a password at 10:32pm on 06-06-2004.
- Attribute statements contain specific additional characteristics related to the subscriber. For example, subject “John” is associated with attribute “Role” with value “Manager”.
- Authorization statements identify the resources the subscriber has permission to access. These resources may include specific devices, files, and information on specific web servers. For example, subject “John” for action “Read” on “Webserver1002” given evidence “Role”.


## OpenID Connect (OIDC)

OpenID Connect builds on top of the OAuth 2.0 authorization protocol to enable the subscriber to authorize the RP to access the subscriber’s identity and authentication information. The RP in both OpenID Connect and OAuth 2.0 is known as the client.

In a successful OpenID Connect transaction, the IdP issues an ID Token, which is a signed assertion in JSON Web Token (JWT) format. The client parses the ID Token to learn about the subscriber and primary authentication event at the IdP. This token contains at minimum the following information about the subscriber and authentication event:

- iss - An HTTPS URL identifying the IdP that issued the assertion.
- sub - An IdP-specific subject identifier representing the subscriber.
- aud - An IdP-specific audience identifier, equal to the OAuth 2.0 client identifier of the client at the IdP.
- exp - The timestamp at which the ID Token expires and after which SHALL NOT be accepted the client.
- iat - The timestamp at which the ID Token was issued and before which SHALL NOT be accepted by the client.

In addition to the ID Token, the IdP also issues the client an OAuth 2.0 access token which can be used to access the UserInfo Endpoint at the IdP. This endpoint returns a JSON object representing a set of attributes about the subscriber, including but not limited to their name, email address, physical address, phone number, and other profile information. While the information inside the ID Token is reflective of the authentication event, the information in the UserInfo Endpoint is generally more stable and could be more general purpose. Access to different attributes from the UserInfo Endpoint is governed by the use of a specially-defined set of OAuth scopes, openid, profile, email, phone, and address. 

An additional scope, offline_access, is used to govern the issuance of refresh tokens, which allow the RP to access the UserInfo Endpoint when the subscriber is not present. Access to the UserInfo Endpoint is structured as an API and may be available when the subscriber is not present. Therefore, access to the UserInfo Endpoint is not sufficient for proving a subscriber’s presence and establishing an authenticated session at the RP.

## Kerberos Tickets

Kerberos supports authentication of a subscriber over an untrusted, shared local network using one or more IdPs. The Kerberos Network Authentication Service [RFC 4120] was designed to provide strong authentication for client/server applications using symmetric-key cryptography on a local, shared network. Extensions to Kerberos can support the use of public key cryptography for selected steps of the protocol. Kerberos also supports confidentiality and integrity protection of session data between the subscriber and the RP. Even though Kerberos uses assertions, it was designed for use on shared networks and, therefore, is not truly a federation protocol.









































