---
title: Accounts in Adobe Marketo Qualifier
description: Learn how to review account intelligence in Adobe Marketo Qualifier, including AI research, recent news, opportunities, and top engaged contacts, to prioritize outreach.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
autotag-review: '2026-10-08T17:56:44.977Z'
TQID: 'https://experienceleague.adobe.com/MQxeaEGw7q8rv57xKg1f-3LahWx1laiawyvaY3n6Ri8'
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Sales Qualifier
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---

# Accounts

The account view combines AI-generated research, recent news, open opportunities, pipeline value, and engaged contacts. Use this information to understand and prioritize an account before you reach out.

To find and prioritize many accounts at once, use [Smart audience (Beta)](smart-audience.md). Build an account list, refine it with CRM data and growth signals, and find leads to add to an Outbound Workflow.

## Open an account

Open an account from the profile of a prospect associated with it.

1. Select **[!UICONTROL Prospects]** in the left navigation and open a prospect. See [Prospects](prospects.md).
1. On the prospect detail page, select the **[!UICONTROL Account]** tab.

![Prospect detail page with Person and Account tabs](./assets/account-home.png){width="800" zoomable="yes"}

Adobe Marketo Qualifier identifies the account from the prospect's CRM record. The same account view is available from every prospect associated with that account. If Marketo Qualifier cannot match an account, the tab shows _No account found_.

>[!NOTE]
>
>The available sections and metrics depend on your CRM, your organization's configuration, and the account data. If a section described here does not appear, the required data or feature is not configured.

The account view has two tabs: **[!UICONTROL Details]** and **[!UICONTROL Account Research]**.

## Review the account details

The **[!UICONTROL Details]** tab gives you a snapshot of the account and its pipeline.

### Account overview

The overview card at the top of the tab identifies the account and summarizes its value:

* The account name and region
* **Annual recurring revenue (ARR)**—The annual recurring revenue across all active subscriptions. To review ARR by product in the **[!UICONTROL Annual Recurring Revenue]** dialog, select **[!UICONTROL View All]**.
* Account statistics, including open opportunity and contact counts and the pipeline value

### Account overview summary

The **[!UICONTROL Account Overview]** panel summarizes the account based on CRM data and Account Qualification Agent research. If research is in progress, the panel shows a loading state. If research is unavailable, the panel shows a message.

### Account insights

Use the buttons below the overview to switch between account views. The available views depend on your CRM and configuration:

| View | What it shows |
| --- | --- |
| **[!UICONTROL Opportunities]** | Open opportunities linked to the account, with key fields for each. To see the full list in a table, select **[!UICONTROL View all]**. Opportunity details, such as stage, type, and close date, can also be used to filter the account's contacts in **[!UICONTROL My Opportunity Contacts]** when an administrator makes those fields filterable. |
| **[!UICONTROL Top Members]** | The account's top engaged contacts, ranked by engagement. Each contact shows their job title, email address, engagement score, and urgency indicator. |
| **[!UICONTROL Intent data]** | Buying intent signals for the account, such as the products and topics the account is researching. |
| **[!UICONTROL Account Team Members]** | People assigned to the account, with their email, job title, territory, and product group. |
| **[!UICONTROL CRM fields]** | Account fields imported from your CRM, as configured in inbound mapping. Fields that an administrator makes filterable can also be used to filter contacts by their associated account and define Outbound Workflow targeting criteria. See [Integrations](integrations.md#map-crm-fields-inbound-mapping). |

From the **[!UICONTROL Top Members]** view, take either of these actions for a contact:

* **[!UICONTROL Add to Outbound Workflow]**—Enroll the contact in an [Outbound Workflow](outbound-workflows.md).
* **[!UICONTROL Add to Marketo campaign]**—Trigger a [!DNL Marketo] campaign for the contact.

## Research the account

The **[!UICONTROL Account Research]** tab contains three areas:

* **[!UICONTROL Research categories]**—Research topics. To view a category's research in the center pane, select the category.
* **Research content**—AI-generated research cards grouped by category. A card can include the source domain and the dates when the signal was first and last detected.
* **[!UICONTROL Recent news]**—Current news about the account, including dates, tags, and source links.

![Account Research tab](./assets/account-detail.png){width="800" zoomable="yes"}

If research or news cannot load, each area offers a **[!UICONTROL Reload]** action to try again.

## Use account intelligence in outreach

Account intelligence is most valuable when it shapes what you send:

* Reference a recent news item or research signal to make your opening relevant instead of using a generic pitch.
* Check open opportunities and pipeline value to decide whether to prioritize the account.
* Use **[!UICONTROL Top Members]** to identify who to contact, then enroll them in an Outbound Workflow.
* Ask [AI Chat](ai-assistant.md) to develop positioning for the account before a call.

>[!MORELIKETHIS]
>
>* [Prospects](prospects.md)
>* [Outbound Workflows](outbound-workflows.md)
>* [AI Chat](ai-assistant.md)
