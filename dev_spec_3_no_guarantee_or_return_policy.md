# No guarantee or return policy — dev spec
Site: allbirds.com · Priority 3 · Medium · Effort: Medium (2-5 days)

## Problem
Product pages lack shipping, return, or guarantee messaging near the purchase path, reducing trust at the decision point.

## Evidence (from the live site)
> copy: Free ground shipping on orders over $100
> h2: Refund policy

## Current state
cta: Add to Cart; notes: No return policy or guarantee message near price or add-to-cart; only a refund policy heading elsewhere.

## Required change
cta: Add to Cart; notes: Display a concise return policy and satisfaction guarantee message directly on product pages near the price and add-to-cart controls.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display a concise return policy and satisfaction guarantee message directly on product pages near the price and add-to-cart controls.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_guarantee_or_return_policy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
