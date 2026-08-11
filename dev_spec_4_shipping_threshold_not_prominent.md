# Shipping threshold not prominent — dev spec
Site: allbirds.com · Priority 4 · Medium · Effort: Low (0.5-2 days)

## Problem
The free shipping threshold is buried in page copy rather than surfaced near prices or CTAs, so visitors may not see it until checkout.

## Evidence (from the live site)
> Free ground shipping on orders over $100

## Current state
notes: Free shipping threshold mentioned in copy but not prominent near prices or CTAs.

## Required change
notes: Display the free shipping threshold prominently near product prices and in the cart drawer so it is visible before checkout.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display the free shipping threshold prominently near product prices and in the cart drawer so it is visible before checkout.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_shipping_threshold_not_prominent` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
