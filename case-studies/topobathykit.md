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

The patch, verifier, and a scoped offer are complete locally. Three direct SMTP
delivery attempts were rejected by Microsoft 365 because the residential source
IP was listed by Spamhaus. The project publishes only a `mailto:` contact and no
web form. The work has therefore not been delivered and no payment is claimed.
