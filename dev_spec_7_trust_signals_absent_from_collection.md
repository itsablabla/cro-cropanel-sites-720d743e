# Trust signals absent from collection — dev spec
Site: allbirds.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
Collection page lacks any review, rating, or credibility indicators, offering no social proof while users browse products.

## Evidence (from the live site)
> copy: SHOP ALL '26 Free ground shipping on orders over $100
> h2: Refund policy

## Current state
h1: SHOP ALL '26; notes: No reviews, ratings, or trust badges on product cards.

## Required change
h1: SHOP ALL '26; notes: Add star ratings or review counts to product cards on collection pages to build trust during browsing.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add star ratings or review counts to product cards on collection pages to build trust during browsing.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_trust_signals_absent_from_collection` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
