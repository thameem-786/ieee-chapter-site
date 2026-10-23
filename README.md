# IEEE Student Chapter Website (S3 + CloudFront + GitHub Actions)

Static chapter site with a Docker-based test and an automated deploy to AWS.

Flow: push to main -> build Docker image + smoke test -> sync to private S3 bucket -> invalidate CloudFront cache.

Stack: HTML/CSS, Docker (nginx), GitHub Actions (OIDC, no stored keys), AWS S3, CloudFront, IAM.

Run locally:
  docker build -t ieee-site .
  docker run -p 8080:80 ieee-site

Setup: see the steps in the chat; set repo variables AWS_ROLE_ARN, AWS_REGION, S3_BUCKET, CF_DIST_ID.
