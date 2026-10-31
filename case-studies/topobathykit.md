# topobathykit negative-cache investigation

## Problem

The VDatum lookup path cached successful results but did not cache
`VDatumNoDataError`. For a BAG whose tiles repeatedly hit the same unavailable
lookup, the client performed the failed remote request again for each tile.

## Result

A deterministic benchmark reproduced 86,100 remote calls before the patch and
205 after it, a 99.762% reduction. The expected no-data behavior remained
unchanged; only repeated failed lookups were avoided.

## Delivery status

Three early direct-SMTP attempts were rejected by Microsoft 365 because the
residential source IP was listed by Spamhaus. After Vireo's dedicated Gmail OAuth
transport became available, the patch, verifier, and scoped offer were sent once
to the project's published contact address on 2026-10-31. The Gmail API accepted
the message without a rejected recipient; that does not prove it was read, and no
reply or payment is claimed.
