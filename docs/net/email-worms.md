# 电子邮件蠕虫

> 原文:[https://www.geeksforgeeks.org/email-worms/](https://www.geeksforgeeks.org/email-worms/)

电子邮件蠕虫通常被称为群发邮件蠕虫。这种蠕虫能够以电子邮件附件或链接的形式发送自己。只有当邮件来自可信来源时，它才能激活。因此，为了欺骗用户，它来自一个可信的来源，蠕虫找到了各种资源，通过这些资源可以发送这个被感染的附件。当用户打开附件或点击链接时，代码激活。因此，当用户点击附件时，恶意代码就会被执行，或者如果他们点击链接，就会被带到一个受感染的网站，在那里数据可能会被窃取。该蠕虫也可以作为带有双扩展名的附件发送。

**邮件蠕虫发送被感染邮件的方法–**

蠕虫使用最多的方法是:-

*   It uses the Windows MAPI function.
*   It uses the windows MS Outlook service.
*   Worms can find e-mail, through which they can send infected attachments to other users.
*   You can send it yourself in the message body. This worm or virus can be embedded in the message body as a link or simple HTML code.

**注意:**黑客利用这种方法发送这种病毒或蠕虫来获取用户的敏感数据、个人信息。他们使用这种类型的社会工程策略来获取大量对他们有益的数据。这种类型的方法称为网络钓鱼。

**有趣的事实:**

*   It can delete security software.
*   It also tries to download files.

**邮件蠕虫能做什么？**

*   It can be sent by mail attachment.
*   It can be used to obtain sensitive data and personal information.

**我们必须知道的避免由电子邮件病毒或蠕虫引起的网络钓鱼攻击的基本步骤–**

*   If the email comes from an unknown source, we should not open it.
*   We should not open emails from unknown companies. Therefore, e-mail may contain some viruses that can affect the system.
*   Encrypt all sensitive company information.
*   If the user finds that the email is fake, then the user should delete the email.
*   Deploy web filters to block malicious websites.

**阻止邮件病毒或蠕虫的另一种方法。**

*   We can use anti-virus software, and we can scan all attachments in emails for malware.
*   We should not provide email addresses to any unsafe web pages.
*   Scan all attachments for malware.
*   We should not open any executable files in email attachments with two extensions.
*   Always keep the mail client, operating system and web browser updated.
*   You can stop these attacks by getting a text preview in the email service of your choice.