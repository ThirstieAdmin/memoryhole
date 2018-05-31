<!-- TITLE: Cart Model -->

# Fields
- `id` *Bigint, Primary Key.* The cart ID.
- `cart_key` *Varchar.* The cart's unique key for external consumption. [Described here](unique-keys)
- `external_reference` *Varchar, optional.* The third-party client's ID.
- `session_ref` *Varchar.* The UUID of the session that created the cart.
- `customer_id` *Bigint.* The ID of the customer.
- `payment_method_id` *Bigint.* The ID of the payment method used for the cart.
- `status`
- `date_created` *Datetime.* The date and time the cart was created.
- `date_submitted` *Datetime.* The date and time the cart was submitted.
- `date_deleted` *Datetime.* The date and time the cart was deleted.

# Properties
- `orders` *Read-write property.*
- `tip` *Read-only property.*
- `discount` *Read-only property.*