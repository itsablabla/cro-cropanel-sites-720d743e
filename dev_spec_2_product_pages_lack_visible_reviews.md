# Product pages lack visible reviews — dev spec
Site: allbirds.com · Priority 2 · High · Effort: Low (0.5-2 days)

## Problem
Product pages show a reviews heading but no actual review content, ratings, or social proof, undermining purchase confidence.

## Evidence (from the live site)
> h2: Reviews for Anytime Ankle Sock
> h2: Added to Cart

## Current state
cta: Add to Cart; notes: Reviews heading present but no review text or ratings visible.

## Required change
cta: Add to Cart; notes: Ensure review summaries, star ratings, and at least a few review excerpts render visibly on product pages near the add-to-cart area.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Ensure review summaries, star ratings, and at least a few review excerpts render visibly on product pages near the add-to-cart area.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_product_pages_lack_visible_reviews` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
