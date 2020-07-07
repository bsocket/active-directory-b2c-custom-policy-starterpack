
 chprodb2c
ca87d35e-03fc-4de7-8565-4020cc890235 tenantid

SAML Steps:
https://docs.microsoft.com/en-us/azure/active-directory-b2c/connect-with-saml-service-providers
following directions in https://docs.microsoft.com/en-us/azure/active-directory-b2c/connect-with-saml-service-providers
1.Using the derived sociall only as the starting point so difference:
Changes in signup_signinCaravanHealth_saml.xml from copied file signup_signinCaravanHealth.xml
  i) B2C_1A_signup_signinCaravanHealth_saml name of file and policy in rename file. 
  ii) changed user journey Id ="SignUpSignInCaravanHealth"
  iii)token issuer step changed to 6
  iv ) changed   <OutputClaim ClaimTypeReferenceId="objectId" PartnerClaimType="objectId"/> to sub like in SignUpSignInCaravanHealth.xml file
changes in Trustframe extension:
            <Item Key="IssuerUri">https://chprodb2c.b2clogin.com/chprodb2c.onmicrosoft.com/B2C_1A_signup_signinCaravanHealth_saml</Item>
https://chprodb2c.b2clogin.com/chprodb2c.onmicrosoft.com/B2C_1A_signup_signinCaravanHealth_saml/Samlp/metadata
Info which needs to be provided by SAML App like jiraAccess whic will be put in manifest of the registerd app in the portal:
1.identifierUris
The identifierUris is a string collection containing user-defined URI(s) that uniquely identify a Web app within its Azure AD B2C tenant. Your service provider must set this value in the Issuer element of a SAML request.
2> samlMetadataUrl if not available seprately
replyUrlsWithType

{
  "typ": "JWT",
  "alg": "RS256",
  "kid": "scipYEy-RMYJyAn8CywaELLTcXMg6hlePLAmlhCAzns"
}.{
  "exp": 1593712479,
  "nbf": 1593708879,
  "ver": "1.0",
  "iss": "https://chprodb2c.b2clogin.com/ca87d35e-03fc-4de7-8565-4020cc890235/v2.0/",
  "sub": "057b4197-e625-4cf6-878f-00d2de8aa620",
  "aud": "5f1c51be-73a5-4f9f-823f-6fb7ec148d2d",
  "acr": "b2c_1a_signup_signincaravanhealth",
  "nonce": "defaultNonce",
  "iat": 1593708879,
  "auth_time": 1593708879,
  "idp": "https://portaldevidservice-as.azurewebsites.net",
  "name": "Ajay Wadhawan",
  "given_name": "Ajay",
  "family_name": "Wadhawan"
}.[Signature]
xp	Thu Jul 02 2020 10:54:39 GMT-0700 (Pacific Daylight Time)	The "exp" (expiration time) claim identifies the expiration time on or after which the JWT MUST NOT be accepted for processing. Implementers MAY provide for some small leeway, usually no more than a few minutes, to account for clock skew. [RFC 7519, Section 4.1.4]
nbf	Thu Jul 02 2020 09:54:39 GMT-0700 (Pacific Daylight Time)	The "nbf" (not before) claim identifies the time before which the JWT MUST NOT be accepted for processing. Implementers MAY provide for some small leeway, usually no more than a few minutes, to account for clock skew. [RFC 7519, Section 4.1.5]
ver	1.0	
iss	https://chprodb2c.b2clogin.com/ca87d35e-03fc-4de7-8565-4020cc890235/v2.0/	The "iss" (issuer) claim identifies the principal that issued the JWT. The processing of this claim is generally application specific. The "iss" value is a case-sensitive string containing a StringOrURI value. [RFC 7519, Section 4.1.1]
sub	057b4197-e625-4cf6-878f-00d2de8aa620	The "sub" (subject) claim identifies the principal that is the subject of the JWT. The claims in a JWT are normally statements about the subject. The subject value MUST either be scoped to be locally unique in the context of the issuer or be globally unique. The processing of this claim is generally application specific. The "sub" value is a case-sensitive string containing a StringOrURI value. [RFC 7519, Section 4.1.2]
aud	5f1c51be-73a5-4f9f-823f-6fb7ec148d2d	The "aud" (audience) claim identifies the recipients that the JWT is intended for. Each principal intended to process the JWT MUST identify itself with a value in the audience claim. If the principal processing the claim does not identify itself with a value in the "aud" claim when this claim is present, then the JWT MUST be rejected. [RFC 7519, Section 4.1.3]
acr	b2c_1a_signup_signincaravanhealth	Authentication Context Class Reference. String specifying an Authentication Context Class Reference value that identifies the Authentication Context Class that the authentication performed satisfied. The value "0" indicates the End-User authentication did not meet the requirements of ISO/IEC 29115 [ISO29115] level 1. Authentication using a long-lived browser cookie, for instance, is one example where the use of "level 0" is appropriate. Authentications with level 0 SHOULD NOT be used to authorize access to any resource of any monetary value. [OpenID Connect Core 1.0, Section 2]
nonce	defaultNonce	String value used to associate a Client session with an ID Token, and to mitigate replay attacks. The value is passed through unmodified from the Authentication Request to the ID Token. If present in the ID Token, Clients MUST verify that the nonce Claim Value is equal to the value of the nonce parameter sent in the Authentication Request. If present in the Authentication Request, Authorization Servers MUST include a nonce Claim in the ID Token with the Claim Value being the nonce value sent in the Authentication Request. Authorization Servers SHOULD perform no other processing on nonce values used. The nonce value is a case sensitive string. [OpenID Connect Core 1.0, Section 2]
iat	Thu Jul 02 2020 09:54:39 GMT-0700 (Pacific Daylight Time)	The "iat" (issued at) claim identifies the time at which the JWT was issued. This claim can be used to determine the age of the JWT. [RFC 7519, Section 4.1.6]
auth_time	Thu Jul 02 2020 09:54:39 GMT-0700 (Pacific Daylight Time)	Time when the End-User authentication occurred. [OpenID Connect Core 1.0, Section 2]
idp	https://portaldevidservice-as.azurewebsites.net	
name	Ajay Wadhawan	End-User's full name in displayable form including all name parts, possibly including titles and suffixes, ordered according to the End-User's locale and preferences. [OpenID Connect Core 1.0, Section 5.1]
given_name	Ajay	Given name(s) or first name(s) of the End-User. Note that in some cultures, people can have multiple given names; all can be present, with the names being separated by space characters. [OpenID Connect Core 1.0, Section 5.1]
family_name	Wadhawan	Surname(s) or last name(s) of the End-User. Note that in some cultures, people can have multiple family names or no family name; all can be present, with the names being separated by space characters. [OpenID Connect Core 1.0, Section 5.1]