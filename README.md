# OneClickParish 🕊️

**Instant, zero-cost, single-page websites for Catholic parishes in low-connectivity regions.**

---

## The Mission

OneClickParish is a mission-driven technology initiative aimed at establishing a basic digital presence for Catholic parishes in the world's poorest regions. In areas where internet access is slow, expensive, and unreliable, this project provides a "Minimum Viable Parish Website"—a single-page, text-only site designed to load instantly even on 2G networks.

The goal is to ensure parishioners can always access vital, up-to-date information, primarily Mass and Confession times, without consuming significant data or waiting for large assets to download. The entire system operates on a **zero-cost model** for the parish.

## The Problem We Solve

In many parts of the world, a stable internet connection is a luxury. For a parish priest, creating and maintaining a website can be an insurmountable technical and financial challenge. This creates a digital divide, leaving parishioners without a reliable source for essential information. OneClickParish bridges this gap by providing a stable, reliable digital connection between the priest and his flock.

## Key Features

*   ⚡ **Ultra-Fast & Lightweight:** The text-only site is highly optimized to be under a few kilobytes, ensuring near-instant load times on the slowest mobile networks.
*   💰 **Zero-Cost for Parishes:** No hosting fees, no domain registration costs, and no maintenance expenses for the end-user priest.
*   ✝️ **Simple & Accessible:** No technical skill is required. If a priest can fill out a web form, they can manage their parish website.
*   🤖 **Fully Automated Deployment:** A "Single Push" workflow handles the entire process of generating and publishing the site.
*   🌍 **Globally Distributed:** Leveraging the AWS CloudFront CDN, the parish site is served from a location close to the user, ensuring the lowest possible latency.

## How It Works: The "Single Push" Workflow

The project's innovation lies in separating the simple user input from the complex, high-performance deployment architecture.

1.  **One-Time Vetting:** A new user (a priest) undergoes a mandatory, one-time Review & Approval process. This non-governmental verification confirms the user's identity as a legitimate Catholic priest to ensure authenticity.
2.  **Simple Web Form:** Once approved, the priest logs in and fills out a simple form with parish information (e.g., Mass times, Confession schedule, contact details).
3.  **Publish:** The priest clicks "Publish."
4.  **Automated Pipeline:** This single click triggers a fully automated, serverless pipeline:
    *   The form data is sent to an **AWS Lambda** function.
    *   The Lambda function executes a custom **Python Static Site Generator (SSG)**.
    *   The SSG generates a new, highly optimized `index.html` file.
    *   The HTML file is instantly deployed to an **Amazon S3** bucket.
    *   The **AWS CloudFront CDN** cache is invalidated, and the new site is immediately available worldwide.

### Architecture Diagram

```
                                 +-----------------+      +----------------+
 (Priest)                        |  Simple Web Form|----->| Review/Approval| (One-Time)
   +                             +-----------------+      +----------------+
   | Fills Form
   v
+--------------------+      +------------------------+      +-----------------------------+
| 1. Click "Publish" |----->| 2. AWS Lambda Triggered|----->| 3. Python SSG Generates HTML|
+--------------------+      +------------------------+      +-----------------------------+
                                                                   |
                                                                   | 4. Uploads to S3
                                                                   v
                             +------------------+      +--------------------------+
 (Parishioner)               | 6. AWS CloudFront|<-+--| 5. Amazon S3 Static      |
   +                         |    (CDN)         |  |  |    Website Hosting       |
   | Visits Site             +------------------+  |  +--------------------------+
   v                                               |
+--------------------+                             | Caches & Serves Globally
|  Loads Instantly   |-----------------------------+
|  on Slow Network   |
+--------------------+
```

## Technology Stack

*   **Backend:** AWS Lambda
*   **Static Site Generator:** Custom Python Script
*   **Storage & Hosting:** Amazon S3
*   **Content Delivery Network (CDN):** AWS CloudFront
*   **Infrastructure as Code:** AWS CDK / SAM (TBD)

## Contributing

This is a mission-driven, open-source project. We welcome contributions from developers, designers, and anyone passionate about helping the Church. Please see `CONTRIBUTING.md` for details on how to get involved, set up your development environment, and submit pull requests.

Key areas for contribution include:
*   Improving the SSG efficiency.
*   Enhancing the user-facing web form.
*   Expanding localization and language support.
*   Developing a more robust vetting process.

## License

This project is licensed under the MIT License. See the LICENSE file for details.