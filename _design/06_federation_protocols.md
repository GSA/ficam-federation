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
- [iGov For OAuth2](#igov-for-oauth2)
- [iGov For OIDC](#igov-for-oidc)
- [Federal PKI](#federal-pki-fpki)

| <center>Protocol</center> | <center>Features</center> |
|:---------------------------------------:|-------------------------------|
| **SAML** | • **XML** based data exchange over HTTP or SOAP. <br/> • Open standard for both authentication and authorization. <br/> • Mostly used for securing web applications. <br/> • Data secured using XML Encryption. |
| **iGov For OAuth2** | • Based on **JSON** data format over HTTP. <br/> • OAuth is open standard for authorization. <br/> • Used for securing web and mobile apps. |
| **iGov For OIDC** | • Based on **JSON** data format over HTTP. <br/> • OIDC is open standard for authentication. <br/> • Used for securing web and mobile apps. |
| **Federal PKI** | • Can be used for both authentication and authorization. <br/>• Leverages PIV/CAC credentials issued by other agencies. <br/>• Federal PKI can be used in conjunction with SAML or iGov protocols. |

## Security Assertion Markup Language (SAML)

SAML is an open-standards for authentication and authorization between trusted entities over the internet.

- SAML standards use XML data type.
- Utilizes the XML Digital Signature envelopes to secure messages.
- It includes secure exchange format to preserve message confidentiality and integrity.
- It can also be used for non-repudiation.
- Latest version is SAML 2.0 though SAML 1.1 is also used. 

SAML is widely used for sharing data securely between websites such as your bank. This is also known as '_Web Browser SSO Profile_'. It comprises of the following three components.

- The Assertions XML schema, which defines the structure of the assertion.
- The SAML Protocols, which are used to request assertions and artifacts.
- SAML can be transported over HTTP or SOAP.

SAML Assertions are encoded in an XML schema and can carry up to three types of statements:

- **_Authentication statements_** include information about the assertion issuer, the authenticated subscriber, validity period, and other authentication information. For example, an Authentication Assertion would state the subscriber “John” was authenticated using a password at 10:32pm on 06-06-2004.
- **_Attribute statements_** contain specific additional characteristics related to the subscriber. For example, subject “John” is associated with attribute “Role” with value “Manager”.
- **_Authorization statements_** identify the resources the subscriber has permission to access. These resources may include specific devices, files, and information on specific web servers. For example, subject “John” for action “Read” on “Webserver1002” given evidence “Role”.

## iGov For OAuth2

**OAuth 2.0** (OAuth2) is a delegated web authorization protocol. It is used widely to request access to web facing applications using JSON data formats via REST APIs. Since OAuth2 does not support data transfer security other than TLS, the iGov specifications add security and interoperability to the protocol framework for federated access in the government context.

OAuth2 has the following roles:
- **_Resource Owner_** is most commonly the end-user who is granting access.
- **_Client_** is the application making the request on behalf of the resource owner, e.g. the web browser.
- **_Resource Server_** is the application that the client is requesting access to.
- **_Authorization Server_** is the application (IdP) which allows the client access using access tokens.

An **Access Token** is issued by the Authorization Server to the Client based on the Resource Owner successfully validating its credentials. This access token is presented to the Resource Server by the Client to request authorization to a specific end point. The access token has a specific scope such as HTTP URI, duration and other access parameters.

You will find these three commonly used profiles of iGov for OAuth2 which define the data requirements:
- OAuth2 Client Profiles
- OAuth2 Authorization Server Profiles
- OAuth2 Protected Resource Profiles

The **Client Profiles** define the data requested for authorization requests. It includes the full redirect URIs with a client ID. The iGov adds the authentication step for the client to the authorization server using the claims based tokens. The data should be signed by the client using its private key. There are different specifications for each type of client.

The **Authorization Server** Profiles are used to define how the authorization server (IdP) will interact with the client. The assertion will need to be encrypted using TLS endpoints. The **Protected Resource Profiles** define the requirements for the client requesting access to the Resource Server.

You will find more information at [IGov for OAuth 2.0](http://openid.net/specs/openid-igov-oauth2-1_0-02.html).

## iGov For OIDC

**OpenID Connect** (OIDC) protocol adds the authentication and profile information for web and mobile applications on top of the **OAuth 2.0 (OAUTH)** authorization protocol. It shares similar JSON data format for assertions. The iGov specifications are used to define the OIDC profile for securing federated access in the government context.

OIDC allows clients such as a web browser or a mobile device to access the authentication information of the end-user. In a successful OIDC transaction, the IdP issues an ID Token, which is a signed assertion in JSON Web Token (JWT) format. The client parses the ID Token to learn about the subscriber and primary authentication event at the IdP. 

In addition to the ID Token, the IdP also issues the client an OAuth 2.0 access token which can be used to access the UserInfo Endpoint at the IdP. This endpoint returns a JSON object representing a set of attributes about the subscriber, including but not limited to their name, email address, physical address, phone number, and other profile information. Access to different attributes from the UserInfo Endpoint is governed by the use of a specially-defined set of OAuth scopes, openid, profile, email, phone, and address.

There are two profiles in OIDC:
- **_OpenID Relying Party Profile_** defines the requests for authorization end points.
- **_OpenID Provider Profile_** defines the provider requirements such as signing the ID Token and support for the UserInfo endpoint.

An additional scope, **_offline_access_**, is used to govern the issuance of refresh tokens, which allow the SP to access the UserInfo Endpoint when the subscriber is not present. 

You will find more information at [IGov for OIDC](http://openid.net/specs/openid-igov-openid-connect-1_0-02.html).

## Federal PKI (FPKI)

A core component of the Federal Trust Framework, FPKI provides a common, government-wide infrastructure (e.g., policies, processes, server platforms, software, and workstations) for the purpose of administering digital certificates and public-private key pairs, including the ability to issue, maintain, and revoke public key certificates. 

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






































