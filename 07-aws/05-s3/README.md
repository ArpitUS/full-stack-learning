# Module 46: AWS S3

Add secure object storage for TeamOps file uploads. Use the [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html), [presigned URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html), and [S3 security best practices](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html).

## Learn

- Buckets, objects, keys, prefixes, storage classes, versioning, lifecycle, encryption, bucket/IAM policies, ownership, and object metadata.
- Presigned upload/download URLs, expiry, multipart upload concepts, event notifications, and object-level access boundaries.

## Practice Deliverable

Implement a secure presigned TeamOps upload flow. The Go API authorizes the user and issues a short-lived, constrained upload URL; the client uploads directly; the application stores metadata in PostgreSQL. Define size/content-type rules, object key ownership, retrieval authorization, encryption, and lifecycle policy.

## Completion Criteria

- [ ] Keep buckets private and grant minimum required IAM access.
- [ ] Use short-lived presigned URLs scoped to intended object/key/action.
- [ ] Authorize file ownership before issuing URLs or returning metadata.
- [ ] Validate size/type expectations and document malware/content scanning as a future production concern.
- [ ] Define lifecycle, versioning, encryption, and cleanup behavior.

## Common Mistakes

Public buckets, overbroad bucket policies, predictable keys without authorization, long-lived presigned URLs, trusting only browser content type, secrets in client code, and orphaned uploads/metadata.

## Next

Continue to [Module 47: AWS RDS](../06-rds/).
