---
title: Create and manage Outbound Workflows
description: Learn how to create, share, review, and manage AI-generated Outbound Workflows in Adobe Marketo Qualifier to run goal-driven outreach cadences.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/n3FbuiM2zF9QSqaKx1bhBSdbsf-w7vEsEGjCQTBo3g4'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
    internal-label: Integrations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---

# Outbound Workflows

An Outbound Workflow is a goal-driven outreach cadence. You define the goal and targeting criteria. AI then proposes a multitouch cadence and writes personalized email content for each prospect. Before you activate the cadence, review and approve each email.

An Outbound Workflow connects four elements:

* **Goal**—The outcome you want from the outreach, such as booking a discovery call or increasing event registration.
* **Targeting filters**—Conditions that determine which prospects are eligible.
* **Touchpoint cadence**—The ordered sequence of email, phone call, and LinkedIn InMail steps.
* **Personalized email content**—AI-generated content based on the prospect profile, account context, engagement history, and recent news.

The AI uses the goal to suggest targeting filters, design the cadence, draft touchpoint prompts, and personalize every generated email.

## Key concepts

| Concept | Description |
| --- | --- |
| **Outbound Workflow** | A reusable outbound activity defined by a goal, targeting filters, cadence, and settings. |
| **Goal** | What the outreach should accomplish. |
| **Touchpoint** | One step in the cadence (email, phone call, or LinkedIn InMail), scheduled relative to enrollment. |
| **Touchpoint prompt** | Instructions the AI follows when generating an email subject line and body for a prospect, including tone, length, focus, and call to action. |
| **Cadence** | The full sequence of touchpoints: how many, in what order, and on which days. |
| **Targeting filter** | A condition that limits the Outbound Workflow to a subset of prospects. |
| **Draft** | A generated email that is ready for review but not yet approved. |
| **Reasoning** | The AI's explanation of how it wrote a given email, including the signals and data sources it used. |
| **Enrollment** | Approving a prospect's drafts, which activates the cadence and queues emails to send during the Outbound Workflow's send window. |

The following sections explain how to create an Outbound Workflow, review generated emails, approve prospects, and manage Outbound Workflows.

## Create an Outbound Workflow

The Outbound Workflow wizard has five steps: **[!UICONTROL Goal]**, **[!UICONTROL Targeting]**, **[!UICONTROL Generate touchpoints]**, **[!UICONTROL Settings]**, and **[!UICONTROL Add prospects]**. Your goal shapes the remaining steps.

1. In the left navigation, select **[!UICONTROL Outbound Workflows]**.
1. On the **[!UICONTROL Browse]** tab, select **[!UICONTROL + Create Outbound Workflow]** in the upper-right corner.

Administrators can assign the Outbound Workflow to a teammate instead of themselves. Before launching the workflow, select **[!UICONTROL Assign User]** from the dropdown and choose the teammate.

### Step 1: Define your goal

The goal defines the intended outcome and guides targeting, cadence, and email generation.

1. Select **[!UICONTROL Start from scratch]** to write your own goal, or select **[!UICONTROL Start from template]** to use a saved template.

1. Select one of the **[!UICONTROL Recommended goals]** matched to your company. Each recommendation includes a short explanation of why it fits. Select a recommendation to fill in the goal, select **[!UICONTROL View all]** to browse the full set of recommendations, or enter your own goal. You can also choose from the **[!UICONTROL Popular goals]** list.
1. Select **[!UICONTROL Next: Targeting]**.

State a specific outcome in the goal. For example, enter `Book a 15-minute discovery call with marketing leaders evaluating campaign automation` instead of `Promote campaign automation`.

### Step 2: Configure targeting filters

Targeting filters define which prospects are eligible. When you add prospects later, only those prospects who match these filters appear in the selection list.

![Targeting filters](assets/create-workflow-targeting.png){width="800" zoomable="yes"}

1. Select the down arrow to open the **[!UICONTROL Add a filter]** list, then select a filter.

1. Set values for the filter.
1. Add more filters if you need to narrow the audience.

1. Select **[!UICONTROL Next: Generate touchpoints]**.

### Step 3: Generate and review touchpoints

After you configure targeting, AI analyzes the goal and targeting criteria, defines the cadence, and writes a prompt for each touchpoint. The cadence can include email, phone call, and LinkedIn InMail steps.

![Touchpoints](assets/create-workflow-touchpoints.png){width="800" zoomable="yes"}

To read its prompt, expand an email touchpoint. The prompt guides the AI as it writes each prospect's email, including tone, length, focus, and call to action.

Typing a forward slash `/` brings up the list of defined tokens you can use to personalize the email.

#### Regenerate the cadence

If the cadence is not what you want, select **[!UICONTROL Regenerate]** and enter a refinement instruction. For example:

* `Use three touchpoints across two weeks`
* `Lead with an executive briefing offer in the first email`
* `Add a nurture touch focused on a relevant case study`

