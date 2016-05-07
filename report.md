Extracted from the [Open Banking Report](http://theodi.org/open-banking-standard)

# 7c. Security

## 7c. 1 Outline

This chapter covers three broad areas.
1. Security aspects of the API specification, including authentication, authorisation, access
levels and permission and encryption.
2. Security standards for data attribute providers and third-parties.
3. Security aspects of open data.

## 7c. 2 Key Recommendations

### 7c. 2.1 User consent

In the context of data-sharing with a third-party a principle of informed consent should be adopted.

The user should clearly understand the authorisation they are being asked to provide, including:

 - who they are providing authorisation to;
 - what they are providing authorisation for (i.e. what the authorisation will permit the third party to do);
 - how long the authorisation will last for.

### 7c. 2.2 Authentication

The process through which a customer authenticates itself to its data attribute provider (in order to further authorise a third party access) will be a tripartite process and should be designed to minimise digital friction. Specifically:

 - data attribute providers and third parties should retain control over authentication method.
 - OAuth 2.0 in conjunction with OpenID Connect are recommended as authentication protocols
of choice – future work will be needed to specify the precise model.

### 7c. 2.3 Fraud detection and monitoring

 - The API should provide support for out-of-band (OOB21) authentication.
 - Data Attribute Providers should be required to notify the user asynchronously/OOB when
significant actions have occurred (e.g. a change to a payee).
 - The API response should inform the third party that an OOB process is underway so that,
where appropriate, they can inform the customer.
 - The practicality of including fraud-relevant information (e.g. IP addresses) in the API return message from the third party should be assessed in future work.

### 7c. 2.4 Authorisation

Once a customer has authenticated with their data attribute provider tokens should be used to ensure the third party is acting within the bounds of the permissions granted. The third-party service should provide evidence that it is entitled to use the authorisation token (e.g. by way of providing a client ID and client secret) to the data attribute provider Each data attribute provider will be responsible for issuing its own tokens and ensuring third parties are in possession of legitimate tokens.

 - Permissions: access granted to third-party providers should be defined in terms of specific
permissions to data and/or functionality. To reflect the potential risks from malicious misuse of permissions and protect consumers’ interests, the following are recommended:
  - Granting users and, in certain instances the data attribute provider revocation rights;
  - Requiring data attribute providers to establish a mechanism through which users can
review and cancel their permissions;
  - Assigning risk levels to permissions;
  - Allowing for prohibitions on granting permissions;
  - Placing contextual limits on permissions where appropriate (e.g. payment limits);
  - Subjecting permissions to time/duration limits.
  - Roles: a set of permissions and roles should be defined with a standardised nomenclature in
future work.
  - Encryption: API connections and data in transit should be encrypted using TLS v1.2 as a
minimum.
 - Certification: should be used to coordinate the management and issuing of digital certificates with a whitelist of approved companies.
 - Security standards: it is suggested to use the Cheque Printers Accreditation Scheme (CPAS)
as a model, i.e. a security accreditation model based on ISO27001 with a specific minimum
threat profile, against which independent auditors can assess the security of data attribute
providers and third parties (it may be appropriate to grant a waiver to certain data attribute
providers, e.g. banks).

It is recommended that the task of defining a threat profile relevant to the open banking environment be carried out by a body that includes relevant professional individuals and wider representative stakeholders with experience of the financial sector and the threats the third parties and data attribute providers are likely to face. A control framework should be implemented to address the risk profile to set a reasonable industry standard security control.

This should be done in such a way that allows flexibility for future threats and technical flexibility to allow innovation in implementation of the controls.

## 7c. 4 Risks

The growing threat from cyber-criminals means that the adoption of the Open Banking API brings with it significant security challenges. Banks have traditionally protected their clients' accounts and information within a clearly defined and tightly controlled environment. Allowing customers to grant third parties access to their data will expand the security perimeter beyond the data attribute providers' control, and introduce new risks. Responsibility for protecting clients' data will be shared by third parties.

The design of the Open Banking Standard must take account of this new security paradigm and
address the risks it brings.

### 7c. 4.1 Open Banking API as a new attack vector

As a new technology and method of gaining access to customer data, it is likely that cyber-criminals will specifically focus on the open API as a new attack vector. The ability to amend or make payments will be a specific driver. Attacks are likely to include both exploiting any technical weaknesses that may exist in implementations of the open API, supporting applications and services, or through social engineering of customers who will be unfamiliar with the API process. Details obtained may be leveraged to effect an account takeover or commit fraud through other channels.

The rollout of the Open Banking API may also provide opportunities for bad actors to exploit customers’ naiveté or lack of familiarity with the processes surrounding the API to conduct phishing or social engineering attacks (e.g. criminals could attempt to create fake apps or services, or prompt customers to provide authority to a third party but not actually read the requests properly, just simply approve whatever has been requested in order to let the app or service work).

### 7c. 4.2 Aggregation of data at third parties

Third parties that collate and store data on behalf of customers are likely to become a primary target for criminals. A popular “main player” in this area could potentially hold a significant amount of customer data, across multiple data attribute providers. Compromising this single entity could be easier and more lucrative than attacking multiple data attribute providers.

### 7c. 4.3 Intermediary third parties

In the event that third parties are permitted to act as intermediaries for other third parties, there is the risk that data may be passed on to third parties that do not have appropriate security measures in place. Special consideration should be given to this scenario and clear policies should be put in place to govern and restrict how data obtained by the primary third party is passed to secondary third parties, and define what vetting requirements and security standards secondary third parties will be subject to.

### 7c. 4.4 Compromise of customer devices

Customer devices) such as personal computers, laptops, tablets and smartphones are commonly
targeted by cyber-criminals, and have been shown to be highly susceptible to compromise. As a
result, any data or credentials (e.g. access tokens) that are stored on customer devices are at risk of compromise.

