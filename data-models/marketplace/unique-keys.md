<!-- TITLE: Cart and Order Unique Key Generation -->

# Motivation and Requirements
Initially, Marketplace Carts and Orders used base-58 encoded UUIDs as unique keys for records. This presented two usability problems: the keys did not strictly increase with subsequent creation events and the keys were difficult to both read visually and speak aloud.

Ideally, Cart keys should be:
- __Monotonicallyincreasing__ (sorting carts by key should be the same as sorting carts by date created)
- __Non-sequential__ (comparing keys generated at different times should not leak order volume)
- __Human readable__ (a customer should be able to read an Order or Cart key over the phone to to customer service)

This document discusses the Cart and Order key generation algorithm currently used in the Marketplace Service.

# Algorithm
Generating a Cart key uses the time elapsed since a custom epoch. This gives us sufficient key space for order volume growth up to 1000 carts per second with a service life of 20 years.

To generate Cart keys:
- Compute the time since January 1, 2010 with millisecond precision as __∆t__
- Set __a__ to the seconds in __∆t__ converted to a base-32 string (max 7 characters)
- Set __b__ to the milliseconds in __∆t__ converted to a base-32 string (max 3 characters)
- Return the string '__{a}-{b}__' (e.g.: `02HQ4ER-8WG`)

To generate Order keys:
- Set __pfx__ to the `cart_key` of the order's cart
- Set __sfx__ to two randomly selected characters from the base-32 alphabet
- Return the string '__{pfx}-{sfx}__' (e.g.: `02HQ4ER-8WG-4P`)

# Future Expansion
The proposed algorithms should be sufficient for at least long enough to come up with a viable replacement if order volume or service duration exceed the estimates presented above. In that case, we may choose to prefix the keys with a version identifier.