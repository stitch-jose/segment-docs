---
title: Ironclad (Actions) Destination
hide-boilerplate: true
hide-dossier: true
hidden: true
private: true
id: 
---


{% include content/plan-grid.md name="actions" %}

<!-- Include a brief description of the destination here, along with a link to your website. -->
[Ironclad](https://ironcladapp.com/product/clickwrap/){:target="_blank"} Ironclad Clickwrap is the fastest, easiest way to gather a legally binding digital acceptance, helping forward-thinking companies manage high-volume contracts like terms & conditions, NDAs, and more. Limit risk and provide a seamless experience? Win.

Ironclad maintains this destination. Contact [support@ironcladhq.com](mailto:support@ironcladhq.com) with any questions.

<!-- This include describes the requirement of A.js 2.0 or higher for Actions compatibility, and is required if your destination has a web component. -->

{% include content/ajs-upgrade.md %}

<!-- In the section below, explain the value of this actions-based destination. If you don't have a classic version of the destination, remove this section. -->

## Benefits of Ironclad Clickwrap (Actions)

Ironclad (Actions) provides the following benefits:

- **Compliance that’s setup without code** - Configure a simple set of options to start tracking acceptance of clickwrap agreements in Ironclad Clickwrap. Don’t know what a clickwrap agreement is? [Check out our website.](https://ironcladapp.com/product/clickwrap/)
- **Control what data is tracked** - Easily map data that Segment receives from your sources, and send the right data to form an enforceable contract in Ironclad.
- **Connect key user activities to events legal needs for enforceability** - Configure existing events to comply with what your legal team needs to enable you to keep doing business online.


<!-- The section below explains how to enable and configure the destination. Include any configuration steps not captured below. For example, obtaining an API key from your platform and any configuration steps required to connect to the destination. -->

## Getting started

1. From the Segment web app, navigate to **Connections > Catalog > Destinations**.
2. Click the **Destination Actions** category item in the left navigation.
3. Search for **Ironclad (Actions)** and select it.
4. Click **Configure Ironclad (Actions)**.
5. Select an existing Source to connect to Ironclad (Actions).
6. Set your Site Access Id. 

<!-- The line below renders a table of connection settings (if applicable), Pre-built Mappings, and available actions. -->

{% include components/actions-fields.html %}

<!--
Additional Context

Include additional information that you think will be useful to the user here. For information that is specific to an individual mapping, please add that as a comment so that the Segment docs team can include it in the auto-generated content for that mapping.
-->

## Get your Site Access Id
On the Settings page, you see a pane for Account Settings and one for Site Settings. In the Site Settings section is a really important value: the Site's Access ID (or write key). The Access ID is unique for each Site within your account and is used to render your Contracts on your website, apps, and other digital surfaces. It is used in your API calls to Ironclad and helps us identify your unique Site across our entire cloud-based infrastructure. It is a GUID.

**Tip:** If you need the Access ID for a different Site in your account, you need to switch to that Site and find it in the Account Settings there. Use the Change Site button (crossing arrows) near the bottom of the navigation bar on the left side of the screen to sign in to a different Site.
 

To get your Site Access Id:
1. Log in to Ironclad.
2. Click the Profile & Settings button at the bottom of the navigation menu on the left (usually contains your photo or your initials).
3. Click **Settings** from the menu that appears. 
4. Under the site settings pane, you will find **Access Id**.

## Ironclad mappings and definitions

Once the Ironclad (Actions) Site Access Id is configured, you're ready to finish the rest of the mappings:

1. **Signer ID**:
    1. Type: `String`
    2. Description: The unique identifier used to save your signer’s signature. Can be email, mobile number, UUID, or any integer or string. Should be URL encoded
    3. Mapping: Automatically mapped to `userId` field, if `userId` doesn't exist then its mapped to the `anonymousId` field.
    4. Required: Yes
2. **Event Name**:
    1. Type: `String`
    2. Description: The name of the event coming from the source, this is an additional information field before the call goes to Ironclad
    3. Mapping: Automatically mapped to `event` field
    4. Required: Yes
3. **Group Id**:
    1. Type: `String`
    2. Description: The ID of the Group associated with the acceptance event. You can find your Clickwrap Group ID by clicking into a Clickwrap Group in Ironclad and getting the ID from the URL (e.g. clickwrap.pactsafe.com/groups/1235)
    3. Mapping: Manual input
    4. Required: Yes
3. **Event Type**:
    1. Type: `Select`
    2. Description: The type of event being logged, the available choices are displayed, agreed, and disagreed.
    3. Mapping: Manual input
    4. Required: Yes
4. **Context Parameters**:
    1. Type: `Object`
    2. Description: Context Parameters including page, time and other information.
    3. Mappings: 
        `addr`: IP address mapped by default to the `ip` field,
        `ts`: Timestamp field mapped by default to the `timestamp` field,
        `pat`: Page title field mapped by default to the `context.page.title` field,
        `pau`: Page URL field mapped by default to the `context.page.url` field,
        `pap`: Page path field mapped by default to the `context.page.path` field,
        `paq`: Page search field mapped by default to the `context.page.search` field,
        `ref`: Page referrer field mapped by default to the `context.page.referrer` field,
        `btz`: Browser timezone field mapped by default to the `context.timezone` field,
        `bl`: Locale field mapped by default to the `context.locale` field,
        `os`: Operating system name field mapped by default to the `context.os.name`,
        `res`: Screen resolution field mapped by default to the `context.screen` json object,
    4. Required: No
4. **Custom Data**:
    1. Type: `Object`
    2. Description: Optional. Allows you to append key/value pairs of data to your Clickwrap events. URL encode a JSON object to attach custom data to your Activity. The example is URL encoded for { "first name": "Eric" }. Using this in an “updated” Event Type for Clickwrap will append the data to the Signer, otherwise it will be added to the specific Activity call/transaction.
    3. Mappings: 
        `first_name`: Firstname field mapped by default to the `custom_data.first_name` field,
        `last_name`: Lastname field mapped by default to the `custom_data.last_name` field,
        `company_name`: Company name field mapped by default to the `custom_data.company_name` field,
        `title`: Signer title field mapped by default to the `custom_data.title` field,
        `customer_id`: Customer id field mapped by default to the `custom_data.customer_id` field
    4. Required: No

