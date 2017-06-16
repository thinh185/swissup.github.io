---
layout: default
title: Usage
description: magento 2 checkout fields module usage
keywords: magento 2 checkout fields extension
category: Checkout Fields
---

# Checkout Fields Usage Examples

## Contents

 -  [Order Comment Field](#order-comment-field)
 -  [Display Fields in Order Email](#display-fields-in-order-email)

### Order Comment Field

To add order comment field on checkout, follow below steps:

 1. Go to `Swissup > Checkout > Checkout Fields`
 2. Press `Add New Field` button
 3. Fill `Default Label`
 4. Select `Store View` where to show the field
 5. In `Catalog Input Type` select `Text Area`
 6. If required, fill other optional properties, such as `Values Required`, `Sort Order` and `Default Value`
 7. Specify labels for other store views on `Manage Labels` tab if required
 8. Press `Save Field` button
 9. Go to checkout and check the field you created:

![Order Comment Field](/images/m2/checkout-fields/order-comment.png)

### Display Fields in Order Email

In order to display checkout fields in order emails, follow next steps:

 1. Go to `Marketing > Communications > Email Templates`
 2. Press `Add New Template` button
 3. Select template, for example `New Order for Guest`, and press `Load Template` button
 4. Give name for template in `Template Name` field
 5. In `Template Content` place the following code where you want to show checkout fields:

    ```txt
    {% raw %}{{block class="Swissup\CheckoutFields\Block\Adminhtml\Order\View\Fields" area="frontend" template="Swissup_CheckoutFields::email/order/fields.phtml" order=$order}}{% endraw %}
    ```

 6. Press `Save Template` button
 7. Go to `Stores -> Configuration -> Sales > Sales Emails -> Order`, select new template in
    `New Order Confirmation Template for Guest` and press `Save Config`
 8. Check order email with checkout fields:

![Fields in Order Email](/images/m2/checkout-fields/fields-order-email.png)