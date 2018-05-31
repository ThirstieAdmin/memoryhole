<!-- TITLE: Address Model -->
<!-- SUBTITLE: Order Delivery Address -->

# Fields
- `id`
- `first_name`
- `last_name`
- `company`
- `telephone`
- `email`
- `street_1`
- `street_2`
- `street_3`
- `municipality`
- `administrative_region`
- `administrative_subregion`
- `post_code`
- `country_code`
- `latitude`
- `longitude`
- `delivery_message_id`
- `is_verified`
- `date_created`
- `date_deleted`

# Methods
- `__eq__(other: Address)` Tests for surface equality of addresses. Returns true if `first_name`, `last_name`, `company`, `telephone`, `street_1`, `street_2`, `street_3`, `municipality`, `administrative_region`, `administrative_subregion`, `post_code`, and `country_code` are all equal.

- `approximately_matches(other: Address)` Tests for a name- and apartment number-agnostic equality between addresses. Returns true if `street_1`, `municipality`, `administrative_region`, `administrative_subregion`, `post_code`, and `country_code` are all equal.