Furthermore, when a customer device is used to access an API), the risk exists that a bad actor that compromises the customer device may be able to access the API by controlling the device remotely, effectively impersonating the user.

The opportunity to mitigate the risk of such attacks is limited. Therefore, the Open Banking API should include measures designed to minimise their impact if and when they do occur.

### 7c. 4.5 Emerging threats

Not all risks and threats can be anticipated. The security risk landscape will evolve and develop over time as existing security technologies become obsolete and bad actors develop new techniques. New threats may emerge that require rapid, decisive and coordinated action by third parties and data attribute providers.

The Open Banking Standard must be capable of recognising, reacting and adapting to emerging risks and threats. Requirements that third parties and data attribute providers share information on security incidents will facilitate recognition (see section 7c. 11.4: Information sharing and incident handling).

Policies and procedures should be established to support the implementation of changes to the Open Banking Standard at short notice.

## 7c. 5. Consumer Protection

### 7c. 5.1 Customer confidence

Customer confidence is built on a number of tangible and intangible elements and security clearly plays an important role Customer confidence in the API ecosystem is likely to be bolstered if it is clear that that third parties and data attribute providers are subject to appropriate security standards and that appropriate protections are in place from a fraud perspective.

Ultimately, for customers, confidence may also link to the question of liability for losses that result from security breaches. This has security implications in that the security measures and standards employed should align with and support the liability model. Further consideration should be given to this topic at the next stage of the Open Banking Standard development.

### 7c. 5.2 Usability vs. security

It is important to ensure that security measures are put in place to mitigate risks associated with the Open Banking API. However, these should not be so restrictive and/or onerous that they
unreasonably reduce the utility, usability and benefits derived from products and services reliant on APIs. The challenge is to balance customer protection with the potential benefits.

A possible benchmark to use for determining whether usability is unreasonably restricted is to
compare the functionality offered by the open API with that offered by data attribute providers’ existing websites and apps. For example, if, within the scope of the Open Banking API, a data attribute provider’s own website and mobile app were to offer significantly more functionality than is available through the API, that would suggest that the API may be unduly restricted.

