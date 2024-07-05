%%%
title = "Structured Email: Use cases"
area = "ART"
workgroup = "SML"

[seriesInfo]
name = "Internet-Draft"
value = "draft-ietf-sml-structured-email-use-cases-00"
stream = "IETF"
status = "informational"

[[author]]
initials = "H.-J."
surname = "Happel"
fullname = "Hans-Joerg Happel"
organization = "audriga GmbH"
  [author.address]
   email = "happel@audriga.com"
   uri = "https://www.audriga.com"

%%%

.# Abstract 

This document collects and discusses use cases for "structured email" ([I-D.happel-structured-email-00]).

{mainmatter}

# Introduction

This document is currently structured in the following sections:

* Existing use cases, which are already in use by vendors.
* Sharing use cases, which relate to sharing functions of other communication tools such as social networks and instant messaging tools.
* Transactional use cases, which address (semi-)formal interactions carried out via email messages.
* Email-specific use cases that are specfic to the email domain as such.

A final section points to related use cases which are addressed by particular RFCs.

# Conventions Used in This Document

The terms "message" and "email message" refer to "electronic mail messages" or "emails" as specified in [@RFC5322]. The term "Message User Agent" (MUA) denotes an email client application as per [@RFC5598].

The terms "machine-readable data" and "structured data" are used in contrast to "human-readable" messages and denote information expressed "in a structured format (..) which can be consumed by another program using consistent processing logic" [@MachineReadable].

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in BCP 14 [@RFC2119] [@RFC8174] when, and only when, they appear in all capitals, as shown here.

# Existing use cases

The following use cases are currently supported by one or more of the email providers which support [@SchemaOrg] in email (see also [@StructuredEmail]).

## Orders and invoices

Related to the general topic of online shopping, the [@SchemaOrg] types "Order", "Invoice", and "ParcelDelivery" can be used throughout the purchasing lifecycle.

## Promotions

Some vendors support arrays of structured data which are aggregated to show promotional offers to end users.

These arrays contain a set of products (images), a discount or coupon code and vendor information.

## Reservations

Various types of reservations can be processed by some email providers and tools. These include types for transport (Bus-, CarRental-, Flight-, and TrainReservation), HotelReservation, RestaurantReservation and a generic EventReservation type.

# Sharing use cases

## Geolocation

Location sharing is common action supported by many instant messaging tools. The current best practice to share locations in email messages would probably be to share URLs/deep links to online map services.

## Media

Media and content such as news articles, books, cooking recipes, films, or music albums are commonly shared by users. Many websites contain corresponding "share buttons". The particular "share by email" feature either launches an email send form or a MUA using a "mailto:" ([@RFC6068]) URL.

In both cases, email messages will typically contain a plain website URL pointing to the shared media item. The recipient needs to switch from her MUA to the web browser and find out manually, what kind of content has been shared.

## Newsletters

Newsletters can be considered as a special conduit for sharing information between a newsletter editor and a larger audience.

They often feature media and content or products. Structured data might ease the further sharing or processing of individual pieces of information.

## Products and services

Similar to media and content, users may share or recommend certain products and services, which may result in a later purchase or reservation (see first section).

## Public events

While (corporate) meeting scheduling is a common use case based on email (see Message Scheduling below), public events are not supported similarly well.

There are efforts to extend the current event data model for this use case ([@RFC9073]), which allow to embed [@SchemaOrg] into calendar data. Structured email might complement and improve this use case.

# Transactional use cases

## Formal interaction

Email messages are often used for formal requests sent to government organizations or business. 

Users may intiate such requests by composing a free-form email message in their MUA or use a so-called "contact form" on a website, which in many cases will generate an email based on the form's content. 

Such contact forms are however a major source of email abuse, since the recipient will technically send an email to itself, based on whatever data was entered into the form.

Structured email could provide means which make such formal contact more efficient and trustworthy.

## Mail-in-APIs

Various tools such as ticket systems or mailinglist management software allow for controled vocabulary (such as "UNSUBSCRIBE") in reply messages to trigger certain functionality.

Structured email could help to formalize and improve such use cases, so that they allow for easier interaction.

## Multi-factor authentication

