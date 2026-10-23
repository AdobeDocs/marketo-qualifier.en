---
title: Smart Audience (Beta)
description: Learn how to use Smart audience (Beta) to build account lists, add CRM data and growth signals, prioritize leads, and add them to an Outbound Workflow.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
badgeBeta: label="Beta" type="Informative"
---

# Smart audience (Beta)

Smart audience (Beta) helps you find the accounts and people to work next in [!DNL Adobe Marketo Qualifier]. Describe your audience in plain language, refine the account list with CRM data and growth signals, find relevant leads, and add selected leads to an Outbound Workflow.

Work in the list view with its grid, filters, and buttons, or use chat to describe what you want. Both work on the same list: changes in one appear in the other. If a change does not appear right away, select **[!UICONTROL Refresh]**.

The progress tracker at the top of each list shows three stages: **[!UICONTROL Build smart audience list]**, **[!UICONTROL Prioritize leads]**, and **[!UICONTROL Add to outbound workflow]**.

## Before you begin

Smart audience requires a connected Salesforce or Microsoft Dynamics 365 CRM. It reads CRM data live and does not write to the CRM. For connection instructions, see [Get started](getting-started.md#connect-your-crm).

You can create up to 100 lists. Each list holds up to 500 accounts and 2,000 leads. Accounts or leads over these limits are not added. Narrow your criteria or split the audience into several lists, for example by region or segment.

## Describe and preview accounts

Start with a description of the accounts you want to reach. Previewing does not save a list.

1. Open **[!UICONTROL Smart audience]** and select **[!UICONTROL New smart audience]** or **[!UICONTROL Create list]**.
1. In chat, describe the accounts you want. For example, enter `Find healthcare accounts with revenue over $50M`.
1. Review the number of matching accounts and the sample in the preview.

Your request can include these criteria:

| Criteria | Examples |
| --- | --- |
| Firmographics | Industry, employee count, annual revenue, account type, and rating |
| Location | Region, country, state, or city |
| Ownership | Your accounts or accounts assigned to a named owner |
| Pipeline | Accounts with or without an open opportunity, subject to the [Salesforce limits](#current-scope-and-limits) |
| Account details | Name, website or domain, and account number |

Other sample requests include:

* `Accounts in the US with more than 1000 employees`
* `My accounts in Germany or France`
* `Accounts with no open opportunity`

If part of a request cannot be applied to your CRM data, chat identifies the skipped condition. The preview reflects only the conditions that were applied. Review these omissions before saving.

## Save or refine the preview

Save the preview when it matches your intended audience.

1. To change the preview, send a new request with the conditions you want. Nothing is saved until you confirm.
1. When the preview is ready, ask chat to save it as a list and give the list a name.
1. Review the saved accounts on the **[!UICONTROL Accounts]** tab.

You can rename a list from its page. To delete a list, open it and select **[!UICONTROL Delete smart audience list]**.

>[!CAUTION]
>
>Deleting a list permanently removes its accounts, leads, and columns from Smart audience. It does not delete CRM records.

## Enrich and shortlist accounts

Add information columns to help decide which accounts to work. Ask for one column or one signal per request.

To add CRM information, enter a request such as `Add a column showing which accounts have an open opportunity`. See [Current scope and limits](#current-scope-and-limits) for Salesforce restrictions.

To add growth signals, select **[!UICONTROL Enrich accounts]** in the list view or ask in chat. The available signals include:

| Signal | What it shows |
| --- | --- |
| Funding | Recent funding and financing events |
| Hiring | Recent job openings and hiring demand |
| Expansion signals | New offices, new markets, and expansion announcements |
| Technology changes | Additions and changes to a company's technology stack |
| Layoffs | Layoff information requested through chat |

For example, enter `Which of these accounts have raised funding recently?` or `Which of these accounts have had layoffs?`.

On large lists, adding a signal can take a few minutes. Follow the progress shown in the list, review each new column, and keep or discard it.

To narrow and prioritize the accounts:

1. On the **[!UICONTROL Accounts]** tab, open **[!UICONTROL Filters]**.
1. Filter by account, domain, industry, owner, minimum or maximum employees, minimum or maximum revenue, or custom columns. Custom columns are the CRM and signal columns you added. For example, filter for accounts where the hiring column is set to `Yes`.
1. Optionally, select **[!UICONTROL Prioritize accounts]** to rank the accounts by score.
1. Remove any accounts that you do not want to work.

Filters are saved with the list. Leads are found only for the filtered accounts, so set account filters before you prioritize leads.

## Find and prioritize leads

Find relevant people at the accounts you shortlisted. Under **[!UICONTROL Prioritize leads]**, choose a preset or describe the people you want in chat.

| Preset | Contacts it finds |
| --- | --- |
| **[!UICONTROL Sales contacts]** | Director of Sales and Sales Manager contacts |
| **[!UICONTROL Marketing contacts]** | VP of Marketing and Marketing Manager contacts |
| **[!UICONTROL Product contacts]** | SVP Product and Product Manager contacts |
| **[!UICONTROL Technology contacts]** | Director of IT and VP Engineering contacts |
| **[!UICONTROL All CRM contacts]** | Every available contact at the accounts, up to the 2,000-lead limit |

For a chat request, enter `Find VP and Director level people at these accounts`, `Find C-level executives (CEO, CTO, CFO) at these accounts`, or `Find managers at these accounts`.

Review the results on the **[!UICONTROL Leads]** tab. Each lead shows their name, title, account, email, owner, and score. Filter by seniority, whether an email address is available, minimum or maximum score, or whether the lead is in a workflow. The **[!UICONTROL Reasoning]** column explains why each lead is ranked where it is.

### How scores work

Scores range from 0 to 100. A higher score indicates a better fit and more readiness to engage. The same data produces the same score.

A score combines:

* **Fit**: How well the account matches your ideal customer profile, such as industry and size.
* **Buying and growth signals**: Signals such as hiring, funding, and leadership changes. Recent signals count more.
* **Sales context**: Context such as an existing customer with an expansion opportunity.

Review the reasoning and available data before deciding whom to contact.

## Add leads to an Outbound Workflow

After you review the leads, add the ones you want to an existing Outbound Workflow.

1. On the **[!UICONTROL Leads]** tab, filter and select the leads you want. For example, select leads with an email address and a minimum score of 70.
1. Select **[!UICONTROL Add to outbound workflow]**.
1. Choose the workflow and confirm.
1. Review the confirmation. The **[!UICONTROL Workflow]** column shows **[!UICONTROL Assigned]** for the added leads.

You can also ask chat to add the leads to a workflow by name. If you do not know the name, ask chat to list your available workflows. Check the workflow name and the number of leads in the reply.

Adding leads does not replace email review and approval. Follow the steps to [review generated emails](outbound-workflows.md#review-and-refine-generated-emails) and [approve and enroll prospects](outbound-workflows.md#approve-and-enroll-prospects) before outreach is sent.

## Current scope and limits

During the Beta, keep these limits in mind:

* Ask for one column or one signal per request.
* Smart audience uses standard CRM account fields. Custom CRM fields are not supported.
* Filtering by the products an account owns is not supported.
* For Salesforce, finding accounts that have an open opportunity is not available. Finding accounts with no open opportunity works with both CRMs.
* For Salesforce, requests about hiring for a specific role, such as sales representatives, are not available.

>[!MORELIKETHIS]
>
>* [Accounts](accounts.md)
>* [Prospects](prospects.md)
>* [Outbound Workflows](outbound-workflows.md)
>* [AI Chat](ai-assistant.md)
