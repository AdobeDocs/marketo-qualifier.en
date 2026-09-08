---
title: Prospects in Sales Qualifier
description: Learn how to build your prospect list from CRM, imported, and manually added sources, filter prospects, and review prospect details in Sales Qualifier.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/zf2H5rq1JlIT26LqLPMrm2Mq3tSIrLOiTEw6BXb1w2U'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
    internal-label: Integrations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---

# Prospects

Select **[!UICONTROL Prospects]** in the left navigation to view the leads and contacts that you can access. Use the list to review each prospect's status and latest activity.

![Prospects table displaying lead status and last activity for prospect management](./assets/prospects.png){width="800" zoomable="yes"}

* **[!UICONTROL Leads]**—Leads assigned to you in the connected CRM.
* **[!UICONTROL Contacts]**—Contacts assigned to you in the connected CRM.
* **[!UICONTROL Marketing Highlights]**—Prospects with live Marketo activity, such as email opens or clicks.
* **[!UICONTROL People list]**—Prospects that you import or add manually.

## Build your prospect list

The prospect list combines people from more than one source:

* **CRM prospects**—Sales Qualifier automatically imports leads and contacts assigned to the connected user. See [Integrations](integrations.md).
* **Imported prospects**—Prospects imported from a CSV file.
* **Manually added prospects**—Individual prospects added in Sales Qualifier.

To add prospects that do not come from your CRM:

1. On the **[!UICONTROL Prospects]** page, select **[!UICONTROL People list]**.

   ![People list](assets/prospects-people-list.png){width="800" zoomable="yes"}

1. Select **[!UICONTROL + Add people]**, then select **[!UICONTROL Import CSV]** or **[!UICONTROL Add person]**.

   * For a CSV import, upload a CSV in the `firstname,email` format.
     First name and email are required. Last name is optional. The CSV template does not include the CRM lead ID column, but you can add the column and its values to the file before import. If the import fails, review the error message for the fields or values to correct, then upload the file again.
     Map any custom or additional CSV fields, not only the standard ones. Sales Qualifier saves these values to each prospect and makes them available later, including for [email generation](outbound-workflows.md#step-5-add-prospects-and-start-email-generation).
   * To add a person manually, enter their details in the form.

1. Select **[!UICONTROL Save]**.

## Filter and find prospects

Select **[!UICONTROL Filter]** to narrow the list. You can filter by:

* Outbound Workflow status
* Created by
* Job title
* Account
* Source
* Last updated

Administrators can also make mapped CRM fields available as filters. In **[!UICONTROL Admin Settings]**, turn on **[!UICONTROL Filterable]** for each field that representatives use to find prospects. See [Map CRM fields](integrations.md#map-crm-fields-inbound-mapping).

In **[!UICONTROL My Opportunity Contacts]**, you can also filter contacts by fields from their associated opportunities, such as stage, type, and close date. Opportunity fields have labels such as **[!UICONTROL Stage (Opportunity)]**, which distinguishes them from contact fields. Your administrator controls which opportunity fields are available as filters.

### Filter by Marketing Highlights

Find and prioritize prospects by their live [!DNL Marketo] engagement, such as email opens and clicks, web visits, form fills, and interesting moments. Engagement appears in near real time, as it happens.

To filter prospects by Marketing Highlights:

1. Select **[!UICONTROL Filter]**.
1. Add a Marketing Highlights filter and set the activity type, campaign, or other attributes to focus on the engagement that matters.

Each prospect shows their latest [!DNL Marketo] activity along with recent history.

Marketing Highlights is available in all production regions. An administrator completes a one-time setup that connects [!DNL Marketo] to Sales Qualifier. See [Set up Marketing Highlights](integrations.md#turn-on-marketo-engagement-filtering).

## Review prospect details

Select a prospect to open their profile. Review the signals that matter before you reach out:

* **AI person summary**—An AI-written snapshot of the lead or contact and their recent engagement. Use the summary to understand the person at a glance before reviewing individual activities. AI person summaries are available on instances running Adobe Journey Optimizer B2B Edition Prime or Ultimate.
* **Activity list**—A chronological list of activities and recent behavior.
* **Timeline view**—A visual timeline of engagement across channels.
* **Viewed content**—Web pages and assets that the prospect viewed. Select an item to open it.

### Generate meeting prep

In addition to the standing AI person summary, you can generate meeting prep tailored to a specific upcoming call from the **[!UICONTROL Meeting research]** tab, next to **[!UICONTROL Account research]**.

* **Goal-based**—If the prospect is enrolled in a running Outbound Workflow, select it. The prep aligns to that Outbound Workflow's goal, such as booking a meeting, a product pitch, an event invitation, or re-engaging the prospect.
* **Custom prompt**—Enter what you want to prepare for, for example `Focus on renewal risk` or `Prepare for a technical deep dive with their IT lead`. The prep matches your prompt. The custom prompt option is available whenever the prospect is not in a running Outbound Workflow.

>[!MORELIKETHIS]
>
>* [Accounts](accounts.md)
>* [Outbound Workflows](outbound-workflows.md)
>* [AI Chat](ai-assistant.md)
