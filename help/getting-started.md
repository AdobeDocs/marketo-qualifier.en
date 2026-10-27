---
title: Get started with Adobe Marketo Qualifier
description: Learn how to complete the one-time administrator setup for Adobe Marketo Qualifier, including user groups and a CRM connection, before your team starts using the application.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/-nfmFwZyZFUZhm-uQUjSyTvrORuqJgKSKnENWYtvubs'
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
  - id: f8f8b877-7295-5853-989f-e21f73bc94c4
    internal-label: Administration
subfeature_v2:
  - id: 74576239-3a5e-5e17-9c2d-f86db4fbb490
    internal-label: User management
  - id: d2fe5f36-5653-5902-937c-9d3026104284
    internal-label: CRM integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---

# Get started with Adobe Marketo Qualifier

After Adobe provisions Marketo Qualifier for your organization, a [!DNL Marketo] system administrator must create the required user groups and connect Salesforce or Microsoft Dynamics 365.

![Marketo Qualifier home page](assets/homepage.png){width="800" zoomable="yes"}

## Set up user groups

User groups in Adobe Admin Console are used to control access to Marketo Qualifier. Both groups must be created before users can sign in.

See the [Adobe Admin Console documentation](https://helpx.adobe.com/business/enterprise/users/users-and-groups/user-groups.html) for information about setting up groups.

>[!PREREQUISITES]
>
>The administrator who creates the groups must meet both of these requirements:
>
>* Be an organization administrator with access to **[!UICONTROL Admin Console]** from the Adobe app switcher.
>* Be assigned the Adobe Experience Platform product or be a System Administrator. Otherwise, Adobe Experience Platform does not appear in the product list.

### Marketo Qualifier users

Users must belong to the `Marketo Qualifier` user group to access the application.

These steps are done in the Adobe Admin Console.

1. From the app switcher, select **[!UICONTROL Admin Console]**.
1. Select **[!UICONTROL Users]** > **[!UICONTROL User groups]** > **[!UICONTROL New user group]**.
1. Enter `Marketo Qualifier` for the group name and select **[!UICONTROL Save]**.
1. Open **[!UICONTROL Assigned product profiles]** and select **[!UICONTROL Assign profile]**.
1. Select **[!UICONTROL Adobe Experience Platform]**.
1. Select the **[!UICONTROL Default Production All Access]** product profile, select **[!UICONTROL Apply]**, and then select **[!UICONTROL Save]**.
1. To add everyone who needs access to Marketo Qualifier, open **[!UICONTROL Users]** and select **[!UICONTROL Add users]**.

### Marketo Qualifier administrators

Administrators who configure CRM connections, the [Knowledge Center](admin-settings.md#knowledge-center), and global email opt-out settings must also belong to the `Marketo Qualifier Admins` user group.

1. In Adobe Admin Console, select **[!UICONTROL Users]** > **[!UICONTROL User groups]** > **[!UICONTROL New user group]**.
1. Enter `Marketo Qualifier Admins` for the group name and select **[!UICONTROL Save]**.
1. Open **[!UICONTROL Users]**, select **[!UICONTROL Add users]**, and add the administrators.
1. Confirm that each administrator is also a member of the `Marketo Qualifier` group.

Membership in both groups makes **[!UICONTROL Admin Settings]** visible under **[!UICONTROL Administration]** in the left navigation. Standard users work with the fields, filters, and playbook that administrators configure. The configured opt-out footer applies to their outbound emails automatically. Standard users cannot change these settings.

User group names must match exactly as shown in the preceding steps.

You can also create an optional `Marketo Qualifier BDR managers` group. Members of this group can access email performance reports.

## Connect your CRM

Marketo Qualifier connects to Salesforce or Microsoft Dynamics 365 to give BDRs a unified view of users, leads, contacts, accounts, opportunities, owner mappings, and related activities. The initial connection requires read-only access to this CRM data. To prepare credentials before you connect Marketo Qualifier, work with your CRM administrator. See [Integrations](integrations.md) for integration details.

>[!PREREQUISITES]
>
>To access the CRM administration interface, you must belong to the `Marketo Qualifier Admins` Adobe Admin Console group and the `Marketo Qualifier` group.

>[!BEGINTABS]

>[!TAB Salesforce]

A Salesforce system administrator creates an external client app (also called a connected app) and configures its run-as user.

>[!PREREQUISITES]
>
>Confirm that the Salesforce administrator has these permissions:
>
>* Customize Application
>* View Setup and Configuration
>* Modify All Data
>* Manage Connected Apps
>
>The administrator requires _Manage Connected Apps_ to view the client ID and client secret.

1. In Salesforce, go to **[!UICONTROL Setup]** > **[!UICONTROL App Manager]** and select **[!UICONTROL New Connected App]** or **[!UICONTROL New External Client App]**.
1. Enter an application name and administrative contact email.
1. Enable OAuth and enter a callback URL.

   If the connection does not use a redirect, enter any valid URL.

1. Add the following OAuth scopes:

   * Access the identity URL service (`id`, `profile`, `email`, `address`, `phone`)
   * Manage user data through APIs (`api`)
   * Access unique user identifiers (`openid`)

1. Enable the client credentials flow and select a **[!UICONTROL Run As]** user.
1. Confirm that the run-as user has **Read** access to `Leads`, `Accounts`, `Contacts`, `Tasks`, `Events`, `Opportunity`, `OpportunityContactRoles`, and `OpportunityLineItems`. Also confirm that **Access Activities** is enabled.
1. Save the application.
1. From **[!UICONTROL App Manager]**, open the application and select **[!UICONTROL View]** > **[!UICONTROL Consumer Details]**.
1. Copy the following values for the Marketo Qualifier connection:

   * Consumer Key (Client ID)
   * Consumer Secret (Client Secret)
   * Callback URL
   * Salesforce instance URL

Steps are slightly different than described here. Refer to [Salesforce documentation](https://help.salesforce.com/s/?language=en_US) for more information.

### Find your Salesforce instance URL

1. Sign in and note your org _My Domain_ subdomain from the browser address bar (the `{{mydomain}}` value).
1. Use the canonical form for Marketo Qualifier: `https://{{mydomain}}.my.salesforce.com`.

Do not use a `lightning.force.com` URL as the instance URL.

>[!TIP]
>
>If the CRM connections interface reports missing scopes, check the run-as user's profile under **[!UICONTROL Standard Object Permissions]** for **Read** access to Leads, Contacts, Accounts, and Opportunities. Also check **[!UICONTROL Object Settings]** in every assigned permission set.

>[!TAB Microsoft Dynamics 365]

A Microsoft Dynamics 365 or Azure administrator registers an application and adds it to the Dynamics environment.

1. In Microsoft Entra ID, select **[!UICONTROL App registrations]** and register an application.
1. Copy the client ID and tenant ID, and create a client secret.
1. In the **[!UICONTROL Power Platform admin center]**, select **[!UICONTROL Environments]** and open the Dynamics environment.
1. Go to **[!UICONTROL Settings]** > **[!UICONTROL Users + permissions]** > **[!UICONTROL Application users]** and select **[!UICONTROL New app user]**.
1. Select the registered Microsoft Entra application.
1. Assign a security role that grants read access to leads, contacts, accounts, opportunities, and activities.

   A security role is required. A security role is required for the application to access Dynamics data.

1. Collect the client ID, client secret, tenant ID, and Dynamics instance URL. Use the canonical URL form `https://{{mydomain}}.crm.dynamics.com`.

>[!ENDTABS]

### Enter your connection

1. As a member of both required Marketo Qualifier groups, sign in to Marketo Qualifier and confirm that the correct sandbox or environment is selected.
1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**.
1. Select **[!UICONTROL CRM connections]** under **[!UICONTROL Integrations]**.

   The page displays cards for Salesforce and Microsoft Dynamics. An inactive connection shows **[!UICONTROL Connect]**. A configured connection shows **[!UICONTROL Connected]** and **[!UICONTROL Manage]**.

   ![Salesforce credentials](assets/crm-salesforce-config.png){width="800" zoomable="yes"}

1. Select **[!UICONTROL Connect]** for the CRM that you use.
1. Enter the credentials and instance URL from your CRM administrator.
1. After a successful connection, confirm that the card shows **[!UICONTROL Connected]**.

### Import CRM fields

After connecting the CRM, configure inbound mapping to determine which CRM fields appear within Marketo Qualifier. To open **[!UICONTROL Inbound mapping]**, select **[!UICONTROL Manage]** on the connected CRM card, then add a section for each entity type whose fields you want to import.

See [Map CRM fields (inbound mapping)](integrations.md#map-crm-fields-inbound-mapping) for complete steps, including how to make imported fields available as filters.

## Next steps

>[!MORELIKETHIS]
>
>* [Prospects](prospects.md)
>* [Outbound Workflows](outbound-workflows.md)