Data attribute providers, and any other institutions, are free to provide additional services on top of the core Open Banking API; the point here is that restrictive practices (e.g. unnecessarily complex controls) for commonly defined services will be unacceptable.

Recent research published by Ipsos MORI and Barclays shows that for customers using API-based products security is important and “consumer protecton needs to form a key part of any developments in this area”. See htp://www.ipsosmori.com/researchpublicatons/publicatons/1769/Open-API-Exploring-the-views-of-consumers-and-small-businesses.aspx

Balancing usability and security inevitably requires a certain amount of risk acceptance. It is important that consumers are made aware of and understand the risks they may be incurring by making use of a third party’s service or app.

### 7c. 5.3 Informed consent

#### 7c. 5.3.1 Clarity

A core principle of this report is informed consent. This is discussed further in chapter 9, however, the principle of informed consent implies that the customer must be able to clearly understand the authorisation they are being ask to provide, including:

 - who they are providing authorisation to;
  - what they are providing authorisation for (i.e. what the authorisation will permit the third party to do);
 - how long the authorisation will last for.

If the third party intends to share the customer’s information with another party, this must also be made clear and the customer must be given the opportunity to opt out of having their data shared.

Customers must have the ability to review this information before, during and after authorisation has been granted and to revoke any authorisation they have previously granted. They must also have confidence that their data will not be retained by a third party unnecessarily after authorisation to access it has expired or been revoked. It is the responsibility of each third party and data attribute provider to ensure they are complying with relevant Data Protection Act (DPA).

#### 7c. 5.3.2 Common terminology

The Open Banking Standard must define common terminology for describing the fine-grained
permissions defined by the API, as well as any roles that may be granted. Definitions must be simple, concise and easily understood by customers. All parties should adhere to the standard terminology, with any variance highlighted and explained clearly.

Where a data attribute provider extends the functionality of their API beyond the core Open Banking API, care should be taken to ensure that users can distinguish between core and non-core functionality.

Information about the authorisations the customer is being asked to grant, or has granted, to third parties should be presented in clear and simple language (i.e. plain English). A standardised format and lexicon for third parties’ terms and conditions governing customer data should form part of the standard.

## 7c. 6 Fraud Detection/Monitoring

It is anticipated that banks’ existing fraud monitoring mechanisms will be utilised to detect fraudulent activity carried out through the APIs. Consideration should be given to mandating the supply of relevant information by third parties to data attribute providers to support risk-profiling activity (e.g. IP address, user agent, customer device characteristics). It is recommended that the Open Banking API allow third parties to supply such information within API messages.

Existing fraud information-sharing mechanisms are expected to be extended into this space (e.g.
those provided by Financial Fraud Action UK). Explicit API functionality to support out of band challenges should be put in place to allow data attribute providers to require an additional level of authentication before an action is authorised (e.g. a new payment). Third parties should also be able to request/trigger re-authentication by the data attribute provider (e.g. in the event that the third party detects suspicious activity that may not be
apparent to the data attribute provider).

The API should support the use of one-time transaction authorisation codes that are supplied out of band to be submitted via the API, as well as transactions that must be authorised entirely outside the API. The latter implies that the API must also support the concept of “queued” or “pending” transactions that must be authorised by the customer before the data attribute provider will accept/action them.

We expect that data attribute providers will notify users asynchronously/ out of band (e.g. using SMS or push notifications) in a timely manner when significant actions are carried out via the API (e.g. the granting of permissions to a third party, the instruction of payments by third parties).

## 7c. 7 Alignment with Existing Standards

### 7c. 7.1 Existing security standards that can form part of the Open Banking API

