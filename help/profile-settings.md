---
title: Configure profile settings
description: Learn how to configure your email connection, signature, and calendar availability in Adobe Marketo Qualifier profile settings.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/YsrBduYA7jKhgxttexqMBBpgDIq23s6wUb4Wp6y6h3g'
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: f8c781b4-253f-436e-b9f1-a71172814e41
    internal-label: Profile Settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
---

# Profile settings

In the left navigation, expand **[!UICONTROL Configuration]** and select **[!UICONTROL Profile settings]**. Use these settings to manage your personal details, email connection, calendar, and chat availability.

![Profile settings](assets/profile-email-config.png)

## Email settings

In the **[!UICONTROL Email settings]** tab, set up your email connections.

* **[!UICONTROL Email connections]** — Select Microsoft Outlook or Google and follow the sign-in process. See [Connect Outlook](integrations.md#connect-outlook) for the access you approve and the administrator approval path, if required.
* **[!UICONTROL Email signature]** — Add or update the signature used in generated emails. Include your [meeting booking](outbound-workflows.md#meeting-booking) link so that prospects can schedule time with you.
* **[!UICONTROL Meeting booking link]** - Send a meeting invite within your emails. Takes the meeting URL.

### Email drafting context

![Email context](assets/profile-email-instructions.png)

Use **[!UICONTROL Email drafting context]** to set the email tone, structure, and style, so that emails are consistent.

Write your context in plain markdown on the **[!UICONTROL Email drafting context]** area. 
Use it to define:

* Tone and voice
* Structure and length
* Personalization and greeting rules
* Subject-line style
* How engagement signals are used
* How metrics, proof points, and customer stories are framed

By default, drafts use a house-style context, so your existing drafts do not change until you add your own context.

## Calendar configuration

On the **[!UICONTROL Calendar configuration]** tab, set your time zone and availability.

* **[!UICONTROL Calendar connection]**—Select **[!UICONTROL Connect]** and follow the Microsoft sign-in process.
* **[!UICONTROL Meeting confirmation email]**—Define the subject and body of the confirmation email that a prospect receives after booking a meeting.
* **[!UICONTROL Preferences]**—Set the default meeting length and the buffer between meetings.

If you disconnect your calendar:

* Active booking links stop working.
* The booking page shows a temporary unavailability message.
* Your settings are preserved when you reconnect.

## Calendar availability

Your calendar availability in Adobe Marketo Qualifier is based on two inputs:

* Your connected work calendar, such as Outlook or Gmail
* The availability and time-slot rules in **[!UICONTROL Calendar configuration]**

Marketo Qualifier reads free/busy status, not event details, from the connected calendar. It combines this status with your rules to determine the time slots that prospects can book.

You can configure:

* Working hours by day of week
* Multiple blocks per day, for example, 9:00 a.m.–noon and 1:00–5:00 p.m.
* Your time zone
* Meeting duration
* Buffer before and after meetings
* Minimum notice
* Booking window

>[!MORELIKETHIS]
>
>* [Outbound Workflows](outbound-workflows.md)
>* [Integrations](integrations.md)
>* [Tasks](tasks.md)