AI rewrites the full cadence based on your instruction. To adjust one email touchpoint, edit its prompt instead of regenerating the entire cadence.

Set a touchpoint delay in days, hours, and minutes. Set the days, hours, and minutes to `0` to send the touchpoint with no wait after enrollment or completion of the preceding touchpoint. Use a longer delay to space later touchpoints within the cadence.

#### Use the Knowledge Center in prompts

If your organization has built a [Knowledge Center](admin-settings.md#knowledge-center) playbook, refer to it in the prompt. Name the document and describe the context to use. For example, enter `Use the ABC positioning guide from the Knowledge Center and focus on the security value proposition`.

When the cadence and prompts are ready, select **[!UICONTROL Next: Settings]**.

Refine the touchpoint prompts before generating prospect emails. AI uses these prompts for every selected prospect.

### Step 4: Configure Outbound Workflow settings

The **[!UICONTROL Settings]** step controls how the Outbound Workflow runs.

![Settings panel](assets/create-workflow-settings.png){width="800" zoomable="yes"}

1. Review the **[!UICONTROL Outbound Workflow name]** and change it if needed.
1. In **[!UICONTROL Max prospects per Outbound Workflow]**, confirm the maximum number of prospects that the Outbound Workflow can manage at once.
1. Set the **[!UICONTROL Send window]** for the hours when outbound emails are allowed to send.
1. Select the days of the week when emails can send. To avoid weekend sends, select only the weekdays instead of using a separate **[!UICONTROL Skip Weekends]** setting.
1. Choose whether to send during each prospect's most active hours.
1. To stop follow-up touchpoints automatically once a prospect books a meeting, turn on **[!UICONTROL Meeting Booking Pause]**.
1. Choose whether to use each prospect's time zone or the Outbound Workflow **[!UICONTROL Timezone]** for send timing. If you use the Outbound Workflow time zone, confirm that it matches your audience.
1. Under **[!UICONTROL Permissions]**, keep **[!UICONTROL Private]** (the default) or select **[!UICONTROL Shared with everyone]**. For details, see [Share an Outbound Workflow](#share-an-outbound-workflow).
1. Select **[!UICONTROL Save and add prospects]**.

To revert the send window, time zone, days, follow-up and out-of-office rules, visibility, and suggestion cadence back to their defaults, turn on **[!UICONTROL Reset to default settings]**. The Outbound Workflow name is left unchanged.

An administrator configures the opt-out footer globally, which applies to outbound emails independently of the Outbound Workflow settings. See [Configure global email opt-out](integrations.md#configure-global-email-opt-out).

### Step 5: Add prospects and start email generation

Saving opens the prospect selection view with the targeting filters from step 2 applied.

1. Review the list.

   Rows typically include prospect name, account, email, job title, engagement status, and prospect status.

1. Adjust filters here if you need to expand or narrow the list.
1. Select prospects using the checkboxes.
1. Select **[!UICONTROL Next: Review touchpoints]** to start per-prospect email generation.

AI generates a personalized email for each selected prospect and email touchpoint. Phone and LinkedIn InMail touchpoints remain scheduled steps. To continue working during generation, select **[!UICONTROL Notify when ready]**.

For each prospect, the AI combines the touchpoint prompt with person and account data, engagement history, and recent news to produce a subject line and body.

Generated emails use any additional data saved against a prospect, including [custom fields imported with the prospect](prospects.md#build-your-prospect-list), so drafts are more relevant. There is no fixed list of supported fields, and new or custom fields work without extra setup. The AI uses this data when it is relevant; if a prospect has no extra data, email generation works as before.

Emails can also be generated in the prospect's language, with correct greetings, natural phrasing, and appropriate business tone. Supported languages include French, German, Spanish, and more.

## Review and refine generated emails

When generation finishes, the Outbound Workflow detail view prompts you to review the drafts. Adobe Marketo Qualifier does not send email until you approve it.

1. In the Outbound Workflow detail view, select **[!UICONTROL Review drafts]** in the banner.
1. The **[!UICONTROL Review touchpoints]** step has two tabs:
   * **[!UICONTROL Ready for Review]**—Emails that have finished generating.
   * **[!UICONTROL Generating]**—Emails that are still being written.
1. In the prospect list on the left, select a name to load that prospect's touchpoints on the right.
1. Use the chevron (**>**) on a touchpoint to expand and read the full subject line and body.

### Read the AI reasoning

For each generated email, **[!UICONTROL Reasoning]** explains how the AI crafted that message, including signals, attributes, and sources that shaped the content and call to action. Review this information and validate personalization before you approve.

### Edit emails directly

For small wording or tone changes:

1. On the expanded touchpoint, select the **[!UICONTROL Edit]** icon to open the editor.
1. Edit the subject line or body.
1. Select **[!UICONTROL Save]**.

### Refine emails with AI

For structural or emphasis changes, use **[!UICONTROL Generate with AI]**. AI rewrites the email while retaining its personalization context.

1. In the email editor, select **[!UICONTROL Generate with AI]**.

1. Enter a clear instruction, for example:
   * `Make it shorter and more direct. Keep it under 100 words.`
   * `Focus more on the prospect's role and how the solution helps them specifically.`
   * `Change the call-to-action to suggest a 15-minute introductory call instead.`
1. Review the revision and edit it if needed.
1. Select **[!UICONTROL Save]**.

>[!TIP]
>
>Use direct edits for wording and tone changes. Use **[!UICONTROL Generate with AI]** to rewrite the email.

## Approve and enroll prospects

Approval activates the cadence for a prospect. The system does not send emails to a prospect until you approve and enroll them.

1. In the left prospect list, select the prospects whose emails you have reviewed and are ready to send.
1. Select **[!UICONTROL Approve and enroll prospects]** in the lower-right corner.

Approved emails are sent according to the Outbound Workflow's selected days, send window, active-hours option, and time-zone setting. A touchpoint with zero delay sends immediately; every other touchpoint follows its configured delay. Unapproved prospects remain in **[!UICONTROL Ready for Review]**.

## Share an Outbound Workflow

Each Outbound Workflow has a **[!UICONTROL Permissions]** setting. Outbound Workflows are **[!UICONTROL Private]** by default. The owner can select **[!UICONTROL Shared with everyone]** to make an Outbound Workflow available to the team.

>[!CAUTION]
>
>Sharing is permanent. After an Outbound Workflow is set to **[!UICONTROL Shared with everyone]**, it cannot be changed back to **[!UICONTROL Private]**.

On a shared Outbound Workflow, teammates can enroll their own prospects. Each person can manage or pause only the prospects that they enrolled, including when using bulk actions. The Outbound Workflow owner alone can edit plan-level settings, including schedule, time zone, and cadence. These settings are read-only for teammates.

Use these filters to keep shared Outbound Workflows and results focused:

* On **[!UICONTROL Engaged Prospects]** and **[!UICONTROL Performance]**, use **[!UICONTROL Enrolled by]** to filter prospects by the person who enrolled them. The filter defaults to prospects that you enrolled.
* On the **[!UICONTROL Browse]** tab, use the sharing filter to select **[!UICONTROL Shared by me]**, **[!UICONTROL Shared with me]**, **[!UICONTROL Private]**, or **[!UICONTROL All]**.

## Out-of-office reply handling

When a prospect replies with an out-of-office message, the Outbound Workflow handles it automatically.

* **Automatic resume**: On by default. If the out-of-office reply includes a return date, the Outbound Workflow resumes the cadence on that date. If no return date is given, the Outbound Workflow resumes after a resume-after buffer that your team can configure.
* **Manual options**: A rep can still select **[!UICONTROL Resume now]** or schedule a specific resume date. See [Manage existing Outbound Workflows](#manage-existing-outbound-workflows).

## Manage existing Outbound Workflows

On the **[!UICONTROL Outbound Workflows]** page, the **[!UICONTROL Browse]** tab lists every Outbound Workflow available to you. Each card shows the goal, configured touchpoints, and performance metrics. Use this view to monitor Outbound Workflows, review drafts, or add prospects.

## Email outbox

The [Email Outbox](email-outbox.md) lists the automated emails sent on your behalf and any replies.

## Meeting booking

When you connect your calendar, Marketo Qualifier generates a personal booking link that prospects can use to schedule time with you.

* **Booking links**—Configure your calendar connection and availability in [Profile settings](profile-settings.md). Add the booking link to your email signature so that it appears in outbound emails.
* **Cadence placement**—Marketo Qualifier inserts your booking link at relevant points in a cadence. You can change its placement.
* **Booking pause**—When a prospect books a meeting, **[!UICONTROL Meeting Booking Pause]** stops further follow-ups. See [Step 4: Configure Outbound Workflow settings](#step-4-configure-outbound-workflow-settings).

Track booking outcomes on the [Outbound performance](performance.md) page.

## Outbound Workflow best practices

* **Define a specific goal.** Targeting, cadence, and emails all derive from the goal. State the outcome that you want the Outbound Workflow to achieve.
* **Finalize touchpoint prompts before per-prospect generation.** After bulk generation, changes are typically made one prospect at a time.
* **Use Reasoning as a quality check.** If the wrong signal is emphasized or a relevant signal is missing, edit the email or revise the touchpoint prompt and regenerate the cadence.
* **Match the editing tool to the change.** Use direct edits for wording and tone. Use **[!UICONTROL Generate with AI]** for restructuring or reframing.
* **Approve only what you have reviewed.** Expand touchpoints, read the content, and refine where needed before enrollment.

>[!MORELIKETHIS]
>
>* [Tasks](tasks.md)
>* [Knowledge Center](admin-settings.md#knowledge-center)
>* [Outbound performance](performance.md)
