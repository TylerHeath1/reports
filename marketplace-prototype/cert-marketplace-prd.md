# Product Requirements Document: Certification & Audit Marketplace

**Author:** Tyler Heath, Director of Strategic Initiatives
**Date:** April 16, 2026
**Status:** Draft / Prototype Phase
**Prototype:** [Live Clickable Prototype](https://tylerheath1.github.io/reports/prototypes/cert-marketplace-prototype.html)

---

## Problem Statement

Buyers (sourcing, procurement, and compliance professionals at brands and retailers) currently have to chase down facility certifications and audit reports manually. They click out to provider websites, email facilities, or take claims on faith. Open Supply Hub already shows *that* certifications exist via Spotlight data, but there is no way to verify, purchase, or retrieve the actual documents directly on the platform.

Meanwhile, service providers (audit firms, certifying bodies) have no scalable channel to distribute their reports to the buyers who need them.

---

## Opportunity

Build a two-sided marketplace on OS Hub where buyers can purchase certifications and audit reports directly from service providers, inline on facility profile pages or in bulk across their supply chain. This positions OS Hub as the single platform where supply chain data is not only discovered but verified and transacted.

---

## Marketplace Structure

### Sellers
Service providers: audit firms and certifying bodies (e.g., amfori, GOTS, Hohenstein, SGS, Worldly). They list and sell their documents on OS Hub. Facilities do not sell directly but may receive a revenue share.

### Buyers
Sourcing, procurement, or compliance professionals at brands and retailers who need certification or audit documents for due diligence, reporting, or regulatory compliance.

### Two Document Types

| | Certifications | Audits / Assessments |
|---|---|---|
| **Who controls the document** | Facility typically owns the PDF | Audit firm controls the report |
| **Who initiates** | Facility pays for certification | Buyer or brand commissions the audit |
| **Current behavior** | Facilities share freely via email | Reports are proprietary and paid |
| **OS Hub value proposition** | Convenience at scale | Access to proprietary information |
| **Price expectation** | Lower (operational convenience) | Higher (information is inherently valuable) |

---

## Trust & Neutrality

OS Hub does not rank, rate, or editorialize on service providers. The platform remains neutral. Trust signals are factual and crowd-sourced:

- Is the document **digitally signed** by the issuing organization?
- Did the **facility confirm** they hold this certification?
- Did the **service provider validate** the document?

The buyer decides what meets their standards. OS Hub is not the arbiter of trustworthiness.

---

## Key Data Per Document

Each certification or audit listing must display:

- **Expiration date** -- current vs. lapsed status (critical for buyer decision-making)
- **Scope** -- whole facility, specific product line, or specific process
- **Issuing / certifying body**
- **Issue date**
- **Document format** -- digitally signed PDF

---

## User Flows

### Flow 1: Individual Purchase

**Persona:** A compliance officer at a brand, on a facility's profile page, needs a specific audit report.

**Entry point:** Production location profile page, Spotlight / partner data section.

| Step | What happens |
|------|-------------|
| 1 | Buyer scrolls to Spotlight section and sees certifications and audits **available for purchase**, visually distinct from free data |
| 2 | Each purchasable item shows a **"What you'll receive"** summary: document format, delivery method (dashboard + email), approval steps, estimated timelines, and refund policy |
| 3 | Buyer clicks **"Request to Purchase"** and lands on a single transaction page showing document details, price, approval process, and notification preferences |
| 4 | **Payment via Stripe** -- funds held in escrow until approval completes |
| 5 | Request enters a **pending state** with a step-by-step visual tracker: |
| | -- Step 1: Payment received |
| | -- Step 2: Service provider reviews and approves (always required) |
| | -- Step 3: Facility confirms (sometimes required, depending on document type) |
| | -- Step 4: Document delivered |
| 6 | Buyer receives **email/SMS notifications** as status changes, with average response times displayed for each party |
| 7 | Once approved: **watermarked PDF** with buyer's name, organization, and date is available in their dashboard and delivered to their email |

### Flow 2: Bulk Purchase

**Persona:** A major brand's compliance team needs GOTS certificates for all 45 facilities in their Bangladesh supply chain.

**Entry point:** The existing search / filter page.

| Step | What happens |
|------|-------------|
| 1 | Buyer uses search to filter facilities by country, contributor, product type -- same as today |
| 2 | A new **filter checkbox** is available: **"Only show facilities with certifications available for purchase"** (similar to existing "shared facilities" checkbox) |
| 3 | Buyer applies filter -- sees refined results (e.g., 43 of 45 have purchasable GOTS certs) |
| 4 | Results clearly show which facilities have what. **Edge case:** "2 facilities in your list do not have this certification listed on OS Hub" -- with an option to request it from the service provider |
| 5 | Buyer selects facilities (individually or "Select All") and clicks **"Bulk Purchase Selected"** |
| 6 | Lands on a **bulk transaction page** showing all selected facilities, per-facility pricing, total cost, and what they'll receive |
| 7 | Each request fans out to service providers (and facilities where confirmation is required) **independently** |
| 8 | Buyer sees a **dashboard** tracking per-facility status. Documents arrive as they're approved -- no waiting for the full batch |
| 9 | Each document is watermarked to the buyer |

---

## Approval Model

The marketplace uses a **hybrid approval model**:

- **Instant access** -- the service provider has pre-approved open access for certain document types or buyer tiers
- **Approval required** -- the service provider (and possibly the facility) reviews who is buying before releasing the document
- **Example:** A provider may sell to Amazon's compliance team but decline to sell to a competing facility

If any party declines, the buyer receives a full refund for that specific document.

---

## Document Protection

**Approach: Watermarked PDFs (lightest touch)**

- Each delivered document is watermarked with the buyer's name, organization, and purchase date
- Documents are downloadable but traceable
- A **"Share Access"** feature encourages legitimate sharing: the buyer can grant a colleague access through OS Hub rather than forwarding the file
- Notice on each document: "This document is watermarked and traceable. Unauthorized distribution is prohibited."

This approach mirrors industry norms (SEDEX, Higg/Worldly) and creates accountability without heavy DRM.

---

## Payment

- Processed via **Stripe** (consistent with existing OS Hub premium products)
- Funds held in **escrow** until approval is complete
- Full refund on declined requests
- Pricing set by the service provider per document
- Bulk pricing model TBD (per document, volume discounts, subscription bundles)

---

## My Requests Dashboard

Buyers get a dashboard to track all their purchases:

- Document name, facility, service provider
- Status: Pending (Service Provider Review), Pending (Facility Confirmation), Completed
- Date requested
- Actions: Track Status, View Document
- Completed documents show "View Document" and "Download PDF" options

---

## Outstanding Questions

| Question | Notes |
|----------|-------|
| **Pricing model** | Per document? Subscription? Bulk discounts? Needs market research |
| **Revenue share with facilities** | Do facilities get a cut when their certifications are sold? What percentage? |
| **Service provider onboarding** | What does the seller-side experience look like? How do they list documents? |
| **Facility-side experience** | What does the facility see when asked to confirm? |
| **SLAs** | Can we contractually guarantee response times from service providers? |
| **UNTP conformity** | Natalie flagged this -- need to assess prototype against UNTP requirements once reference docs are reviewed |
| **API access** | Should bulk purchases be available via API for enterprise customers? |
| **Expired certifications** | Can buyers request a renewed version directly through the platform? |

---

## UNTP Assessment

**Status:** Pending. Reference documents on UNTP (UN Transparency Protocol) conformity requirements are being gathered. Once received, the prototype and product design will be evaluated against UNTP standards to determine whether this marketplace feature contributes to or enables UNTP conformity.

---

## Prototype

A fully clickable HTML prototype is available at:

**[https://tylerheath1.github.io/reports/prototypes/cert-marketplace-prototype.html](https://tylerheath1.github.io/reports/prototypes/cert-marketplace-prototype.html)**

The prototype covers all 7 screens across both user flows:

1. Facility Profile (with Spotlight / purchasable cert section)
2. Individual Transaction Page
3. Status Tracker (pending state with step-by-step progress)
4. My Requests Dashboard
5. Document Viewer (with watermark and digital signature)
6. Search & Filter (bulk flow with new certification filter)
7. Bulk Transaction Page

Use the purple "Prototype Navigation" panel in the bottom-right corner to jump between screens.

---

## Session Participants

This PRD was developed in a collaborative ideation session on April 16, 2026, with input from:

- Tyler Heath (facilitator)
- Natalie (product)
- Hannah (product)
- Basti (engineering perspective)
- Irem (standards/UNTP)
- Griffin (UX/search patterns)

AI (Claude) was used as a core part of the ideation, refinement, and prototyping process.
