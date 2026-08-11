# Late fee disclosure on product pages — dev spec
Site: allbirds.com · Priority 5 · Medium · Effort: Medium (2-5 days)

## Problem
Product pages show prices but no shipping or fee information near the price, leaving cost details to be discovered later in the funnel.

## Evidence (from the live site)
> prices: $100 $5.00 $105 $105 $105 $100

## Current state
notes: Prices shown but no shipping or fee information near price.

## Required change
notes: Add a shipping and returns cost summary directly on product pages near the price to set expectations before add-to-cart.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a shipping and returns cost summary directly on product pages near the price to set expectations before add-to-cart.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_late_fee_disclosure_on_product_pages` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
