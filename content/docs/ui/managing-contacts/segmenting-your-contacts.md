---
layout: page
weight: 70
title: Segmenting your Contacts
group: managing-contacts
navigation:
  show: true
seo:
  title: Segmenting your Contacts
  keywords: Segmentation, email segmentation, targeted marketing, email, marketing campaigns
  override: true
  description:
---

<iframe src="https://player.vimeo.com/video/385360784" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

<call-out type="warning">

The content on this page describes the experience in the latest version of Marketing Campaigns. If you’re using the legacy version of Marketing Campaigns, your experience may be different. To explore Marketing Campaigns plans and upgrade, click [here](https://sendgrid.com/pricing).

</call-out>

[Segments]({{root_url}}/glossary/segmentation/) are similar to contact lists, except they update dynamically over time as information stored about your contacts changes. When you segment your audience, you are able to create personalized Automation emails and Single Sends that directly address the wants and needs of your particular audience.

[Custom fields]({{root_url}}/ui/managing-contacts/custom-fields/), [reserved fields]({{root_url}}/glossary/reserved-fields/), and engagement data like opens and clicks, provide unique information you can use to identify contacts for different segments. As your contacts' traits change and you add more contacts that meet the criteria of your segment, your segments will update to reflect these changes. For example, a segment populated using the criteria, “lives in Denver” or, “is under 30 years old” will change as your contacts age and their addresses change.

Segments can pull from _All Contacts_ or any of your more narrowly defined lists.

## How segments work

Segments are created by comparing your contacts against criteria you define. If a contact matches the specified criteria, they will be included in your segment. Engagement data such as "opened" or "clicked" will add contacts who have _engaged_ in this behavior with one of your messages. Whether or not a contact meets your defined criteria is evaluated using expressions that consist of three parts: fields, operators, and values.

The first part of the pattern, the field, is the data _field_ you want to filter your contacts by. Fields include traits such as "First Name," "Email," or "City, " and engagement data such as "Last Clicked." For a full list of available fields, see the [Segmentation fields and types tables](#segmentation-fields-and-types).

Operators are the second part of the expression, and they define how your contacts should be evaluated. All fields have a data type assigned to them (text, number, date, Single Send); this type will determine which operators are available. For example, "Last Clicked" is a date field, and it has date operators such as "is after" and "is before" available. For a full list of operators available by field type, see the [Operators available by field type section](#operators-available-by-field-type).

The last part of the expression is a value. The value is compared to the field using the operator. For example, you may select the field, "City." City is a text-type field, so you can then choose "is" from the available operators for that field type. You can then add the value, "Denver." This expression will check your contacts for entries who live in Denver and include all who do in your segment.

You can build precisely targeted segments by using multiple conditions to filter your contacts. The previous example is among the simplest segments possible using Marketing Campaigns.

## Creating a segment with the SendGrid App

To create a segment, login to the Twilio SendGrid App, and complete the following steps.

1. Navigate to [**Marketing** and then select **Contacts**](https://mc.sendgrid.com/contacts).
2. Click on the **Create** dropdown button, and then the **New Segment** option.

![The SendGrid App with the Create dropdown extended and "New Segment" highlighted in the dropdown.]({{root_url}}/img/new_segment_dropdown.png 'Create dropdown')

3. Enter a _Segment Name_.
4. Choose **Segment all contacts** or **Segment an existing list**.

![The contacts menu inside the SendGrid App, displaying the segment name field and list from which a the segment should be built.]({{root_url}}/img/create_new_segment.png 'Create a new segment')

<call-out>

If you're segmenting an existing list, you can click the action menu to the right of the list name and select "Create Segment" directly.

</call-out>

5. To segment an existing list, select a list from the **Existing List** drop-down.
6. In the **Who are you targeting?** section, start building your condition by choosing a _field_ from the drop-down.
7. Choose from the list of available _operators_.
8. Enter the desired _value_ you want to segment by.
9. You can add multiple conditions and choose to join them with **AND** or **OR**. This functionality allows you to further refine your segments to target your audience with precision.
10. Once you are finished adding conditions, click **Save Segment**.

![The contacts menu inside the SendGrid App, displaying a new segment with a City condition set to "Denver" and a State, Province, Region condition set to "Colorado".]({{root_url}}/img/create_new_segment_two_fields.png 'Create a new segment with two fields')

<call-out type="warning">

Segments built using engagement data such as "was sent" or "clicked" will take approximately 30 minutes to begin populating.

</call-out>

## Segmentation fields and types

The following tables list the available fields, excluding custom fields that you set, and the fields' data types. The operators available for each type are included in the section following the tables.

### Contact Profile fields

<table class="table auto">
  <tr>
    <th>Field Name</th>
    <th>Field Type</th>
  </tr>
  <tr>
    <td>First Name</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Last Name</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Email</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Address Line 1</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Address Line 2</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>City</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>State Province Region</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Postal Code</td>
    <td>Text</td>
  </tr>
  <tr>
    <td>Country</td>
    <td>Text</td>
  </tr>
 <tr>
    <td>Date Added</td>
    <td>Date</td>
  </tr>
  <tr>
    <td>Last Updated</td>
    <td>Date</td>
  </tr>
</table>

### Email Activity fields

<table>
  <tr>
    <th>Field Name</a></th>
    <th>Field Type</a></th>
  </tr>
  <tr>
    <td>Last Clicked</td>
    <td>Date</td>
  </tr>
 <tr>
    <td>Last Opened</td>
    <td>Date</td>
  </tr>
  <tr>
    <td>Last Emailed</td>
    <td>Date</td>
  </tr>
</table>

### Single Send fields

<table>
  <tr>
    <th>Field Name</a></th>
    <th>Field Type</a></th>
  </tr>
  <tr>
    <td>Single Send Activity</td>
    <td>Single Send*</td>
  </tr>
</table>

\* Single Send Activity fields have their own Single Send type. The operators available for a Single Send ("was sent," "opened," and "clicked") behave like [Email Activity fields](#email-activity-fields), but they are scoped to engagement on Single Sends.

### Operators available by field type

The operators available on a field depend on the field type (Text, Date, Number, or Single Send).

Operators available on a “Date” field include:

- `is`
- `is not`
- `is blank`
- `is not blank`
- `is after`
- `is at or after`
- `is before`
- `is at or before`
- `starts with`
- `on`
- `not on`
- `is between`
- `is not between`
- `is within`
- `is not within`

Operators available on a "Number” field include:

- `is`
- `is not`
- `is blank`
- `is not blank`
- `is greater than`
- `is less than`
- `is equal or greater than`
- `is equal or less than`
- `is between`
- `is not between`

Operators available on a “Text” field include:

- `is`
- `is not`
- `is blank`
- `is not blank`
- `contains`
- `does not contain`
- `starts with`
- `does not start with`
- `ends with`
- `does not end with`

Operators available on a “Single Send” field include:

- `was sent`
- `has clicked`
- `has opened`

When using more than one condition to segment your contacts, you can select `AND` or `OR` as options, where `AND` requires both conditions to be true and `OR` requires either condition to be true. Once you’ve selected the field, operator, and value, you can layer additional conditions in the segment to narrow the results to a more targeted audience.

## Duplicating a Segment

Duplicating a segment eliminates the time and effort needed to recreate a complex segment from scratch in order to make a few changes or tweaks to reach a different audience. Follow these steps to create a copy of an existing segment.

_To duplicate a segment:_

1. From the Contact Lists page, click the Action Menu next to the name of the segment you wish to duplicate.
1. Select **Duplicate**.

## Exporting a Segment

_To export a segment from the Contact List Page:_

1. Click the Action Menu next to the name of the segment you wish to export.
1. Select **Export**.

![]({{root_url}}/img/duplicate-segment-contact-list-page.png "Duplicate a segment from the contact list page")

_To export a segment from the segment details page:_

1. Click **Segment Options** to open the drop-down menu.
1. Select **Duplicate**.

![]({{root_url}}/img/duplicate-segment-details-page.png "Duplicate a segment from the segment detail page")

This triggers SendGrid to send an email to the primary email address on the account. The email includes a link to download the CSV of all the contacts in the list and their associated custom field values.

<call-out>

The download link for your CSV export will be valid for 24 hours.

</call-out>

## Additional Resources

- [Contacts]({{root_url}}/ui/managing-contacts/adding-contacts/)
- [Custom Fields]({{root_url}}/ui/managing-contacts/custom-fields/)
- [Tips on Segmenting Your Active Subscribers](https://sendgrid.com/blog/tips-on-segmenting-your-active-subscribers/)
