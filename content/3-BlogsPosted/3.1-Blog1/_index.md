---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Hosting a Static Website on Amazon S3 and Amazon CloudFront

In this lab I hosted a static website (HTML/CSS/JS) on Amazon S3 and delivered it worldwide over HTTPS with Amazon CloudFront. This is a very common, low-cost pattern for landing pages, documentation sites, and single-page applications.

## Architecture

```
User → CloudFront (HTTPS, cached at edge) → S3 bucket (private, static files)
```

- **Amazon S3** stores the website files. The bucket stays **private**; users never access it directly.
- **Amazon CloudFront** is the CDN in front of S3. It terminates HTTPS, caches content at edge locations close to users, and reads from S3 through **Origin Access Control (OAC)**.

## Main steps

1. **Create an S3 bucket** and upload the website files (`index.html`, assets). Keep *Block Public Access* enabled.
2. **Create a CloudFront distribution** with the S3 bucket as the origin.
3. **Enable Origin Access Control (OAC)** so only CloudFront can read from the bucket, then update the **bucket policy** to allow the CloudFront service principal.
4. **Set the default root object** to `index.html`.
5. (Optional) **Add a custom domain** with Amazon Route 53 and an **ACM certificate** for HTTPS on your own domain.
6. **Test** the CloudFront URL and confirm the site loads over HTTPS.

## Lessons learned

- Keeping the S3 bucket private and serving only through CloudFront + OAC is more secure than making the bucket public.
- CloudFront caching noticeably reduces latency for users far from the bucket's region.
- After updating files in S3, you may need a **cache invalidation** (or versioned file names) to see changes immediately.

> This pattern is exactly what I used for the frontend of my capstone Serverless E-commerce Platform.
