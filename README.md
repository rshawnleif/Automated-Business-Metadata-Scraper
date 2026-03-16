# Automated-Business-Metadata-Scraper
An automated intelligence pipeline that aggregates and audits local business data from Google, Social Media, and Web Performance metrics into a unified dashboard

## Overview

This n8n workflow replaces manual research by consolidating a business's digital footprint in seconds. It is built with a "Shift-Left" mindset, ensuring data is validated and transformed before being committed to a master database.

## Tech Stack

- **Orchestration:** [n8n](https://n8n.io/)
- **Data Extraction:** [Apify](https://apify.com/) (Google Maps, Facebook, and Instagram Actors)
- **Web Analysis:** [Google PageSpeed Insights API](https://developers.google.com/speed/docs/insights/v5/get-started)
- **Storage:** Google Sheets
- **Logic & Transformation:** Node.js / JavaScript

## Key Features

- **GBP Presence Audit:** Extracts review recency (rolling 4-week window), star ratings, and differentiates between owner-uploaded vs. customer-uploaded images.
- **Social Authority Tracking:** Calculates post frequency and average engagement (likes) for Facebook and Instagram over the last 28 days.
- **Web Health Monitoring:** Pulls real-time Lighthouse scores for SEO, Performance, Accessibility, and Best Practices.
- **NAP+W Validation:** Automatically checks for "Name, Address, Phone, and Website" consistency across platforms.

## Prerequisites

To run this workflow, you will need the following:
1. An **n8n** instance (Cloud or Self-hosted).
2. An **Apify API Key** (for Google Maps and Social scrapers).
3. A **Google Cloud API Key** (with PageSpeed Insights API enabled).
4. A **Google Sheets** credential (OAuth2 or Service Account).

## Installation & Setup

1. **Import the Workflow:** Download the `.json` file from this repository and import it into your n8n instance.
2. **Configure Credentials:**
   - Link your Apify API credentials to the Apify nodes.
   - Link your Google Sheets credentials to the final node.
3. **Environment Variables:**
   - Replace `YOUR_GOOGLE_API_KEY` in the **WEB** node with your actual Google PageSpeed API key.
   - Replace `YOUR_SPREADSHEET_ID` in the **Google Sheets** node with the ID of your target sheet.
4. **Trigger:** The workflow is set to trigger via an **n8n Form**. You can access the form URL under the "On form submission" node settings to start auditing businesses.

## Data Output

The workflow outputs a single row per business including:
- **Google:** Review counts (last 1–4 weeks), Total Reviews, and Image Stats.
- **Social:** Follower counts, Verified status, and Weekly posting activity.
- **Web:** 0–100 scores for SEO, Performance, and Accessibility.

---
*Developed as a modular tool for data-driven Quality Assurance and Competitive Intelligence.*
