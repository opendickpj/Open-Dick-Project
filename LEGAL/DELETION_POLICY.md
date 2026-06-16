# Deletion Policy

Last updated: June 16, 2026

## Deletion ID

After saving a submission, the collector shows a deletion ID. The ID is the primary way to locate a submission without asking for personal information.

## Request Process

1. Email opendickpj@gmail.com.
2. Use the subject line `Deletion request`.
3. Include the deletion ID exactly as shown.
4. Do not attach the original photo unless specifically requested.

## Deleted Items

- Raw image object in production storage.
- Metadata JSON associated with the deletion ID.
- Active use in future training manifests.

## Possible Remaining Records

- Tombstone record proving deletion happened.
- Security, abuse, or legal records if required.
- Aggregate statistics or model artifacts created before deletion if they cannot practically be reversed.

## Timing

The target response time is 30 days for valid deletion requests.

## Production Command

Dry run:

```bash
node tools/delete-r2-submission.mjs <deletion-id>
```

Execute:

```bash
node tools/delete-r2-submission.mjs <deletion-id> --execute
```
