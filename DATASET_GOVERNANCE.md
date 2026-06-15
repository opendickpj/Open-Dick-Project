# Dataset Governance

Open Dick Project exists to build better mask data, not to publish raw private photos.

This document lists the main risks and the operating rules we use to reduce them.

## 1. Raw Photo Exposure

**Risk:** Raw submissions may contain private anatomy, background details, faces, documents, tattoos, mirrors, or other identifying information.

**Mitigation:**

- Raw photos are not published in the public repository.
- Public releases must use code, documentation, synthetic examples, aggregate statistics, or carefully reviewed derived data only.
- Submissions that contain a face or identifying details should be rejected or deleted.

## 2. Deletion Requests

**Risk:** A contributor may later want their submission removed.

**Mitigation:**

- Each saved submission must return a deletion ID.
- A deletion request should be processed by deletion ID, not by name.
- Deletion should remove the raw image, metadata, and any unmerged annotation derived from that submission.
- If a model has already been trained, future training runs should exclude the deleted submission.

## 3. User Identity

**Risk:** Persistent user accounts can make the dataset more identifiable.

**Mitigation:**

- The collector should not require a real name.
- The collector should not require an email address.
- A stable user ID is not required for the first dataset phase.
- If repeat-contributor tracking is needed later, use an anonymous contributor key with clear consent.

## 4. Mask Definition Drift

**Risk:** Contributors may mask too much, including scrotum, thighs, hands, clothing, or background.

**Mitigation:**

- The target definition is shaft and glans only.
- Testicles/scrotum should not be included.
- The UI should repeat this rule before and during annotation.
- Submissions should store the target definition used at collection time.

## 5. Country and Demographic Data

**Risk:** Free-text country input creates inconsistent values. Race or ethnicity data is sensitive and can increase privacy and governance risk.

**Mitigation:**

- Country/region should use fixed options, not free text.
- Race/ethnicity should not be collected in the early phase.
- Any sensitive demographic field must be optional, justified, and documented before collection.

## 6. Self-Reported Size

**Risk:** Self-reported length and girth can be inaccurate, exaggerated, or measured inconsistently.

**Mitigation:**

- Size fields are optional.
- Self-reported size should be marked as self-reported.
- Aggregates should show sample size and confidence limits when possible.
- Size data should not be treated as ground truth without measurement protocol.

## 7. Data Quality

**Risk:** Blurry, cropped, side-angle, or low-light photos may reduce model quality.

**Mitigation:**

- Collect quality flags such as blur, crop, lighting, framing, and target visibility.
- Prefer standing or top-down framing for consistency.
- Keep unusable submissions out of the primary training set.

## 8. Public Claims

**Risk:** The project may be misunderstood as a measurement product before the mask dataset is mature.

**Mitigation:**

- State clearly that the first goal is segmentation masks.
- State clearly that measurement is a later research layer.
- Do not imply that a mask alone can produce centimeters.

## Maintenance Metrics

The private operator should track:

- total submissions
- unique deletion IDs
- submissions with non-empty masks
- submissions that pass quality review
- rejected submissions
- deletion requests processed
- country/region distribution
- optional self-reported size coverage

These metrics should be aggregate only.
