# Adalia Improvement Proposal #4

## Prepaid Lease Auctions

This change adds asteroid-level auction behavior for expired prepaid lot leases, focused on lots that contain buildings. Empty lots, and lots whose `LotUse` is a ship rather than a building, are treated as ordinary expired/available lots and do not enter the auction flow.

Each asteroid has `PrepaidAgreementAuctionSettings` keyed to the asteroid, not to individual lots. The settings are:

- `mode`: `MANUAL` or `AUTO`
- `initial_period`: seconds before the descending auction begins

Defaults:

- mode: `MANUAL`
- initial period: `0`
- fixed auction duration: `7 days`
- fixed price steps: `168` hourly steps
- starting price: `1,000,000,000,000 SWAY`
- ending/minimum price: `1 SWAY`

The auction price uses a precomputed hourly table, not a continuous formula. This keeps the on-chain value exactly reproducible by the JavaScript SDK. The table starts at `1 trillion SWAY`, descends over `168` hourly steps, and remains at `1 SWAY` after the 7-day decline completes.

## Manual Mode

Manual mode is the default. When a lease expires on a lot with a building, the lot effectively remains in an indefinite grace state until the asteroid controller manually starts an auction.

The asteroid controller can call `StartPrepaidAgreementAuction` for an expired building lot. This creates a `PrepaidAgreementAuction` on that lot with a `start_time`. The auction price is then based on time elapsed since that manual auction start.

The asteroid controller may cancel an active explicit auction with `CancelPrepaidAgreementAuction`.

## Auto Mode

In auto mode, expired building-lot leases do not require an explicit auction component to be created. The auction is implicit once the lease expires.

Pricing is based on elapsed time since the expired lease’s `end_time`, plus the asteroid’s configured `initial_period`. During the initial period, the auction remains at the maximum price. After that, it descends according to the fixed hourly table.

## Renewal

The existing `ExtendPrepaidAgreement` flow now handles expired lease renewal rather than adding a separate renewal system.

After expiry, the former lessee or current building controller may renew the lease. If renewing after a lapse, the payer must cover both:

- the requested new lease term
- the elapsed unpaid time since the previous lease expired

Renewal clears any active auction for that lot and updates `UseLot` to the renewing crew.

## Auction Purchase

A third party can create a new prepaid lease on an expired building lot only through the auction flow when auction conditions apply.

Auction proceeds are split as follows:

- The asteroid controller receives up to the computed lease lapse cost since expiry.
- Any remaining auction amount goes to whoever controls the building at the time the auction concludes.

The lapse cost is calculated from the expired lease’s rate and the time since expiry, rounded up by hour.

## Repossess

The asteroid controller may repossess a building on an expired target lot. `RepossessBuilding` transfers building control and clears `UseLot` when the asteroid controller performs the repossession. If there is an explicit active auction, the client can include `CancelPrepaidAgreementAuction` in the same multicall.

## Validation / Tests

The implementation includes tests for:

- auction settings storage
- manual start and cancel
- fixed 7-day auction pricing
- initial-period pricing behavior
- auction purchase proceeds
- expired lease renewal by building controller
- ship/empty-lot behavior bypassing auction requirements

## Discussion
Please find initial discussion here: https://discord.com/channels/814990637178290177/1479315199541383390
