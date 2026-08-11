# Price context missing on collection — dev spec
Site: allbirds.com · Priority 8 · Low · Effort: Medium (2-5 days)

## Problem
Collection page lists prices without indicating which items are on sale or the regular price, reducing transparency on value.

## Evidence (from the live site)
> prices: $100 $5.00 $75 $76 $100 $101

## Current state
notes: Prices listed without sale indicators or original prices.

## Required change
notes: Show strikethrough original prices and sale badges on collection tiles so shoppers can see the discount at a glance.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Show strikethrough original prices and sale badges on collection tiles so shoppers can see the discount at a glance.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_price_context_missing_on_collection` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
