# Open Dick Project

Website: https://opendickproject.dpdns.org/mask?v=mask-collector

There was no practical open dataset for masking self-shot private anatomy.

That is the problem.

Modern AI can detect faces, cars, hands, food, pets, documents, and almost everything else. But when it comes to private anatomy segmentation, the open data simply is not there.

Open Dick Project exists to build the missing mask dataset, annotation workflow, and research tools needed for safer and more accurate private-image processing.

## What This Project Builds

- A web-based mask collection and annotation flow
- Consent-first dataset collection tooling
- Segmentation mask correction UI
- Research notes for private anatomy detection and masking
- A path toward better measurement, privacy protection, and moderation tools

## Why It Matters

Without reliable mask data, every product in this area gets worse:

- bad masks
- bad measurement tools
- bad privacy protection
- bad moderation
- bad user experience

This project is an attempt to fix that gap directly.

## Privacy Position

Raw photos are not published.

The public repository focuses on code, tools, documentation, schemas, and research workflow. Private submissions must be handled separately from the public codebase.

## Safety and Legal Policies

This project handles sensitive data. The public policy drafts are:

- [Privacy Policy](LEGAL/PRIVACY_POLICY.md)
- [Terms of Use](LEGAL/TERMS_OF_USE.md)
- [Consent Policy](LEGAL/CONSENT_POLICY.md)
- [Deletion Policy](LEGAL/DELETION_POLICY.md)
- [CSAM Response Policy](LEGAL/CSAM_RESPONSE_POLICY.md)

These are operating drafts, not legal advice. Broad public collection requires qualified legal review.

Zero tolerance: minor or suspected minor sexual content must not be collected, processed, trained on, published, or shared.

## Dataset Policy

Only adult, consented, self-owned submissions should be used for dataset work.

Current policy:

- Raw images: private, not published
- Public code: MIT License
- Masks and derived annotations: release policy to be defined by consent and dataset governance
- Minor or suspected minor content: prohibited and subject to safety response

## Local Development

Start the local web server:

```bash
node server.mjs
```

Then open:

```txt
http://localhost:8787/
```

Mask collector:

```txt
http://localhost:8787/mask.html?v=mask-collector
```

## Repository Status

This is an early research prototype. The current priority is building a usable collection and annotation flow before publishing any dataset artifact.