Email is often used as an additional "factor" in multi-factor authentication. Services will send a message to the pre-registered address which users will need to confirm in order to complete a log-in process or similar transactions.

Such messages will typically contain a code and/or a link (URL) to a website.

## Sign-up messages

Email is a major form of digital communication with third parties and services they offer. The beginning of such interaction is often some form of "sign-up" or "welcome" message.

Structured data could allow MUAs and downstream tools to help users keep track and manage services they have subscribed to.

## Status notifications

Various software systems use email message to notify users about certain updates and status changes. In many cases, users may want to respond with a comment, confirmation, or similar actions.

These kind of actions currently involve URLs, which often results in a web browser launched out of the MUA. Structured email could help provide a more seamless and direct user interaction in those cases.

# Email-specific use cases

This section presents a number of use cases which are specfic to the email domain as such and/or relate to core features of MUAs.

## MUA configuration

Mobile devices can allow special messages for over-the-air (OTA) configuration updates. In a similar fashion, structured email could be used for (re-)configuring MUA settings.

## Reactions

Social networks and instant messaging tools allow for various forms of low-level instant reactions, such as "liking", "thumbs up", "heart", or "smiley".

A simple variant for usage in email messages has been proposed in [@RFC9078]. Some vendors have also implemented similar solutions, which are however mainly designed for usage within the vendor's own platform ([@OutlookReactions], [@GmailReactions]).

## Structured email signature

Email signatures are a commonly used feature of MUAs which allow users to append contact details or information about upcoming events to email messages. They may also be a legal obligation in some settings.

There are no standards for such signatures beyond the separator "-- " used in text/plain body parts, which stems from Usenet practice [@RFC3676]. With a similar intention, some MUAs allow to append vCard ([@RFC6350]) files to outgoing messages.

## Structured vacation notice

So called "vacation notices" or "out-of-office replies" are automated messages which are sent in response to incoming messages if a recipient is absent or otherwise unable to respond.

Those messages typically include instructions for the sender (when to retry or whom to contact instead). MUAs can currently hardly assist in dealing with such messages, as they are mainly based on human-language.

# Use cases specified by RFCs

Specific structured formats for email messages have been employed for a number of specific use cases in the past. Semantics and interactions of these messages have been captured in individual RFCS

## Message scheduling
<a name="#MessageScheduling"></a>

Message scheduling is probably the most widely use form of interaction with email messages, which is not mainly based on writing text.

Due to the iCalendar Message-Based Interoperability Protocol (iMIP; [RFC6047), certain well-defined messages can be sent between calendaring software in order to deal with meeting invitations.

While mainly focused on private/business meetings, the use case of public events is less well supported in these workflows (see also discussion above).

# Security considerations

None to date.

# Privacy considerations

None to date.

# IANA Considerations

This document has no IANA actions at this time.

{backmatter}

<reference anchor="SchemaOrg" target="https://schema.org/">
   <front>
      <title>Schema.org</title>
      <author>
        <organization>W3C Schema.org Community Group</organization>
      </author>
      <date>2023</date>
   </front>
</reference>

<reference anchor="StructuredEmail" target="https://structured.email/content/related_work/frameworks/schema_org_for_email.html">
   <front>
      <title>Structured.email: Schema.org for Email</title>
      <author>
        <organization>Structured.email</organization>
      </author>
      <date>2023</date>
   </front>
</reference>


<reference anchor="GmailReactions" target="https://support.google.com/mail/answer/14080429?hl=en">
   <front>
      <title>Reply to emails with emoji reactions</title>
      <author>
        <organization>Google</organization>
      </author>
      <date>2023</date>
   </front>
</reference>

<reference anchor="OutlookReactions" target="https://support.microsoft.com/en-us/office/reactions-in-microsoft-outlook-06315501-a790-4a2a-90c1-fbc89d84c393">
   <front>
      <title>Reactions in Microsoft Outlook</title>
      <author>
        <organization>Microsoft</organization>
      </author>
      <date>2023</date>
   </front>
</reference>


<reference anchor="MachineReadable" target="https://csrc.nist.gov/glossary/term/Machine_Readable">
   <front>
      <title>NIST IR 7511 Rev. 4</title>
      <author>
        <organization>NIST</organization>
      </author>
      <date>2016</date>
   </front>
</reference>