As far as is practicable, existing, mature, open security protocols and standards should be leveraged for the Open Banking API. There are a number of obvious candidates for incorporation into the technical Open Banking API specification (e.g. TLS, OAuth and OpenID Connect).
There is also a range of security standards and schemes that should be taken into consideration, both in terms of application to data attribute providers and third parties, and also in terms of how these standards can be enforced. Examples include:

 - ISO27000 family of security standards;
 - PCI DSS;
 - CPAS;
 - tScheme.

It is suggested to adopt a security standards approach based on the ISO/IEC 27000 series of
standards, with a tiered approach, i.e. the standard the third party is required to meet and the degree of scrutiny to which it is subject should be commensurate with the access the third party seeks to obtain. For lower levels of access (e.g. accessing open data), self-certification may be judged sufficient while high levels may require that the third party’s compliance with the relevant standards be independently audited. This is the approach adopted by e.g. PCI DSS.

The servers and infrastructure operated by third parties and data attribute providers must be
protected against cyber-attack. Security standards should mandate security controls that are
commensurate with the nature of the data and functionality that is provided. At this stage, this report is not broaching details pertaining to appropriate security controls, but it is expected they will include the use of penetration testing, firewalls, intrusion detection systems, hardware security modules, OS patching policies, etc. It is recommended that a specific workstream is established to define the security standards in this area and then to review them at appropriate intervals to ensure that they are kept up to date with emerging threats and technologies.

Existing financial institutions (i.e. future data attribute providers) have built up considerable experience in this area; their input is expected to prove valuable.
The need and extent to include security testing of applications and servers on a timely basis is a topic that should be covered in further detail in future stages of work.
There are a number of other working groups and standards bodies undertaking work that has bearing on, or parallels with the Open Banking API, whose work could be leveraged as appropriate.

Peer review is also an important step in the design of security standards. It is recommended that appropriate organisations and individuals be identified and invited to review and comment upon proposals and drafts produced in the process of creating the Open Banking API.

It is also recommended that work towards the Open Banking API be conducted as openly as is
practicable and that the public is given the opportunity to review and comment on it informally (e.g. through mailing lists or social media).

## 7c. 8. Security and Authentication Aspects of the API Specification

### 7c. 8.1 Authentication

#### 7c. 8.1.1 User experience, process and technical data flow

Within the context of an Open Banking API, there are four authentication scenarios:

 - The customer authenticating themselves to an data attribute provider (in order to authorise a third party);
 - The customer authenticating themselves to a third party;
 - The third party authenticating themselves to an data attribute provider (in order to access a customer’s data);
 - The third party authenticating themselves to a customer.

Data attribute providers and third parties should own and control the method by which they
authenticate their customers.23 The methods by which a third party authenticates itself to a data attribute provider, and a user may identify a third party, should form part of the Open Banking API specification.

The process by which a customer authenticates themselves to a data attribute provider in order to authorise the granting of permissions to a third party will be a tripartite process, which should be designed in a way that minimises digital friction, to avoid discouraging or confusing customers. It will potentially involve a hand-off of customer interaction from the third party to the data attribute provider for the authentication to be carried out, followed by a redirect of the customer back to the third party from the data attribute provider after the authentication and authorisation interaction process has been completed.

This approach has the benefit of allowing the data attribute provider to continue to own and control the method for authenticating its customers (thereby minimising the risk that a third party could obtain permissions without explicit approval by the customer) and avoids mandating the use of specific authentication methods. Separately, customers will also need to authenticate themselves to third parties in order to gain access to the services or functionality being provided. The method used by both data attribute providers and third parties to authenticate customers should be appropriate to adequately protect the data and functionality in question.

[Figure 7c.1 Authentication and authorisation: customer experience example (account
aggregation)](./Figure7c.1.png)

[Figure 7c.2 Authentication and authorisation: high-level process flow](./Figure7c.2.png)


Figure 7c.3 Authentication and authorisation: technical data flow
*TODO: Add Link*


