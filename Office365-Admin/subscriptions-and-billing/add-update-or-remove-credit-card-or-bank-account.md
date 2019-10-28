---
title: "Manage your payment methods"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 30ba9c83-50d8-4020-90ed-830a5b8c8724
description: "Learn how to manage your payment methods in the Microsoft 365 admin center."
---

# Manage your payment methods

::: moniker range="o365-worldwide"
You can purchase products and services from Microsoft using a credit or debit card, or bank account. You can enter your payment information on the **Payment methods** page, or when you make a purchase.

You can only manage payment methods that you have added.

> [!NOTE]
> Paying by using a bank account is not available in some countries or regions.

> You must use a credit card issued from the same country as your tenant.

## Add a new payment method
1. In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.
2. Choose **Add a payment method**.
3. On the **Payment methods** page, pick a payment method from the drop-down menu.
4. Enter the information for the new card or bank account, then choose **Save**.

## Update an existing payment method

You can't change the number on an existing card or bank account. If for some reason the card or bank account number has changed, add it as a new card or bank account, pick it as the payment option for your subscription, then remove the existing card or bank account. You must use a card issued from the same country as your tenant.

1. In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.
2. On the **Payment methods** page, pick the card or bank account to update.
3. To change the card or bank account information, choose **Edit payment details**.
4. Update your card or bank account information (name on the card or bank account, billing address, phone number, or expiration date) as needed, then choose **Save** > **Done**.

## Change the payment method used to pay for subscriptions

You can change the payment method that is used to pay for a single subscription, or you can move all subscriptions from one payment method to another.

### Change the payment method used for a single subscription

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.
2. Find and choose the subscription that you want to pay for with the new card or bank account, under **Billing**, next to the payment method, choose **Edit**.
3. Next to your existing payment method, choose **Change**.
4. From the drop-down menu, choose an alternate payment method, or choose to add a new payment method.
5. If you’re adding a new payment method, enter the card or account details, then choose **Save**.
6. Verify that the selected payment method is correct, then choose **Save**.

### Change the payment method used for multiple subscriptions

1. In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.
2. Next to the payment method you want to change, choose the **More** menu (3 dots), and then choose **Change subscriptions**.
3. The **Change payment method** pane lists existing subscriptions that use that payment method.
4. From the **Select payment method** drop-down, choose a different payment method, then choose **Save**.

## Remove a payment method

You can only remove a credit or debit card or bank account from your list of payment methods if it’s not attached to a subscription, regardless of the state of the subscription. You must add a new payment method for the subscription, and then remove the old one from that subscription. If the payment method is associated with a billing profile, you must change the payment method used for the billing profile, and then remove the payment method.

### Delete a payment method

If your payment method is not associated with any subscriptions, you can immediately delete it.

1. In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.
2. Choose the card or bank account to delete.
3. At the bottom of the **Payment method details** pane, choose **Delete**.

### Add an alternate payment method

If your payment method is associated with any subscriptions and you do not have an alternate payment method on file, you must first add a new payment method, and then change the one used to pay for the subscriptions. Then you can delete the payment method.

1. In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.
2. Hover over the card or bank account to delete, then choose the delete icon.
3. The **Delete payment method** pane lists existing subscriptions that use that payment method.
4. Choose **Add a payment method**.
5. Select the type of payment method you want to add, enter the account information, then choose **Add**.
6. Select the new payment method from the drop-down list, then choose **Change**.
    > [!NOTE]
    > This will move all subscriptions to the new payment method.
7. Choose Delete.

### Change the payment method used to pay for subscriptions

If your payment method is associated with any subscriptions, and you have at least one alternate payment method on file, you must first change the payment method used to pay for the subscriptions. Then you can delete the payment method.

1. In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.
2. Hover over the card or bank account to delete, then choose the delete icon.
3. The **Delete payment method** pane lists existing subscriptions that use that payment method.
4. Choose **Change payment method**.
5. Select an alternate payment method from the drop-down list, then choose **Change**.
    > [!NOTE]
    > This will move all subscriptions to the alternate payment method.
