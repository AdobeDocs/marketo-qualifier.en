---
title: CRM Connections
description: Learn how to install Marketo Qualifier in Salesforce or Microsoft Dynamics 365 and configure Salesforce actions for Outbound Workflows and Marketo campaigns.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
  - id: f8f8b877-7295-5853-989f-e21f73bc94c4
    internal-label: Administration
subfeature_v2:
  - id: d2fe5f36-5653-5902-937c-9d3026104284
    internal-label: CRM integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---

# CRM Connections

Install the [!DNL Adobe Marketo Qualifier] CRM plugin so that representatives can use [!DNL Marketo Sales Insights] and AI-generated insights on Lead, Contact, and Account record pages without leaving Salesforce or Microsoft Dynamics 365. The plugin also provides a home view to [prioritize leads in your CRM](admin-settings.md#prioritize-leads-in-the-crm-plugin).

In Salesforce, representatives can also add prospects to Outbound Workflows or Marketo campaigns from lead and contact list views and individual record pages.

## Before you begin

Make sure that the people who install and use the plugin have the required access:

* **Salesforce administrator**: Permission to install packages and edit page layouts.
* **Microsoft Dynamics 365 administrator**: Permission to import solutions into the target environment in Power Apps.
* **Representatives**: Access to Marketo Qualifier and to the relevant CRM records.

Installing the plugin is separate from [connecting your CRM to Marketo Qualifier](getting-started.md#connect-your-crm).

## Install in Salesforce

Install the package, then add its components to the record pages that representatives use.

1. Open the [Salesforce installation page](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=salesforce) and sign in to Salesforce as an administrator.
1. On the package installation page, select **[!UICONTROL Install for All Users]**, then select **[!UICONTROL Install]**.

   You can still control individual users' access through Salesforce permissions.

1. When prompted to approve third-party access, select the approval checkbox and select **[!UICONTROL Continue]**.
1. When installation finishes, select **[!UICONTROL Done]**.

   Installation takes a few minutes. Confirm that the package appears on the **[!UICONTROL Installed Packages]** page.

1. In Lightning App Builder, edit the Lead, Contact, and Account record pages and add the Marketo Qualifier components.

### Add actions to list views

Configure **[!UICONTROL Add to Outbound Workflow]** and **[!UICONTROL Add to Marketo Campaign]** separately for Lead and Contact list views. Use the buttons included in the package to avoid duplicates.

1. Go to **[!UICONTROL Setup]** > **[!UICONTROL Object Manager]** and select **[!UICONTROL Lead]** or **[!UICONTROL Contact]**.
1. Open **[!UICONTROL Buttons, Links, and Actions]** and locate the list buttons **[!UICONTROL AMQ Add to Outbound Workflow]** and **[!UICONTROL AMQ Add to Marketo Campaign]**.
1. Open the object's **[!UICONTROL List View Button Layout]** and select **[!UICONTROL Edit]**.

   Depending on your Salesforce setup, the list-view layout might be under **[!UICONTROL Search Layouts]** > **[!UICONTROL List View]**.

1. Move both list buttons to **[!UICONTROL Selected Buttons]** and save.
1. Repeat for the other object.

Representatives select one or more records in a list view, then select the action.

### Add actions to record pages

Record-page actions must be configured separately from list-view buttons. Add both actions to each Lead and Contact page layout in use.

1. Go to **[!UICONTROL Setup]** > **[!UICONTROL Object Manager]** and select **[!UICONTROL Lead]** or **[!UICONTROL Contact]**.
1. Open **[!UICONTROL Buttons, Links, and Actions]** and locate the detail buttons **[!UICONTROL AMQ Add to Outbound Workflow]** and **[!UICONTROL AMQ Add to Marketo Campaign]**.
1. Open **[!UICONTROL Page Layouts]** and edit a layout assigned to your representatives.
1. Add both detail buttons to **[!UICONTROL Salesforce Mobile and Lightning Experience Actions]** and save.
1. Repeat for each applicable layout and for the other object.

The actions appear in the record's action bar or its menu and apply to the record being viewed.

>[!NOTE]
>
>These actions work in desktop Salesforce Lightning Experience, not the Salesforce mobile app. The layout section named **[!UICONTROL Salesforce Mobile and Lightning Experience Actions]** is also used for desktop actions.

### Replace a missing button

If a packaged button is missing, create a replacement under the object's **[!UICONTROL Buttons, Links, and Actions]**.

1. Select **[!UICONTROL New Button or Link]**.
1. Enter a label for the action, such as `Add to Outbound Workflow` or `Add to Marketo Campaign`.
1. Choose **[!UICONTROL List Button]** for a list view or **[!UICONTROL Detail Page Button]** for a record page.
1. Set **[!UICONTROL Content Source]** to **[!UICONTROL Visualforce Page]** and choose the package's action page that matches the action, object, and placement.

   Lead list, Lead detail, Contact list, and Contact detail placements use different pages. Confirm that the selected page matches the placement you are configuring.

1. For a list button, select **[!UICONTROL Require Row Selection]**.
1. Save the button and add it to the appropriate list-view button layout or record-page actions as described above.

### Check Salesforce actions

After saving the layouts, confirm that both actions appear on Lead and Contact list views and record pages. Test each list action with selected records and each record-page action from an individual record.

If an action is not available or does not open, use these checks:

| Issue | What to check |
| --- | --- |
| Button missing from a list view | Confirm that the list button is in **[!UICONTROL Selected Buttons]** on the correct object's **[!UICONTROL List View Button Layout]**, and save the layout. |
| Button missing from a record page | Confirm that the detail button is in **[!UICONTROL Salesforce Mobile and Lightning Experience Actions]** on the layout assigned to the user. If your organization uses Dynamic Actions, also check the record page's action visibility. |
| Expected page option unavailable when creating a button | Check that the display type is **[!UICONTROL List Button]** for a list view or **[!UICONTROL Detail Page Button]** for a record page. |
| Action does not open or shows an access error | Confirm that the user has access to Marketo Qualifier and to the selected records. |

## Install in Microsoft Dynamics 365

Import the plugin package into the environment where your representatives work.

1. Open the [Microsoft Dynamics 365 installation page](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=dynamics) and download the package ZIP file.
1. Sign in to [Power Apps](https://make.powerapps.com/) as an administrator and select the target environment.
1. Open **[!UICONTROL Solutions]** and select **[!UICONTROL Import solution]**.
1. Select **[!UICONTROL Browse]**, choose the downloaded ZIP file, and select **[!UICONTROL Next]**.
1. Review the package details and select **[!UICONTROL Next]**.
1. Keep the prefilled environment variable value and select **[!UICONTROL Import]**.
1. Wait for the confirmation message at the top of the page that the solution was imported successfully.

The import takes a few minutes.

>[!MORELIKETHIS]
>
>* [Prioritize leads in the CRM plugin](admin-settings.md#prioritize-leads-in-the-crm-plugin)
>* [Integrations](integrations.md)
>* [Get started](getting-started.md)