#### 7c. 8.1.2 Selection of OAuth 2.0 with future consideration of OpenID Connect

The Fingleton Report recommended the use of the OAuth 2.0 protocol, which supports the tripartite approach outlined in 7c. 8.1.1. This report endorses this recommendation, although further consideration must be given to the specific implementation.

The OAuth 2.0 protocol supports a variety of different interpretations and styles of interaction, with different security implications. The Open Banking API should prescribe how authentication and authorisation aspects of the standard are implemented, so the appropriate levels of consistency, interoperability and security are achieved. It is recommended that the OpenID Connect authentication protocol (which provides an identity layer on top of the OAuth 2.0 protocol) be considered as part of this process. Appendix 6 sets out some considerations pertaining OAuth 1.0 and 2.0 and OpenID Connect.

Having been granted permission to access a customer’s account information and act on the
customer’s behalf, there must be a method whereby the third party can authenticate themselves to the data attribute provider during subsequent interactions. OAuth 2.0 solves this through the use of a token that is provided by the ASP to the third party at the point at which permission to access an account is granted. The third party then presents the token to the each time it wishes to access the account.

#### 7c. 8.1.3 Further considerations

The Open Banking API should define a method by which users can identify any third party they are interacting with, particularly at the point at which they are granting authorisation, for example, using certificates. There must also be a method by which the data attribute provider may verify that a third party is authorised to receive the permissions it is requesting.

## 7c. 9 Authorisation

### 7c. 9.1 The authorisation process

The OAuth model as it would apply to the Open Banking API is as follows:

In the course of an interaction with the third party, the customer communicates intent to grant the third party access to account information held by a data attribute provider:
1. The third party requests access to the customer’s account information from the data attribute
provider;
2. The data attribute provider authenticates the customer;
3. The data attribute provider reviews whether the third party is authorised to receive the access it is requesting;
4. The data attribute provider displays to the customer the access being requested by the third
party;
5. The customer reviews the access being requested by the third party and authorises the data
attribute provider to grant the requested access to the account information and act on the
customer’s behalf;
6. The data attribute provider grants the third party the requested access.

Steps 5 and 6 must not involve the third party; doing so would provide opportunities for a bad actor to conceal the extent of the access being requested from the customer.

### 7c. 9.2 Responsibilities of the data attribute provider

The data attribute provider must allow the customer to review:

 - pertinent information about the third party (e.g. the company name, location, what level of
authorisation it has received);
 - permissions being requested by the third party; and
 - duration and validity for which the permissions will be granted.

After the fact, data attribute providers must provide an independent mechanism (i.e. without any third party provided software or service) for customers to review the permissions they have granted and revoke any.

Data attribute providers should also maintain the ability to limit, suspend or revoke a third party’s access if they detect suspicious activity or become aware that it is in the customer’s best interests to do so (e.g. if a third party has been removed from the whitelist for failure to maintain required security standards).

It is expected that each data attribute provider will issue its own authorisation tokens. Third parties are expected to securely manage tokens relevant to each data attribute provider. data attribute providers in turn, must ensure that the third party is in possession of legitimate authorisation tokens and that the requested data or service relates to the customer’s legitimate account (i.e. the right customer is accessing the right account via the right third party at the right time). Data attribute providers must ensure that only valid tokens are accepted and that controls are in place to prevent common attack scenarios such as replay, enumeration, denial of service attacks, etc.

### 7c. 9.3 Requirements of the Open Banking API

Open Banking API specifications must clearly define the mechanism (e.g. authorisation tokens) by which:
 - permissions are granted by the data attribute provider to the third party;
 - evidence of authorisation is provided from the third party to the data attribute provider during subsequent API sessions without requiring re-authentication and re-authorisation from the customer (within the time limit of the permissions).

## 7c. 9.4 Permissions and roles

### 7c. 9.4.1 Permissions

*Defining access by specific permissions*

