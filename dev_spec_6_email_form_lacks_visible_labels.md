# Email form lacks visible labels — dev spec
Site: allbirds.com · Priority 6 · Medium · Effort: Low (0.5-2 days)

## Problem
Email input fields lack visible labels, causing user confusion about what information is required.

## Evidence (from the live site)
> form: inputs=1 submit=Sign Up labels=[]
> form: inputs=1 submit=Get Notified labels=['Email']

## Current state
cta: Sign Up / Get Notified; notes: Input fields have no visible labels; one form has no labels at all, the other has a label for Email.

## Required change
cta: Sign Up / Get Notified; notes: Add visible, descriptive labels to each email input so users clearly understand what to enter before submitting.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add visible, descriptive labels to each email input so users clearly understand what to enter before submitting.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_email_form_lacks_visible_labels` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
