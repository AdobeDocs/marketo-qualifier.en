---
title: Admin settings
description: Learn how to manage CRM fields, activity synchronization, email opt-out, and other [!DNL Adobe Marketo Qualifier] administration settings.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
internal-label: Administration
autotag-review: '2026-10-08T17:58:28.029Z'
TQID: 'https://experienceleague.adobe.com/2eccZWj1XY7qP20n6GcnBe6PZwNkp0ALhZfOhljwZF8'
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Sales Qualifier
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
---

# Admin settings

Use **[!UICONTROL Admin Settings]** to configure CRM integrations, manage the Knowledge Center, and configure email opt-out.

[!DNL Adobe Marketo Qualifier] connects to Salesforce or Microsoft Dynamics 365. The connection gives the Account Qualification Agent (AQA) a consistent view of leads, accounts, contacts, activities, and owners. Marketo Qualifier can also write outreach activities and opt-out status back to the CRM and synchronize outreach activities to Marketo.

To configure CRM connections, field mapping, and activity synchronization, go to **[!UICONTROL Administration]** > **[!UICONTROL Admin Settings]** > **[!UICONTROL CRM connections]**. Standard users can use the configured CRM data and filters but cannot change these settings. To connect a CRM for the first time, see [Get started](getting-started.md#connect-your-crm).

>[!IMPORTANT]
>
>Accessing **[!UICONTROL Admin Settings]** requires membership in both the `Marketo Qualifier` and `Marketo Qualifier Admins` user groups.

## CRM MCP and the embedded plugin

Marketo Qualifier works with your CRM in these ways:

* **CRM MCP queries**—The Account Qualification Agent queries live CRM data so that answers and insights reflect the current state of your records.
* **Embedded plugin**—The CRM plugin displays [!DNL Marketo Sales Insights] (MSI) insights and agentic data in your CRM. Use the plugin to add a prospect to [!DNL Marketo Qualifier].
* **Activity synchronization**—When an administrator turns on **[!UICONTROL Activity sync]**, outreach activities synchronize to the CRM and Marketo.

### Prioritize leads in the CRM plugin

The CRM plugin provides a default home where representatives can prioritize leads without leaving the CRM. The available tabs organize work by source and intent:

* **[!UICONTROL Best Bets]**—Lead recommendations that are ready for action.
* **[!UICONTROL My Watch List]**—Leads that you are tracking.
* **[!UICONTROL Web Activity]**—Recent site visits from known leads.
* **[!UICONTROL Anonymous Web Activity]**—Visits from unidentified visitors.
* **[!UICONTROL My Email]**—Email engagement associated with your leads.
* **[!UICONTROL Webinar]**—Webinar registration and attendance activity.

Each lead can include a [!DNL Marketo] email preview, a link to the lead details, and LinkedIn research. The tabs and data that you can access depend on your CRM plugin configuration.

## CRM access scope

Marketo Qualifier reads users, contacts, owner mappings, leads, accounts, opportunities, and activities from the CRM. It writes only logged outreach activities and opt-out status to the CRM, and it synchronizes outreach activities to Marketo. Your CRM administrator prepares API access in Salesforce or Dynamics. A Marketo Qualifier administrator then connects the CRM, maps inbound fields, and chooses whether to synchronize activities.

>[!NOTE]
>
>The credential steps in [Get started](getting-started.md#connect-your-crm) describe read access to CRM objects. If you turn on activity sync or opt-out write-back, work with your CRM administrator to grant the corresponding write access required by your CRM configuration.

## Map CRM fields (inbound mapping)

After the CRM is connected, select **[!UICONTROL Manage]** for the connection and open **[!UICONTROL Inbound mapping]**. Inbound mapping controls which CRM fields Marketo Qualifier pulls into the application.

1. Select **[!UICONTROL Add section]**.
1. Enter a section name and description.
1. Select an entity type. **[!UICONTROL Prospects]** is selected by default. **[!UICONTROL Contacts]**, **[!UICONTROL Accounts]**, and **[!UICONTROL Opportunities]** are also available.
1. To import CRM fields, select the fields.

   Each field row displays its **[!UICONTROL Display name]**, **[!UICONTROL Field name]**, and **[!UICONTROL Data type]**.

1. Turn on **[!UICONTROL Filterable]** for each prospect, contact, or opportunity field that you want to make available as a filter on the **[!UICONTROL Prospects]** list.
1. Preview the section and select **[!UICONTROL Add]**.

Mapped fields appear in the corresponding areas of Marketo Qualifier:

* Prospect fields appear on the **[!UICONTROL Person]** tab.
* Account fields appear on the **[!UICONTROL Account]** tab.
* Opportunity fields appear in the **[!UICONTROL Account Opportunity]** section. Filterable opportunity fields also appear as their own columns in **[!UICONTROL My Opportunity Contacts]**, with labels such as **[!UICONTROL Stage (Opportunity)]** to distinguish them from contact fields.

## Configure activity sync (outbound mapping)

1. From **[!UICONTROL CRM connections]**, select **[!UICONTROL Manage]** for the connected CRM.
1. Open **[!UICONTROL Outbound mapping]**.
1. Turn on **[!UICONTROL Activity sync]** to sync Marketo Qualifier outreach activities back to the CRM and Marketo.

When activity sync is off, Marketo Qualifier continues to use inbound CRM data but does not synchronize outreach activities to your CRM or Marketo.

## Configure CRM Sync Rules

Marketo Qualifier can write lead status updates back to Salesforce and Microsoft Dynamics automatically as a prospect moves through an Outbound Workflow, so representatives no longer update the CRM by hand.

### What CRM Sync Rules do

An update can target the **[!UICONTROL Lead]**, **[!UICONTROL Contact]**, **[!UICONTROL Account]**, or **[!UICONTROL Opportunity]** record, not only the lead.

Updates fire on these Outbound Workflow moments:

* Added to a workflow, replied, or meeting booked
* Removed by a representative or workflow completed with no reply
* Opted out or email bounced

Field values can be personalized with dynamic tokens so that the CRM update reflects the prospect's actual journey rather than a static value. Tokens are available for details such as the representative's name, the Outbound Workflow name, and the meeting date and time.

Only CRM-compatible values are written, one failed field does not block the others, and temporary issues retry automatically. Every update is tracked so that you can see what synced and what needs attention.

### Set up CRM Sync Rules

To set up CRM Sync Rules:

1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]** > **[!UICONTROL CRM connections]**.
1. Select **[!UICONTROL Manage]** for the connected CRM, then select **[!UICONTROL Sync Rules]**.
1. Choose the target CRM entity and fields, map them to the workflow moments above, and turn on the toggle.

With CRM Sync Rules configured, sales teams see accurate, personalized, up-to-date status across leads, contacts, accounts, and opportunities at every stage, with less data lag and manual work.

## Build a Knowledge Center playbook {#knowledge-center}

The **[!UICONTROL Knowledge Center]** gives the Account Qualification Agent (AQA) access to your sales materials. Marketo Qualifier uses these materials to generate research, qualification insights, and outreach that reflect how your organization sells. Only administrators can build and manage the playbook.

![Knowledge Center](assets/knowledge-center.png){width="800" zoomable="yes"}

1. In the left navigation, expand **[!UICONTROL Administration]**, select **[!UICONTROL Admin Settings]**, and select **[!UICONTROL Knowledge Center]**.
1. Set the **[!UICONTROL Company name]** and **[!UICONTROL Company URL]** that Marketo Qualifier uses to research your company and draft emails.
1. Upload sales plays, ideal customer profiles (ICPs), positioning guides, and other sales collateral in PDF, PPTX, or DOCX format.
1. Select **[!UICONTROL Build Playbook]**.

The page shows the status of the most recently built playbook and provides the next action after you upload content. To retrieve the latest status after a build, select **[!UICONTROL Refresh]**.

Each uploaded document also displays its processing status, such as **[!UICONTROL Ready]**, and when it was last updated.

>[!NOTE]
>
>A playbook can take up to 24 hours to process.

When the playbook is ready, representatives can use it in two places:

* **Outbound email prompts**—In a touchpoint prompt, name the document and describe the context to use. For example, enter `Use the ABC positioning guide from the Knowledge Center and focus on the security value proposition`. See [Configure touchpoints](outbound-workflows.md#step-3-generate-and-review-touchpoints).
* **AI Chat**: Refer to the Knowledge Center in your question. For example, enter `From the Knowledge Center, help me position our security solution for ABC Corp before tomorrow's call`. See [AI Chat](ai-assistant.md).

In both cases, the generated content reflects the messaging in your playbook rather than generic research.

## Configure global email opt-out

1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**.
1. Select **[!UICONTROL Email settings]** under **[!UICONTROL Compliance]**.
1. Turn on **[!UICONTROL Include opt-out link in every email]** to append an unsubscribe footer to outbound emails.
1. In **[!UICONTROL Opt-out message template]**, enter the footer text. Include the `{opt_out_link}` token where the unsubscribe link should appear.

The settings save automatically.

When a prospect selects the link, Marketo Qualifier stops sending emails to that prospect and synchronizes the opt-out status to the connected CRM. Marketo Qualifier also recognizes clear opt-out requests in a prospect's email reply, such as "please stop emailing me" or "unsubscribe," and marks the prospect as opted out automatically. The same **[!UICONTROL Opted out]** status and badge apply, and no further touchpoints are sent. No additional setup is needed. Replies that do not clearly ask to stop, such as "not right now," are not treated as opt-outs. See [Opt-out requests in replies](outbound-workflows.md#opt-out-requests-in-replies).

## Reference: sample API parameters

Your CRM team can use these examples to confirm read access returns the expected lead fields.

### Dynamics OData example

```text
$select=fullname,_ownerid_value,leadid,emailaddress1,jobtitle,statuscode,createdon,modifiedon,statecode
$filter=_ownerid_value eq '<crmUserId>' [AND additional filters]
$expand=Lead_ActivityPointers(...),parentaccountid(...)
$orderby=modifiedon desc
```

### Salesforce SOQL example

```sql
SELECT Id, Salutation, FirstName, LastName, Name, Title, Company, Email,
  LeadSource, Status, OwnerId, LastModifiedDate, LastActivityDate, CreatedDate,
  (SELECT Id, Subject, ActivityDate, Status FROM Tasks ORDER BY ActivityDate DESC LIMIT 1),
  (SELECT Id, Subject, ActivityDateTime FROM Events ORDER BY ActivityDateTime DESC LIMIT 1)
FROM Lead
WHERE OwnerId = '<crmUserId>' AND IsDeleted = false
ORDER BY LastModifiedDate DESC
```

>[!MORELIKETHIS]
>
>* [Get started](getting-started.md)
>* [Prospects](prospects.md)