6. Choose **Delete**.

### Change the payment method for a billing profile

If your payment method is associated with a billing profile and is not also used to directly pay for any subscriptions, you must first change the payment method associated with it. Then you can delete the payment method.

1. In the admin center, go to the **Billing** > **Bills &amp; payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page.
2. Choose the billing profile you want to update.
3. On the billing profile details page, under **Payment method**, choose **Edit**.
4. If you have another payment method saved, choose it from the **Select a payment method** drop down, then choose **Save**.
5. If you need to add an alternate payment method, choose **Add a payment method**. Enter your account information, then choose **Add**.
6. Follow the steps in [Delete a payment method](#delete-a-payment-method) above to finish removing the payment method.

### Change the payment method used for both a billing profile and subscriptions

If your payment method is associated with a billing profile and is also used to directly pay for any subscriptions, you must first change the payment method associated with the billing profile, and then change the payment method used to pay for the subscriptions. Then you can delete the payment method.

1. Follow steps 1-5 in [Change the payment method for a billing profile](#change-the-payment-method-for-a-billing-profile) above.
2. If you have no alternate payment method, follow the steps in [Add an alternate payment method](#add-an-alternate-payment-method) above.
3. If you already have other payment methods available, follow the steps in [Change the payment method used to pay for subscriptions](#change-the-payment-method-used-to-pay-for-subscriptions) above.

## Troubleshoot payment methods

|**Issue**|**Troubleshooting steps**|
|:-----|:-----|
|**I get an error message that says, "The browser is currently set to block cookies."** <br/> |Set your browser to allow third-party cookies and try again.  <br/> |
|**My credit or debit card was declined.** <br/> |If you pay by credit or debit card, and your card is declined, you'll receive an email letting you know that we were unable to process the payment. Double-check that the card details - card number, expiration date, name on the card, and address, including city, state, and ZIP code - appear exactly as they do on the card and your statement. You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page. For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due).  <br/><br/>  If you continue to see the "declined" message, contact your bank. It's possible that your card isn't active—for example, if you recently received the card in the mail with an updated expiration date, you may still need to activate it. Your bank can also tell you if your card is not approved for online, international, or recurring transactions.  <br/> |
|**I need to update a card or bank account number.** <br/> |You can't change the number on an existing card or bank account. If your card or bank account number has changed, add a new card number or bank account, move any active subscriptions from the old card or account to the new one, and then delete the old card or account. For steps to do this, see [Add a new payment method](#add-a-new-payment-method) or [Change the payment method that you're using to pay for a subscription](#change-the-payment-method-that-youre-using-to-pay-for-a-subscription). |
|**I only have one card or bank account on my account and I want to remove it.** <br/> |If you only have one card or bank account, you'll get an error message when you try to remove it. To fix this, make sure that you're using a different payment method to pay for all your subscriptions, then try removing the card or bank account again.  <br/> |
|**I can't add my card or bank account.** <br/> |If you have trouble entering your card or bank account information, you can [contact support](../contact-support-for-business-products.md).  <br/> |

::: moniker-end

::: moniker range="o365-21vianet"

You must be a Global Admin or a Billing Admin to do the tasks described in this article.
  
 **Not an admin?** Contact your IT administrator for help. [Who has admin permissions in my business?](../admin-overview/admin-overview.md#who-has-admin-permissions-in-my-business)
  
 **For Office 365 Home, or Personal**, see [Change the payment method or credit card linked to your Microsoft account](https://support.microsoft.com/help/4026594).
  
> [!NOTE]
> Paying by using a bank account is not available in some countries or regions.

> You must use a credit card issued from the same country as your tenant.

## Add a new credit card or bank account

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.

2. Pick the subscription you want to pay for with the new credit card or bank account, then select **Update payment details**.

    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, then choose **New credit card** or **New bank account**.

    ![The drop-down menu showing the New credit card and New bank account options.](../media/2de0566c-e527-4ae7-ad6a-8b461c1e5322.png)
  
4. Enter the information for the new credit card or bank account, then select **Submit**.

    > [!NOTE]
    > The new credit card or bank account will only be used for the Office 365 subscription you chose in step 2. If you have other subscriptions that you want to use the new credit card or bank account for, follow the steps in this article to change the credit card or bank account used to pay for each subscription.

::: moniker-end

::: moniker range="o365-germany"
## Add a new credit card or bank account

You must be a Global Admin or a Billing Admin to do the tasks described in this article.
  
 **Not an admin?** Contact your IT administrator for help. [Who has admin permissions in my business?](../admin-overview/admin-overview.md#who-has-admin-permissions-in-my-business)
  
 **For Office 365 Home, or Personal**, see [Change the payment method or credit card linked to your Microsoft account](https://support.microsoft.com/help/4026594).
  
> [!NOTE]
> Paying by using a bank account is not available in some countries or regions.
>
> You must use a credit card issued from the same country as your tenant.

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.

2. Pick the subscription you want to pay for with the new credit card or bank account, then select **Update payment details**.

    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, then choose **New credit card** or **New bank account**.

    ![The drop-down menu showing the New credit card and New bank account options.](../media/2de0566c-e527-4ae7-ad6a-8b461c1e5322.png)
  
4. Enter the information for the new credit card or bank account, then select **Submit**.

    > [!NOTE]
    > The new credit card or bank account will only be used for the Office 365 subscription you chose in step 2. If you have other subscriptions that you want to use the new credit card or bank account for, follow the steps in this article to change the credit card or bank account used to pay for each subscription.

::: moniker-end

::: moniker range="o365-21vianet"
## Update an existing credit card or bank account

> [!NOTE]
>  You can't change the number on an existing credit card or bank account. If for some reason the credit card or bank account number has changed, add it as a new credit card or bank account, pick it as the payment option for your subscription, then remove the existing credit card or bank account.
>  You must use a credit card issued from the same country as your tenant.

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.

2. Pick the subscription you bought with the credit card bank account that you want to update, then select **Update payment details**.

    > [!NOTE]
    >  If another admin purchased the subscription, you won't be able to update the credit card or bank account information for it. If the credit card is about to expire and the other administrator isn't able to update it, you can prevent service interruption by adding a different credit card or new bank account for the subscription.
  
    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, choose the credit card or bank account that you want to update, then select **Edit details**.

    ![The Update payment details pane when a subscription is paid for by credit card or bank account.](../media/fa9b3a8f-9a80-4887-88e6-d19e6afd1b3d.png)
  
4. Update your credit card or bank account information (name on the credit card or bank account, billing address. phone number, or expiration date) as needed, then select **Submit**.

5. A confirmation message should appear. If it doesn't, see [Troubleshooting credit cards and bank accounts](#troubleshooting-credit-cards-and-bank-accounts).

    ![Screenshot showing the confirmation message: "Your payment method was successfully updated."](../media/23b4aa8e-f5d5-4535-92a2-9111a270f097.png)

::: moniker-end

::: moniker range="o365-germany"
## Update an existing credit card or bank account

> [!NOTE]
>  You can't change the number on an existing credit card or bank account. If for some reason the credit card or bank account number has changed, add it as a new credit card or bank account, pick it as the payment option for your subscription, then remove the existing credit card or bank account.
>  You must use a credit card issued from the same country as your tenant.

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.

2. Pick the subscription you bought with the credit card bank account that you want to update, then select **Update payment details**.

    > [!NOTE]
    >  If another admin purchased the subscription, you won't be able to update the credit card or bank account information for it. If the credit card is about to expire and the other administrator isn't able to update it, you can prevent service interruption by adding a different credit card or new bank account for the subscription.
  
    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, choose the credit card or bank account that you want to update, then select **Edit details**.

    ![The Update payment details pane when a subscription is paid for by credit card or bank account.](../media/fa9b3a8f-9a80-4887-88e6-d19e6afd1b3d.png)
  
4. Update your credit card or bank account information (name on the credit card or bank account, billing address. phone number, or expiration date) as needed, then select **Submit**.

5. A confirmation message should appear. If it doesn't, see [Troubleshooting credit cards and bank accounts](#troubleshooting-credit-cards-and-bank-accounts).

    ![Screenshot showing the confirmation message: "Your payment method was successfully updated."](../media/23b4aa8e-f5d5-4535-92a2-9111a270f097.png)

::: moniker-end

::: moniker range="o365-21vianet"
## Remove a credit card or bank account

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.

2. Pick any subscription, then select **Update payment details**.

    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, choose the credit card or bank account that you want to delete, then select **Remove**.

    ![The Update payment details pane when a subscription is paid for by credit card or bank account.](../media/fa9b3a8f-9a80-4887-88e6-d19e6afd1b3d.png)
  
4. Select **Remove** again to delete the credit card or bank account.

    ![Screenshot showing the Remove and Cancel buttons.](../media/22135f0d-c758-4564-a3b2-9c9050f7601b.png)
  
    > [!NOTE]
    > You won't be able to remove a credit card or bank account if it's currently being used to pay for a subscription. If you try, you'll get a message that looks like this:
    > ![The error message that appears if you try to remove a credit card or bank account that is currently used to pay for an active subscription.](../media/29319a8b-af0b-4487-853b-6f47d6fe4a28.png) <br/>
    > To remove the credit card or bank account, select **Back** and follow the steps in this article to change the credit card or bank account that you're using to pay for the subscription. Then try removing the credit card or bank account again.

::: moniker-end

::: moniker range="o365-germany"
## Remove a credit card or bank account

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.

2. Pick any subscription, then select **Update payment details**.

    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, choose the credit card or bank account that you want to delete, then select **Remove**.

    ![The Update payment details pane when a subscription is paid for by credit card or bank account.](../media/fa9b3a8f-9a80-4887-88e6-d19e6afd1b3d.png)
  
4. Select **Remove** again to delete the credit card or bank account.

    ![Screenshot showing the Remove and Cancel buttons.](../media/22135f0d-c758-4564-a3b2-9c9050f7601b.png)
  
    > [!NOTE]
    > You won't be able to remove a credit card or bank account if it's currently being used to pay for a subscription. If you try, you'll get a message that looks like this:
    > ![The error message that appears if you try to remove a credit card or bank account that is currently used to pay for an active subscription.](../media/29319a8b-af0b-4487-853b-6f47d6fe4a28.png) <br/>
    > To remove the credit card or bank account, select **Back** and follow the steps in this article to change the credit card or bank account that you're using to pay for the subscription. Then try removing the credit card or bank account again.

::: moniker-end
 
::: moniker range="o365-21vianet"
## Change the credit card or bank account that you're using to pay for a subscription

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.

2. Pick the subscription that you want to pay for with the new credit card or bank account, then select **Update payment details**.

    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, then choose the credit card or bank account that you want to use.

    ![The Update payment details pane when a subscription is paid for by credit card or bank account.](../media/fa9b3a8f-9a80-4887-88e6-d19e6afd1b3d.png)
  
4. Select **Submit**. If the credit card or bank account that you want to use isn't listed yet, pick **New credit card** or **New bank account** to add it.

::: moniker-end

::: moniker range="o365-germany"
## Change the credit card or bank account that you're using to pay for a subscription

1. In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.

2. Pick the subscription that you want to pay for with the new credit card or bank account, then select **Update payment details**.

    ![The Payment method section of the Subscription page, showing the Update payment details link.](../media/03839d72-773c-4030-88d0-484d1efe49c5.png)
  
3. Select the drop-down arrow under **Add or select a payment method**, then choose the credit card or bank account that you want to use.

    ![The Update payment details pane when a subscription is paid for by credit card or bank account.](../media/fa9b3a8f-9a80-4887-88e6-d19e6afd1b3d.png)
  
4. Select **Submit**. If the credit card or bank account that you want to use isn't listed yet, pick **New credit card** or **New bank account** to add it.

::: moniker-end

::: moniker range="o365-21vianet"
## Troubleshooting credit cards and bank accounts

|**Issue**|**Troubleshooting steps**|
|:-----|:-----|
|**I get an error message that says "The browser is currently set to block cookies."** <br/> |Set your browser to allow third-party cookies and try again.  <br/> |
|**My credit card was declined.** <br/> |If you pay by credit card, and your credit card is declined, you'll receive an email letting you know that we were unable to process the payment. Double-check that the credit card details - card number, expiration date, name on the credit card, and address, including city, state, and ZIP code - appear exactly as they do on the credit card and your credit card statement. You can update your credit card information and immediately submit the payment by using the **Pay now** feature. For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due).  <br/><br/>  If you continue to see the "declined" message, contact your bank. It's possible that your credit card isn't active—for example, if you recently received the credit card in the mail with an updated expiration date, you may still need to activate it. Your bank can also tell you if your credit card is not approved for online, international, or recurring transactions.  <br/> |
|**I need to update a credit card or bank account number.** <br/> |You can't change the number on an existing credit card or bank account. If for some reason your credit card or bank account number has changed, [add the new card number or bank account](#add-a-new-credit-card-or-bank-account), [change your subscription to that payment method](#change-the-credit-card-or-bank-account-that-youre-using-to-pay-for-a-subscription), and then [delete the old credit card or bank account](#remove-a-credit-card-or-bank-account). |
|**I only have one credit card or bank account on my account and I want to remove it.** <br/> |If you only have one credit card or bank account, you'll get an error message when you try to remove it. To fix this, make sure that you're using a different payment method to pay for all of your subscriptions, then try removing the credit card or bank account again.  <br/> |
|**I can't add my credit card or bank account.** <br/> |If you have trouble entering your credit card or bank account information, you can [contact support](../contact-support-for-business-products.md).  <br/> |

::: moniker-end

::: moniker range="o365-germany"
## Troubleshooting credit cards and bank accounts

|**Issue**|**Troubleshooting steps**|
|:-----|:-----|
|**I get an error message that says "The browser is currently set to block cookies."** <br/> |Set your browser to allow third-party cookies and try again.  <br/> |
|**My credit card was declined.** <br/> |If you pay by credit card, and your credit card is declined, you'll receive an email letting you know that we were unable to process the payment. Double-check that the credit card details - card number, expiration date, name on the credit card, and address, including city, state, and ZIP code - appear exactly as they do on the credit card and your credit card statement. You can update your credit card information and immediately submit the payment by using the **Pay now** feature. For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due).  <br/><br/>  If you continue to see the "declined" message, contact your bank. It's possible that your credit card isn't active—for example, if you recently received the credit card in the mail with an updated expiration date, you may still need to activate it. Your bank can also tell you if your credit card is not approved for online, international, or recurring transactions.  <br/> |
|**I need to update a credit card or bank account number.** <br/> |You can't change the number on an existing credit card or bank account. If for some reason your credit card or bank account number has changed, [add the new card number or bank account](#add-a-new-credit-card-or-bank-account), [change your subscription to that payment method](#change-the-credit-card-or-bank-account-that-youre-using-to-pay-for-a-subscription), and then [delete the old credit card or bank account](#remove-a-credit-card-or-bank-account). |
|**I only have one credit card or bank account on my account and I want to remove it.** <br/> |If you only have one credit card or bank account, you'll get an error message when you try to remove it. To fix this, make sure that you're using a different payment method to pay for all of your subscriptions, then try removing the credit card or bank account again.  <br/> |
|**I can't add my credit card or bank account.** <br/> |If you have trouble entering your credit card or bank account information, you can [contact support](../contact-support-for-business-products.md).  <br/> |

::: moniker-end

## Related topics

[Change your billing addresses](change-your-billing-addresses.md)
  
[Cancel your subscription](cancel-your-subscription.md)