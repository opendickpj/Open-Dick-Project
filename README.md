<p align="center">
  <img src="assets/open-dick-project-logo-highres.png" width="140" alt="Open Dick Project logo">
</p>

# Open Dick Project

There is a weirdly important missing piece in computer vision:

**we do not have a practical open dataset for self-shot private anatomy masking.**

That means apps, safety tools, research prototypes, and privacy filters often have to guess. They fail on real phone photos, real angles, real lighting, and real bodies.

Open Dick Project exists to fix that.

## The Real Goal

This is not just a measurement app.

Measurement and masking are different problems.

**Masking** means finding the exact pixels that belong to the target.  
**Measurement** means turning that shape into length, girth, and scale.

You cannot measure well if you cannot first see the target well.

That is why this project starts with masks.

## Why Masks Come First

A bounding box is not enough.

NSFW detectors can sometimes say "there is a penis in this image." That is useful, but it does not tell us:

- where the shaft actually starts
- where the tip ends
- which pixels are hand, thigh, clothing, shadow, or background
- where the centerline should go
- where girth should be measured
- whether the object is cropped or angled

For future size estimation, the model needs shape, not just detection.

The mask is the foundation. Measurement comes after.

## Why This Dataset Should Exist

There are general segmentation models. There are NSFW classifiers. There are object detectors.

But we have not found a practical, consent-first, open dataset focused on **self-shot private anatomy segmentation**.

That gap matters because real phone images are messy:

- one-handed shooting
- top-down angles
- close distance
- poor lighting
- skin, hair, fabric, hands, and shadows
- inconsistent framing
- no clean studio background

Models trained on generic data do not reliably solve this.

So the first job is not magic AI.  
The first job is better data.

## The Simple Idea

We are building open mask data for private anatomy segmentation.

Not a gallery.  
Not a porn archive.  
Not a place to publish raw photos.

The goal is simple:

1. Adults take their own photo.
2. They paint only the target area.
3. The corrected mask helps train better segmentation models.
4. Raw photos stay private.
5. Useful tools and research can be released openly.

## Why This Matters

Most public vision datasets avoid this exact problem. That makes sense legally and socially, but it leaves a gap.

If there is no data, there is no good model.

If there is no good model, every app that needs accurate private-anatomy masking is forced to use weak detection, fake samples, or manual correction forever.

This project is for the boring but necessary work:

- consistent framing
- consent-first collection
- corrected masks
- repeatable annotation rules
- model training that can actually improve

## What We Are Building

Open Dick Project is split into two parts.

### Public

The public repository will contain:

- project goals
- annotation rules
- consent and privacy principles
- tooling that can be released safely
- model training notes
- non-sensitive examples

### Private

The private collection system stores:

- submitted raw photos
- corrected masks
- deletion IDs
- quality reports
- internal training data

Raw photos are not published in this repository.

## What This Can Enable

A good mask dataset can support:

- better private-anatomy segmentation
- automatic privacy masking
- safer redaction tools
- cleaner annotation workflows
- better target detection for camera guidance
- future length and girth estimation research

Size measurement is a later layer.

To measure size, a system also needs scale information, such as a reference object, camera geometry, device data, or self-reported measurements. A mask alone does not create centimeters.

But without the mask, measurement is guessing.

## Rules

This project only works if the rules are clear.

- 18+ only.
- Submit only your own image.
- No face.
- No name.
- No identifying details.
- Raw photos stay private.
- Public releases must not expose contributors.

## License

The public code and documentation are intended to be released under the MIT License.

Dataset and mask release terms will be handled separately because consent, privacy, and safety matter more than pretending a normal code license solves everything.

## Status

Early research prototype.

The first mission is not to ship a perfect model.  
The first mission is to collect better mask data safely.

Then the model can get better.