Permissions are the customer’s informed consent for a third party to obtain data stored by the data attribute provider (e.g. an account balance or a list of transactions) or to instruct the data attribute provider to carry out some function (e.g. make a payment or suspend a standing order).

The access granted to third parties should be defined in terms of specific permissions to access data or functionality via the API. Permissions should be mapped to one or more API calls so that, given a specific permission (or set of permissions), it is clear to third parties which API calls may be accessed.

*Assignment of risk levels*

Permissions should be assigned risk levels that reflect the potential impact of malicious misuse of the permission. This applies both to the information being accessed (e.g. sensitive data that could be used for social engineering or identity theft) and the functions being accessed (e.g. setting up new beneficiaries, making high-value payments).

*Prohibitions on granting permissions*

The Open Banking API should allow for the possibility of prohibiting the granting of permissions unless (a) the third party is authorised to receive them, and (b) the channel through which the API is being accessed is approved for the exercise of the permissions in question. The Open Banking API should define rules governing which permissions may be exercised over which channels. An example of such a rule might be that payments cannot be instructed by software running on a user device that does not make use of a trusted execution environment.  Such rules must be enforced by data attribute providers.

*Limitations on permissions*

Where appropriate, it should be possible to apply contextual limits. For example, it should be possible to limit a permission to a specific number of uses (e.g. make no more than three payments, set up one standing order), or limit any permission that can be used to make or instruct payments from an account to a maximum amount and/or maximum amount/period combinations (e.g. £100 limit per day; £1,000 limit during any 30-day period).

*Duration of permissions*

Consideration should be given to permissions being subject to a time/duration limit (with a maximum duration of e.g. one year). Each request by a third party for a permission should adhere to the principle of least privilege and be appropriate to the nature of the data or functionality sought (e.g. a transient interaction versus persistent access over a long period). It may be expedient to draft some guidelines that define what is appropriate. The customer must be able to override the duration (if any) requested by the third party, both at the time permission is granted and at any point subsequently.

*Permissions and authorisation*

The data attribute provider must ensure that no permissions are granted to a third party without first being displayed to and authorised by the customer. The customer must have the opportunity to opt not to grant the third party any or all of the permissions being requested, or to apply relevant limits to any permission (the data attribute provider may opt to apply default limits but these should not be overly restrictive).

*Permissions and data protection*

In accordance with the data protection principles, third parties should not retain data they have obtained by dint of a permission that has expired (or been withdrawn) for longer than is appropriate.

### 7c. 9.4.2 Roles

The Open Banking Framework should define a number of common role profiles, under which
collections of permissions may be requested by third parties. Common profiles should cover core use cases for specific user types (e.g. accountant, financial adviser, power of attorney). Data attribute providers should provide support for the roles that are appropriate to the type of account the customer holds. This will enhance the usability of the API, by simplifying the mechanism for requesting and granting permissions.

Any divergence from industry norms for the common role permissions must be highlighted explicitly prior to permissions being granted.

### 7c. 9.4.3 Future consideration of centralised permissions management

The case for creating a central repository of permissions that users have granted to third parties (e.g. an aggregated view of “permissions dashboards”) is unclear at this stage. There are benefits as well as risks.

 - Benefit: giving customers a single view of their permissions “dashboard” (the permissions
they have granted across multiple organisation).
 - Risks: concentrating information for accounts that have profiles attractive to fraudsters in a single repository makes them a high-value target; there may be possible privacy issues; the
cost of implementation may be high.

Future phases of work may want to undertake a more detailed evaluation on creating a central
permissions repository.

### 7c. 9.5 Encryption

The Fingleton Report recommended the use of HTTP Strict Transport Security (to ensure that API
connections should only be made using HTTPS, thus ensuring that all data in transit is encrypted), and Perfect Forward Secrecy (to minimise the impact if session keys are compromised). This report supports this recommendation and further suggests that the specification mandates the use of TLS v1.2 as a minimum, with a defined set of strong cipher suites.

