---
title: Set Up Marketing Highlights
description: Learn how to connect Marketo to Adobe Marketo Qualifier so representatives can view and filter prospects by live Marketo activity in Marketing Highlights.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
subfeature_v2:
  - id: 7b0925d9-0dc0-5c75-a54d-2bcc31c6ebe4
    internal-label: Marketing highlights
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
---

# Set up Marketing Highlights

Marketing Highlights shows each prospect's live [!DNL Marketo] activity, such as email opens and clicks, web visits, and form fills. This article explains how to connect your [!DNL Marketo] instance so that activity flows in.

>[!IMPORTANT]
>
>Completing this setup requires access to the Adobe Developer Console and to **[!UICONTROL Admin]** in [!DNL Marketo]. Work with your Adobe contact and your [!DNL Marketo] administrator to complete the four parts below.

Setup has four parts:

* Part A: Create API credentials in the Adobe Developer Console.
* Part B: Gather your Adobe Marketo Qualifier endpoint and identifiers.
* Part C: Configure a webhook in [!DNL Marketo Engage].
* Part D: Add the webhook to a trigger Smart Campaign.

After setup is complete, users see and filter this activity on **[!UICONTROL Prospects]** > **[!UICONTROL Marketing Highlights]**.

## Part A: Create API credentials {#part-a-create-api-credentials}

These credentials let [!DNL Marketo] authenticate securely to Marketo Qualifier.

To create the credentials:

