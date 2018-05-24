<!-- TITLE: Order Model -->

# Fields
- `id`
- `order_key` *Varchar.* The order UUID
- `external_reference`  *Varchar, optional.* The third-party client's ID.
- `cart_id` *Bigint.* The ID of the cart containing the order.
- `merchant_ref` *Varchar.* The TMK of the retailer fulfilling the order.
- `delivery_address_id` *Bigint.* The ID of the order's delivery address.
- `status_id` *Int.* The ID of the cart's current status.
- `date_submitted` *Datetime.* The date and time the order was submitted.
- `date_modified` *Datetime.* The date and time the order was last modified.
- `promo_ref` *Varchar.* The promo code used on the order.
- `gift_message_id` *Bigint.* The message ID of the gift message.
- `delivery_minimum` *Decimal.* The merchant's order delivery minimum.
- `amt_delivery_fee` *Decimal.* The delivery fee for the order.
- `amt_shipping_cost` *Decimal.* The shipping cost for the order.
- `amt_delivery_tip` *Decimal.* The tip on the order.
- `delivery_method` *Varchar.* The order delivery method.
- `delivery_date` *Date.* The delivery date for a scheduled delivery.
- `delivery_start_time` *Time.* The start time of a scheduled delivery window.
- `delivery_end_time`*Time.* The end time of a scheduled delivery window.
- `thirstie_logistic_order_ref` __*Deprecated.*__

__PROPOSED:__


- `amt_order_total` *Decimal.* The total cost of the order.
- `amt_paid` *Decimal.* The total amount paid by the customer.
- `merchant_rejection_reason` *Varchar.* The reason the merchant could not fulfull the order.
- `date_merchant_accepted` *Datetime.* The date the merchant accepted the order.
- `date_cancelled` *Datetime.* The date the customer cancelled or disputed the order.
- `date_shipped` *Datetime.* The date the merchant shipped the order.
- `date_completed` *Datetime.* The date the merchant or carrier delivered the order.

# Properties & Methods
- `status` *Read-only property.* The current computed state of the order. This is not simply returning the status referenced by `status_id`.

# State Transitions
Thirstie orders are always in one (and only one) of fourteen states. The states are: `pending`, `payment_submitted`, `payment_approved`, `payment_declined`, `merchant_rejected`, `merchant_accepted`, `merchant_shipped`, `completed`, `cancelled`,  `preship_cancel`, `in_transit_cancel`, `disputed`, `resolved`, and `closed`.

The details of an order's progression from creation to completion are detailed in the following state transition diagram.

[Cart State Diagram](/uploads/diagrams/cart-state-diagram-draft-3.pdf "Cart State Diagram - DRAFT 3")