The case for message-level encryption is less straightforward. Existing bank apps and websites do not use message-level encryption, so mandating its use would go beyond current industry norms. It may also require significant changes to existing technology architecture deployed by many banks.

Unless stakeholders (data attribute providers in particular) indicate a strong preference for its inclusion, it is suggested that message-level encryption should not form part of the Open Banking API at this time. However, its inclusion should be considered in the future if the security threat environment changes significantly and/or its use becomes more widespread.
Similarly, the case for including provision for (or mandating the use of) message authentication codes in the Open Banking API should be assessed during the next phase, in consultation with data attribute providers and third parties.

## 7c. 10. Whitelisting

7c. 10.1 Whitelisting and its limitations
Where access to the’ data attribute providers’ API occurs from a server end-point controlled by the third party), whitelisting may be enforced through the use of cryptographic certificates, with a high degree of confidence provided by the fact that the secret key is protected by the security surrounding the server (and, optionally, by a hardware security module).

For client-side app use cases, the application software is likely to be running on the customer’s hardware, which must be assumed to be insecure. As a result, a cryptographic certificate is not practicable, as the secret key is subject to compromise. To support innovation, further exploration should be made into whether the API specification should allow data attribute providers the option to grant API access to a customer (as opposed to a third party) to use software or a service they have developed themselves.

### 7c. 10.2 Authentication certification

The use of digital certificates is recommended for third party authentication, and to certify that the third party has been to access customer data via the API.

### 7c. 10.3 Secure coding

Both third parties and data attribute providers should be required to adopt measures to minimise the risk of security deficiencies in any software they deploy to provide or consume API data. Measures may include adoption of a secure software development lifecycle methodology (e.g. OpenSAMM, Security Development Lifecycle), penetration testing, fuzzing, or source code review. The stringency of the measures required should be commensurate with the nature of the data/functionality being served or consumed.

The case for requiring that testing or review be carried out by independent specialists should be explored further in the next stage of work.

### 7c. 10.4 Information sharing and incident handling

It should be the responsibility of all participants in the API ecosystem to share any information on fraud security threats. Information-sharing mechanisms may already exist but will need to be expanded to incorporate the wider ecosystem. It is noted that Financial Fraud Action UK (FFA UK) has made proposals to provide a mechanism for firms to share information on security breaches, etc.

Data attribute providers should provide a channel for third parties to report any defects or bugs with security implications, adopt formal procedures for acknowledging and investigating such reports, addressing any security vulnerabilities discovered. In addition to existing statutory requirements, it is recommended that third parties and data attribute providers be required to report any security breaches that affect API data or functionality, to both the Independent Authority, and to any customers affected. In the case of a third party suffering a security breach that affects API data obtained from a data attribute provider, the data attribute provider should also be notified.

Protocols should be put in place to facilitate the exchange of information between third parties and data attribute providers in support of investigation of potential fraud or security breaches.

### 7c. 10.5 Auditing

It is expected that detailed audit logs will need to be maintained by data attribute providers and third parties to facilitate investigations. Further work to define the parameters of these logs will be required in the next phase.

## 7c. 11. Approach to Open Data

By definition, there is no reason to restrict access to truly open data. Therefore, there is no need to prevent unauthorised access to open data (although there may be a need to restrict access for other reasons, such as preventing denial of service (DOS) attacks). If open data is to be accessed via the same API that provides access to customers’ accounts, provision must be made for a level of access that does not require authentication (permission level zero, as opposed to no authentication).

There may be a need to protect the integrity of open data and prevent alteration of open data by bad actors. Therefore, the infrastructure used to provide access to open data should be secured to prevent unauthorised alteration. Authentication of the source of the data may also be required.

Finally, if personal data is anonymised in order to facilitate its publication as open data, care must be taken to ensure that the steps taken to anonymise it preclude de-anonymisation (including through the combination of multiple open data sets). There is more discussion in chapter 9.
