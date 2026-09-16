---
title: Manage integrations
description: Learn how to connect Outlook, manage CRM connections, map inbound fields, sync activities, and configure global email opt-out in Adobe Marketo Qualifier.
feature: Agentic AI, Sales Insights, Account Journeys
role: User, Admin
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
    internal-label: Integrations
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
    internal-label: Administration
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---

# Integrations

Connect Outlook to send emails, recognize prospect replies, and schedule meetings. To make leads, contacts, accounts, opportunities, activities, and owners available to the Account Qualification Agent (AQA) and Outbound Workflows, you can also connect Adobe Marketo Qualifier to Salesforce or Microsoft Dynamics 365. Marketo Qualifier reads CRM data, can write outreach activities and opt-out status back to the CRM, and can synchronize outreach activities to Marketo. It does not otherwise modify CRM records.

This article explains how to connect Outlook, manage a CRM connection, map fields, sync activities, and configure email opt-out. To connect a CRM for the first time, see [Get started](getting-started.md#connect-your-crm).

>[!IMPORTANT]
>
>The Outlook connection is per representative. The CRM and compliance settings described later in this article apply to the entire organization. To access those organization-wide settings, you must belong to the `Marketo Qualifier` and `Marketo Qualifier Admins` user groups. Standard users can use the configured CRM data and filters but cannot change the settings.

## Connect Outlook

Each representative connects their own Outlook account:

1. Select **[!UICONTROL Connect Outlook]**.
1. Sign in with your Microsoft account.
1. Review and approve the requested access.

The connection lets Marketo Qualifier send from your mailbox, recognize when a prospect replies, and schedule meetings on your calendar.

When you connect, you approve access that allows Marketo Qualifier to:

* Recognize replies from prospects.
* Create and send email on your behalf.
* Use your calendar to schedule meetings.
* Read your mailbox time zone and working hours for scheduling.
* Remain signed in automatically so that these features continue to work without requiring you to sign in again.

### Outlook approvals (if required)

By default, no administrator action is required. Each representative approves access for themselves when they connect Outlook.

If your organization has turned off user consent to third-party apps in Microsoft 365 or Microsoft Entra, a Microsoft 365 or Entra administrator must approve Marketo Qualifier once for the entire organization. The administrator completes this approval before representatives connect their Outlook accounts. After the organization-wide approval, each representative can connect their account.

### How Marketo Qualifier handles your mailbox data

Marketo Qualifier reads only replies to emails that it sent, not the rest of your inbox. It does not store incoming attachments or emails outside an active engagement. Stored sign-in credentials are encrypted.

## Open CRM settings

In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**. The settings are organized into two groups:

| Group | Items |
| --- | --- |
| **[!UICONTROL Integrations]** | **[!UICONTROL CRM connections]**, **[!UICONTROL Knowledge Center]** |
| **[!UICONTROL Compliance]** | **[!UICONTROL Email settings]** |

For the Knowledge Center, see [Build a Knowledge Center playbook](admin-settings.md#knowledge-center).

## Manage CRM connections

Select **[!UICONTROL CRM connections]**. The page contains cards for **[!UICONTROL Salesforce]** and **[!UICONTROL Microsoft]** (Microsoft Dynamics 365). Each card shows one of these statuses:

| Status | Meaning |
| --- | --- |
| **[!UICONTROL Connected]** | The connection is active and authenticated. |
| **[!UICONTROL Not active]** | No connection is configured for this CRM. |
| **[!UICONTROL Permissions required]** | The connection is authenticated, but required scopes are missing. The card lists the missing scopes. |

>[!NOTE]
>
>Only one CRM can be active at a time. When one CRM is connected, the other card is disabled. Disconnect the active CRM before you connect a different one.

An unconfigured card shows **[!UICONTROL Connect]**. A configured card shows **[!UICONTROL Manage]** and a **[!UICONTROL More]** menu with **[!UICONTROL Edit configuration]** and **[!UICONTROL Disconnect]**.

### Connect or edit a connection

1. On the CRM card, select **[!UICONTROL Connect]**, or select **[!UICONTROL More]** > **[!UICONTROL Edit configuration]** to update an existing connection.
1. Enter the credentials from your CRM administrator.

   >[!BEGINTABS]

   >[!TAB Salesforce]

   Enter the **[!UICONTROL Client ID (Consumer Key)]**, **[!UICONTROL Instance URL]**, and **[!UICONTROL Client Secret]**. Use the canonical instance URL form `https://{{mydomain}}.my.salesforce.com`.

   ![Salesforce credentials](assets/crm-salesforce-config.png){width="800" zoomable="yes"}

   >[!TAB Microsoft Dynamics]

   Enter the **[!UICONTROL Client ID (Consumer Key)]**, **[!UICONTROL Tenant ID]**, **[!UICONTROL Microsoft Dynamics Instance URL]**, and **[!UICONTROL Client Secret]**. Use the canonical instance URL form `https://{{mydomain}}.crm.dynamics.com`.

   >[!ENDTABS]

1. Select **[!UICONTROL Connect]** (or **[!UICONTROL Save]** when editing).

If Marketo Qualifier rejects the credentials, it identifies the cause, such as invalid or expired credentials, missing permissions, or an unrecognized Dynamics tenant. Correct the value and try again.

>[!IMPORTANT]
>
>Do not send client secrets by email. Use your organization's approved secure channel to share credentials with whoever enters them in Marketo Qualifier.

### Disconnect a connection

1. On the connected CRM card, select **[!UICONTROL More]** > **[!UICONTROL Disconnect]**.
1. Review the warning and select **[!UICONTROL Disconnect]** to confirm.

>[!WARNING]
>
>When you disconnect a CRM, Outbound Workflows pause for all prospects in your organization, and no new prospects sync from your CRM until you reconnect.

## Map CRM fields (inbound mapping) {#map-crm-fields-inbound-mapping}

Inbound mapping controls which CRM fields Marketo Qualifier imports and where they appear. Fields are grouped into sections, and each section belongs to an entity type.

![Inbound mapping](assets/crm-conn-salesforce.png){width="800" zoomable="yes"}

1. On the connected CRM card, select **[!UICONTROL Manage]**.
1. On the **[!UICONTROL Inbound mapping]** tab, select **[!UICONTROL Add section]**.

   ![Add section](assets/crm-add-section.png){width="800" zoomable="yes"}

1. On the **Select section** step, choose the entity type, then select **[!UICONTROL Next]**:

   | Entity | Where its fields appear |
   | --- | --- |
   | **[!UICONTROL Prospects]** | The **[!UICONTROL Person]** tab of a prospect. |
   | **[!UICONTROL Contacts]** | The contact record. |
   | **[!UICONTROL Accounts]** | The **[!UICONTROL Account]** tab. See [Accounts](accounts.md). |
   | **[!UICONTROL Opportunities]** | The account's opportunity details. |

1. Enter a **[!UICONTROL Section name]** and an optional **[!UICONTROL Description]**. Then, select **[!UICONTROL Next]**.
1. On the **[!UICONTROL Add field]** step, search for and select the CRM fields to import. Then, select **[!UICONTROL Next]**. Each field shows its **[!UICONTROL Display name]**, **[!UICONTROL Field name]**, and **[!UICONTROL Data type]**.
1. For **[!UICONTROL Prospects]**, **[!UICONTROL Contacts]**, and **[!UICONTROL Opportunities]** sections, turn on **[!UICONTROL Filterable]** for each field that representatives need on the [Prospects](prospects.md) list.

   A field cannot be made filterable if its data type does not support filtering or if it is already used in another section.

   In **[!UICONTROL My Opportunity Contacts]**, filterable opportunity fields appear as separate columns with labels such as **[!UICONTROL Stage (Opportunity)]**. The suffix distinguishes opportunity attributes from fields on the associated contact.

1. On the **[!UICONTROL Preview]** step, confirm your selection and select **[!UICONTROL Add]**.

To change a section later, select **[!UICONTROL Edit]** on the section card. To remove a section, select **[!UICONTROL Remove]** on the section card. To remove an individual field, select the delete action in the field row. Confirm each removal.

## Configure activity sync (outbound mapping) {#configure-activity-sync-outbound-mapping}

Activity sync writes Marketo Qualifier outreach activities to your CRM and Marketo. Email sent, opened, clicked, and replied activities include the Outbound Workflow name. Representatives can see the activities in the CRM, while marketing teams can use the Marketo activities in lead scoring and engagement timelines.

1. On the connected CRM card, select **[!UICONTROL Manage]**.
1. Open the **[!UICONTROL Outbound mapping]** tab.
1. Turn on **[!UICONTROL Activity sync]**. The setting saves immediately.

When activity sync is off, Marketo Qualifier continues to use inbound CRM data but does not synchronize outreach activities to the CRM or Marketo.

>[!NOTE]
>
>Activity sync requires write access in your CRM. If the required permission is missing, the switch is disabled and Marketo Qualifier prompts you to contact your administrator. To grant activity write access, work with your CRM administrator.

## Set up Marketing Highlights {#turn-on-marketo-engagement-filtering}

Marketing Highlights lets representatives find and prioritize prospects by their live [!DNL Marketo] engagement, such as email opens and clicks. See [Filter by Marketing Highlights](prospects.md#filter-by-marketing-highlights).

An administrator completes a one-time setup that connects [!DNL Marketo] to Marketo Qualifier for the relevant org and sandbox. The setup covers creating API credentials in the Adobe Developer Console, configuring a webhook in [!DNL Marketo], and adding that webhook to a trigger Smart Campaign. See [Set up Marketing Highlights](marketing-highlights-setup.md) for complete steps.

Marketing Highlights is available in all production regions: North America, EMEA, and Australia.

## Configure global email opt-out {#configure-global-email-opt-out}

The opt-out setting appends an unsubscribe footer to every outbound email. Standard users cannot turn it off for an individual email.

1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**.
1. Select **[!UICONTROL Email settings]** under **[!UICONTROL Compliance]**.
1. Turn on **[!UICONTROL Include opt-out link in every email]**.
1. In **[!UICONTROL Opt-out message template]**, enter the footer text. Include the `{opt_out_link}` token where the clickable unsubscribe link should appear.

   For example: `If you'd prefer not to receive these emails, you can {opt_out_link}.`

The setting and template save automatically.

When a prospect selects the link, Marketo Qualifier stops sending emails to that prospect and syncs the opt-out status to the connected CRM.

## CRM access scope

Marketo Qualifier reads the CRM entities it needs and writes back only a defined set of data:

* **Read**—Users, contacts, owner mappings, leads, accounts, opportunities, and activities.
* **Write**—Logged outreach activities (when [activity sync](#configure-activity-sync-outbound-mapping) is on) and opt-out status.

Your CRM administrator prepares API access in Salesforce or Dynamics. A Marketo Qualifier administrator then connects the CRM, maps inbound fields, and chooses whether to synchronize activities. The initial connection requires read-only access. Activity synchronization and opt-out write-back require the corresponding write access.

>[!MORELIKETHIS]
>
>* [Get started](getting-started.md)
>* [Accounts](accounts.md)
