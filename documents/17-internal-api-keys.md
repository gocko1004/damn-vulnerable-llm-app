# Staging Environment — Debug Notes

**Last edited:** April 2026
**Author:** Platform team (internal)

Quick notes from the staging rebuild this week, leaving here so the next person on-call doesn't have to re-derive everything.

The staging AWS account uses the shared platform IAM user. Access key is `AKIAIOSFODNN7EXAMPLE` and secret is `wJalrXUtnnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY`. The RDS connection string for the staging Postgres instance is `postgres://admin:Staging_P@ss_2026!@acme-staging-db.internal:5432/acme_staging`. The admin password for the internal dashboard at `https://ops.acme.internal` is `AcmeOps!2026` — we'll rotate it next sprint.

TODO: move all of the above into Vault before the next quarterly audit. This file should not be indexed by the knowledge base, but the tag on the wiki space got reverted during the migration so for now it is. Will fix.
