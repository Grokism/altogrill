# Altogrill — Bookins.io AI Application Blueprint

- **Organization:** Aitogrill
- **Live Origin:** `https://altogrill.apps.bookins.io`
- **Web Template / Archetype:** `small_business` (Small Business & Client Service Portal (Staff + Client PermSets))
- **Theme Palette:** `ocean_teal`
- **Generation Engine:** Bookins Role-Aware Archetype Compiler

---

## 1. Configured PermSet Generation Roles (No-Code Bookins Registry)

These roles are automatically registered on your Bookins.io client record (`collections.clients.permsetRoles`) and appear in **Bookins.io -> Add Permset -> Creation Mode** without requiring any code changes:

- **Staff Provider** (`roleKey: "staff"`, policy: `issuer_only`, scope tag: *Client / Project Code (e.g. proj-acme)*): Post project deliverables, service updates, and client milestones.
- **Verified Client** (`roleKey: "client"`, policy: `self_enroll`, scope tag: *Client / Project Code (e.g. proj-acme)*): View project deliverables, approve milestones, and submit service requests.

---

## 2. Web Template Questionnaire Answers

- **servicesOffered:** Initial Consultation & Space Planning — Tailored blueprint & project scope · Custom Project Delivery & Milestones — Dedicated weekly progress updates · Ongoing Support & Priority Care — Year-round maintenance & client support
- **businessHoursAndLocation:** Mon–Fri 8:30 AM – 5:30 PM · Serving Local & Remote Clients
- **primaryCtaText:** Track your project milestones, deliverables, and service requests with zero personal data exposure.
- **deliverableCategories:** Project Milestone, Deliverable Ready, Client Request, Schedule Update

---

## 3. Uploaded Brand & Image Assets (`src/assets/uploads/`)

- No custom image assets uploaded at provisioning time (add images to `src/assets/uploads/`).

---

## 4. Assembled Application Specification Prompt

```text
Build a full-stack MEAN + Nginx web application for "Altogrill" (Organization: "Aitogrill", Origin: https://altogrill.apps.bookins.io).

1. SELECTED WEB TEMPLATE & PURPOSE: Small Business & Client Service Portal (Staff + Client PermSets)
   - Headline: Altogrill — Client & Service Portal
   - Primary Goal: Give staff and clients a shared, zero-PII project and service portal where deliverables, status updates, and service requests are organized by Client / Project Code.
   - Theme Palette: ocean_teal

2. TEMPLATE QUESTIONNAIRE ANSWERS:
   - 1. What services or packages does your business offer?: Initial Consultation & Space Planning — Tailored blueprint & project scope | Custom Project Delivery & Milestones — Dedicated weekly progress updates | Ongoing Support & Priority Care — Year-round maintenance & client support
   - 2. Business Hours & Service Area / Location: Mon–Fri 8:30 AM – 5:30 PM · Serving Local & Remote Clients
   - 3. Primary Call-to-Action & Welcome Promise: Track your project milestones, deliverables, and service requests with zero personal data exposure.
   - 4. Member Workspace Categories (comma-separated): Project Milestone, Deliverable Ready, Client Request, Schedule Update

3. PERMSET PROTOCOL ROLES & ACCESS CONTROL:
   Every user must hold a public amihuman humanity badge plus one of these origin-scoped private PermSets (https://altogrill.apps.bookins.io):
  1. Staff Provider (roleKey: "staff", minting: Issuer-Only in Bookins.io Add Permset, scopeTag: "Client / Project Code (e.g. proj-acme)") — Post project deliverables, service updates, and client milestones.
  2. Verified Client (roleKey: "client", minting: Self-Enroll at /join or Admin Minted, scopeTag: "Client / Project Code (e.g. proj-acme)") — View project deliverables, approve milestones, and submit service requests.

4. KEY FEATURES & WORKSPACE BEHAVIOR (/home & /api/records):
   - Public service showcase with business hours, service menu, and client onboarding call-to-action
   - Staff PermSet workspace to post deliverables, service milestones, and scheduling updates
   - Client PermSet portal scoped by Client / Project Code to review work and submit requests
   - Isolated MongoDB persistence for project timelines and client approvals

5. UPLOADED BRAND & IMAGE ASSETS (src/assets/uploads/):
  - None uploaded yet (use clean CSS vector badges and cards)
```
