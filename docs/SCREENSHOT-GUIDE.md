# Screenshot publishing guide

The current SVGs are fictional UI reconstructions, and the PNGs are high-fidelity anonymized reconstructions based on the supplied production screen references. Keep them as portfolio visuals unless the client approves a sanitized production capture for public use.

## Recommended set

| File | Capture | What it demonstrates |
| --- | --- | --- |
| `01-program-discovery.webp` | Public course/program page | Responsive UI, content hierarchy, calls to action |
| `03-teacher-workspace.webp` | Attendance or progress screen | Role-specific operational design |
| `04-admin-operations.webp` | Admin dashboard/list using demo records | CMS and workflow breadth |
| `05-showcase.webp` | Public project gallery | Media presentation and verified voting entry point |
| `06-mobile-enrollment.webp` | Mobile enrollment step | Responsive form and conversion flow |

## Current portfolio reconstructions

| File | Demonstrates |
| --- | --- |
| `05-operations-dashboard.png` | Senior operations dashboard, KPI cards, global search, and demo funnel |
| `06-showcase-results.png` | Voting state, moderation KPIs, ranked results, award controls, and exports |
| `07-demo-bookings-conversion.png` | Booking funnel, conversion/attendance rates, filters, statuses, and next actions |

## Capture standard

- Use a 16:9 viewport, ideally 1440 × 810 or 1600 × 900.
- Populate the environment with synthetic names, emails, phone numbers, dates, IDs, and project content.
- Remove the real logo, company name, domain, location, and social links.
- Hide browser tabs, bookmarks, extensions, notifications, and local file paths.
- Prefer WebP at 80–88 quality and keep each image below about 700 KB.
- Use a consistent crop and avoid adding heavy device frames.
- Add concise alt text describing the screen and the engineering value.

## Mandatory privacy review

Zoom to 200% and inspect every area for:

- Student or parent information
- Email addresses, phone numbers, and postal addresses
- Avatars or identifiable photographs
- Internal record IDs, QR codes, and barcodes
- Private URLs, tenant names, and environment labels
- Analytics, revenue, enrollment totals, or other confidential metrics
- Browser chrome, notifications, and developer-tool output

Cropping or replacing data is preferable to blur. Blur can sometimes be reversed or leave enough context to identify a person. Keep the original captures outside this repository.

## Updating the README

The README currently highlights the three PNG reconstructions because they better represent the production-level complexity of this delivery. If approved WebP captures are added later, replace the PNG links only after the privacy review. Keep the SVG reconstructions as lightweight fallback visuals.