1. Go to [Adobe Developer Console](https://developer.adobe.com/console/) and sign in with your Adobe ID.
1. Select **[!UICONTROL Create new project]**, or open an existing project.
1. To rename the project, select **[!UICONTROL Edit project]**, enter an identifiable name such as `Marketo Qualifier Marketing Highlights`, and select **[!UICONTROL Save]**.
1. Select **[!UICONTROL Add API]**, select **[!UICONTROL Experience Platform API]**, then select **[!UICONTROL Next]**.
1. Choose **[!UICONTROL OAuth Server-to-Server]** as the authentication type, then select **[!UICONTROL Next]**.

   **[!UICONTROL OAuth Server-to-Server]** lets [!DNL Marketo] call the Marketo Qualifier API directly from its server, without requiring a person to sign in.

1. Enter a credential name of 45 characters or fewer, such as `Marketo Qualifier Marketing Highlights Creds`.
1. To associate the product profile, select it, then select **[!UICONTROL Save configured API]**.
1. Under **[!UICONTROL Connected credentials]**, open the **[!UICONTROL OAuth Server-to-Server]** credential. Select **[!UICONTROL Retrieve client secret]**, then copy the **[!UICONTROL Client ID]** and **[!UICONTROL Client Secret]**. You use these values in [Part C](#part-c-configure-the-marketo-webhook).

>[!WARNING]
>
>Keep the Client Secret private. Treat it like a password, and do not send it by email. Use your organization's approved secure channel to share it with whoever configures the webhook.

## Part B: Gather your endpoint and identifiers {#part-b-gather-your-endpoint-and-identifiers}

You need three values for [Part C](#part-c-configure-the-marketo-webhook):

* **Endpoint URL**—The Marketo Qualifier webhook address for your region.
* **imsOrg ID**—Your organization's identifier in the Adobe Identity Management System (IMS), in the form `{ORG_ID}@AdobeOrg`.
* **Sandbox name**—The name of your AEP sandbox exactly as it appears in the Marketo Qualifier URL (the `sname` value), not the display name shown in the UI. Use the lowercase URL value, for example `prod`, not `Prod`.

| Region | Webhook endpoint URL |
| --- | --- |
| North America | `https://5r6xakp9k3.execute-api.us-east-1.amazonaws.com/prod/external/marketo/signals` |
| EMEA | `https://pc72i8q1k3.execute-api.eu-west-1.amazonaws.com/prod/external/marketo/signals` |
| APAC / Australia | `https://5cxxxyqlai.execute-api.ap-southeast-2.amazonaws.com/prod/external/marketo/signals` |

{style="table-layout:auto"}

If you are unsure of your region, imsOrg ID, or sandbox name, your Adobe contact can confirm them.

## Part C: Configure the Marketo webhook {#part-c-configure-the-marketo-webhook}

To create the webhook:

1. In [!DNL Marketo], select **[!UICONTROL Admin]** > **[!UICONTROL Webhooks]**.
1. Select **[!UICONTROL New Webhook]**.
1. Set **[!UICONTROL URL]** to the endpoint URL for your region from [Part B](#part-b-gather-your-endpoint-and-identifiers).
1. Set **[!UICONTROL Request Type]** to `POST`.
1. Set **[!UICONTROL Request Token Encoding]** to `JSON`. This setting is required.
1. Paste the payload template below into **[!UICONTROL Template]**. Use [!DNL Marketo]'s **[!UICONTROL Insert Token]** to match the field names in your instance.

   >[!NOTE]
   >
   >With JSON encoding, do not wrap string tokens in quotation marks. [!DNL Marketo] adds them automatically.

   ```json
   {
     "leadId": {{lead.Id:default=0}},
     "email": {{lead.Email Address:default=}},
     "fullName": {{lead.Full Name:default=}},
     "company": {{company.Company Name:default=}},
     "title": {{lead.Job Title:default=}},
     "department": {{lead.Department:default=}},
     "country": {{lead.Country:default=}},
     "score": {{lead.Lead Score:default=0}},
     "rating": {{lead.Lead Rating:default=}},
     "leadStatus": {{lead.Lead Status:default=}},
     "leadSource": {{lead.Lead Source:default=}},
     "isCustomer": {{lead.Is Customer:default=false}},
     "industry": {{company.Industry:default=}},
     "annualRevenue": {{company.Annual Revenue:default=0}},
     "numEmployees": {{company.Num Employees:default=0}},
     "campaignId": {{campaign.id:default=0}},
     "campaignName": {{campaign.name:default=}},
     "programName": {{program.name:default=}},
     "occurredAt": {{system.dateTime:default=}},
     "munchkinId": {{system.munchkinId:default=}},
     "triggerName": {{trigger.Trigger Name:default=}},
     "crmId": {{lead.SFDC ID:default=}},
     "crmType": {{lead.SFDC Type:default=}},
     "crmOwnerEmail": {{lead.Lead Owner Email Address:default=}},
     "crmOwnerFirstName": {{lead.Lead Owner First Name:default=}},
     "crmOwnerLastName": {{lead.Lead Owner Last Name:default=}},
     "attributes": {
       "asset": {{trigger.Name:default=}},
       "link": {{trigger.Link:default=}},
       "subject": {{trigger.Subject:default=}},
       "webPage": {{trigger.Web Page:default=}},
       "category": {{trigger.Category:default=}},
       "details": {{trigger.Details:default=}},
       "sentBy": {{trigger.Sent By:default=}},
       "receivedBy": {{trigger.Received By:default=}},
       "referrer": {{trigger.Referrer:default=}},
       "searchEngine": {{trigger.Search Engine:default=}},
       "searchQuery": {{trigger.Search Query:default=}},
       "imDescription": {{lead.Last Interesting Moment Desc:default=}},
       "imType": {{lead.Last Interesting Moment Type:default=}},
       "imDate": {{lead.Last Interesting Moment Date:default=}},
       "imSource": {{lead.Last Interesting Moment Source:default=}},
       "chatAgentName": {{trigger.Agent Name:default=}},
       "chatAgentEmail": {{trigger.Agent Email:default=}},
       "chatConversationStatus": {{trigger.Conversation Status:default=}},
       "chatConversationSummary": {{trigger.Conversation Summary:default=}},
       "chatGoalName": {{trigger.Goal name:default=}},
       "chatMeetingStatus": {{trigger.meeting status:default=}},
       "chatScheduledFor": {{trigger.Scheduled For:default=}},
       "chatDocumentName": {{trigger.Document Name:default=}},
       "chatDocumentUrl": {{trigger.Document URL:default=}},
       "chatPageUrl": {{trigger.Page URL:default=}}
     }
   }
   ```

1. Select **[!UICONTROL Webhook Actions]** > **[!UICONTROL Set Custom Header]**, then add the following headers, using the values from [Part A](#part-a-create-api-credentials) and [Part B](#part-b-gather-your-endpoint-and-identifiers):

   | Header | Value |
   | --- | --- |
   | `Content-Type` | `application/json` |
   | `x-client-id` | Your Client ID |
   | `x-client-secret` | Your Client Secret |
   | `x-gw-ims-org-id` | Your imsOrg ID |
   | `x-sandbox-name` | Your sandbox name |

   {style="table-layout:auto"}

1. Select **[!UICONTROL Save]**.

## Part D: Add the webhook to a trigger Smart Campaign {#part-d-add-the-webhook-to-a-trigger-smart-campaign}

Add a **[!UICONTROL Call Webhook]** flow step to a trigger Smart Campaign, either an existing one or a new one. The Smart List triggers on that campaign decide which activities are sent to Marketo Qualifier.

To add the webhook:

1. Open an existing trigger Smart Campaign, or create a new one (**[!UICONTROL Marketing Activities]** > **[!UICONTROL New]** > **[!UICONTROL Smart Campaign]**).
1. On the **[!UICONTROL Smart List]** tab, add the trigger or triggers for the activities you want to send, for example **[!UICONTROL Clicks Link in Email]**, **[!UICONTROL Fills Out Form]**, or **[!UICONTROL Visits Web Page]**.
1. On the **[!UICONTROL Flow]** tab, add a **[!UICONTROL Call Webhook]** step and select the webhook you created in [Part C](#part-c-configure-the-marketo-webhook).
1. Activate the Smart Campaign.

Activity from that Smart Campaign now flows into Marketo Qualifier. Representatives see and filter this activity on **[!UICONTROL Prospects]** > **[!UICONTROL Marketing Highlights]**.

>[!MORELIKETHIS]
>
>* [Manage integrations](integrations.md)
>* [Prospects](prospects.md)
>* [Get started](getting-started.md)
