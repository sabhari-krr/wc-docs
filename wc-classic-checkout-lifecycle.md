
---

## WooCommerce Order Lifecycle Hooks

### 1. **Checkout Process Hooks**

**`woocommerce_before_checkout_form`**
- **Fires Before:** The checkout form starts.
- **Parameters:** None.
- **Use Cases:** Customize or add content before the checkout form begins (e.g., display promotional messages).

**`woocommerce_checkout_before_customer_details`**
- **Fires Before:** The customer details section begins.
- **Parameters:** None.
- **Use Cases:** Insert custom fields or content before the customer details input (e.g., additional instructions).

**`woocommerce_checkout_after_customer_details`**
- **Fires After:** The customer details section ends.
- **Parameters:** None.
- **Use Cases:** Add content or fields after customer details (e.g., custom order notes or upsell offers).

**`woocommerce_checkout_before_order_review`**
- **Fires Before:** The order review section begins.
- **Parameters:** None.
- **Use Cases:** Display additional information or custom fields before the order review (e.g., terms and conditions).

**`woocommerce_checkout_order_review`**
- **Fires During:** The order review section.
- **Parameters:** None.
- **Use Cases:** Modify the order review section (e.g., add custom summaries or additional order review elements).

**`woocommerce_checkout_after_order_review`**
- **Fires After:** The order review section ends.
- **Parameters:** None.
- **Use Cases:** Add custom content or functionality after the order review (e.g., extra promotions or surveys).

**`woocommerce_checkout_process`**
- **Fires During:** The checkout process, before the order is created (for validation).
- **Parameters:** None.
- **Use Cases:** Validate custom fields or data during checkout (e.g., ensure custom field values are correct).

**`woocommerce_checkout_update_order_meta`**
- **Fires After:** The order meta data has been updated.
- **Parameters:**
  - `$order_id`: The ID of the order being updated.
  - `$posted_data`: The posted checkout data.
- **Use Cases:** Save additional order metadata after checkout (e.g., custom fields or extra information).

**`woocommerce_checkout_update_order_review`**
- **Fires During:** Order review update, typically via AJAX.
- **Parameters:**
  - `$order_id`: The ID of the order being updated.
- **Use Cases:** Modify the order review dynamically (e.g., update order summary based on changes).

**`woocommerce_checkout_order_processed`**
- **Fires After:** The order is processed and saved to the database.
- **Parameters:**
  - `$order_id`: The ID of the order.
  - `$posted_data`: The posted checkout data.
  - `$order`: The order object.
- **Use Cases:** Perform actions right after an order is created and saved (e.g., send a custom notification).

### 2. **Order Creation Hooks**

**`woocommerce_new_order`**
- **Fires After:** A new order is created.
- **Parameters:**
  - `$order_id`: The ID of the newly created order.
- **Use Cases:** Trigger actions when a new order is created (e.g., integrate with external systems or services).

**`woocommerce_payment_complete`**
- **Fires After:** Payment is completed for an order.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Perform actions after payment is processed (e.g., send a confirmation email or update inventory).

**`woocommerce_thankyou`**
- **Fires After:** An order is placed and payment is processed.
- **Parameters:**
  - `$order_id`: The ID of the successfully placed order.
- **Use Cases:** Customize the "Thank You" page or perform actions after an order is successfully placed (e.g., show thank you messages or perform additional tasks).

### 3. **Order Status Hooks**

**`woocommerce_order_status_pending`**
- **Fires When:** Order status changes to pending.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Trigger actions when an order is marked as pending (e.g., notify the customer or update records).

**`woocommerce_order_status_processing`**
- **Fires When:** Order status changes to processing.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Execute actions when an order is marked as processing (e.g., start order fulfillment).

**`woocommerce_order_status_completed`**
- **Fires When:** Order status changes to completed.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Perform actions when an order is completed (e.g., trigger a thank you email or update customer records).

**`woocommerce_order_status_cancelled`**
- **Fires When:** Order status changes to cancelled.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Handle actions for cancelled orders (e.g., restock items or notify the customer).

**`woocommerce_order_status_refunded`**
- **Fires When:** Order status changes to refunded.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Manage actions for refunded orders (e.g., process refund records or update inventory).

**`woocommerce_order_status_failed`**
- **Fires When:** Order status changes to failed.
- **Parameters:**
  - `$order_id`: The ID of the order.
- **Use Cases:** Address actions for failed orders (e.g., notify the customer or handle failed payment processing).

**`woocommerce_order_status_changed`**
- **Fires When:** An order’s status transitions from one status to another.
- **Parameters:**
  - `$order_id`: The ID of the order.
  - `$old_status`: The previous status.
  - `$new_status`: The new status.
- **Use Cases:** Monitor and act on any status change in an order (e.g., logging status transitions or triggering additional workflows).

### 4. **Order Details and Email Hooks**

**`woocommerce_order_details_after_order_table`**
- **Fires After:** The order details table on the “Thank You” page.
- **Parameters:**
  - `$order`: The order object.
- **Use Cases:** Add custom content or functionality to the order details section on the “Thank You” page (e.g., display additional order information).

**`woocommerce_order_item_meta_start`**
- **Fires Before:** The meta information for each order item.
- **Parameters:**
  - `$item_id`: The ID of the order item.
  - `$item`: The order item object.
- **Use Cases:** Customize or add content before order item meta information (e.g., additional item details).

**`woocommerce_order_item_meta_end`**
- **Fires After:** The meta information for each order item.
- **Parameters:**
  - `$item_id`: The ID of the order item.
  - `$item`: The order item object.
- **Use Cases:** Customize or add content after order item meta information (e.g., additional item information or actions).

**`woocommerce_email_order_meta`**
- **Fires In:** Order email templates to add additional meta information.
- **Parameters:**
  - `$order`: The order object.
  - `$sent_to_admin`: Boolean indicating if the email is sent to the admin.
  - `$plain_text`: Boolean indicating if the email is plain text.
- **Use Cases:** Include custom order meta information in email notifications (e.g., add extra details to customer or admin emails).

### 5. **Order Deletion Hook**

**`woocommerce_delete_order`**
- **Fires When:** An order is deleted.
- **Parameters:**
  - `$order_id`: The ID of the deleted order.
- **Use Cases:** Handle actions related to order deletion (e.g., clean up related data or notify relevant parties).

---
