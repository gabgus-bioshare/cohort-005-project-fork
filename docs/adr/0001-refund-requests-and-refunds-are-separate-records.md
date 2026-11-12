# Refund Requests and Refunds are separate records

A Refund Request (open, approved, declined) and the Refund it leads to (pending, issued, failed) have independent lifecycles: a Refund can fail while its Refund Request stays approved. We store them as two records rather than one row with a combined status, so neither state has to be inferred from the other. Until a payment provider exists, a Reviewer marks each Pending Refund as Issued or Failed by hand after sending the money outside the app; that step is expected to be rewired when a provider is integrated.
