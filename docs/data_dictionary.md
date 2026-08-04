# Data Dictionary

## Dataset

`data/bay_area_211_access_points.csv`

## Unit of Analysis

Each row represents one Bay Area county-level 211 access record identified through the California Public Utilities Commission listing.

A shared website or lead organization may appear in multiple rows when it serves multiple counties. These repeated values are intentional and should not automatically be treated as duplicate records.

## Field Definitions

| Field | Definition | Format | Example | HSDS Connection |
|---|---|---|---|---|
| `record_id` | Unique identifier created for this project | Text | `BA211-001` | Conceptually related to an HSDS `id`; project IDs are not HSDS UUIDs |
| `county` | Bay Area county represented by the record | Text | `Alameda` | Related to `service_area` |
| `lead_entity` | Organization identified by the CPUC as the county’s 211 lead entity | Text | `Eden I&R, Inc.` | Related to `organization.name` |
| `access_url` | Public website used to access or search 211 information | HTTPS URL | `https://211alamedacounty.org/` | Related to a service URL or virtual location |
| `web_search_available` | Whether a public resource-search function was visible on the reviewed website | `Yes`, `No`, or `Not observed` | `Yes` | Project-specific access field |
| `phone_access` | Publicly displayed instruction for reaching 211 by phone | Text | `Dial 211` | Related to `phone` |
| `text_access` | Publicly displayed instruction for reaching 211 by text | Text | `Text ZIP code to 898211` | Related to a digital contact channel |
| `published_availability` | Availability statement displayed by the reviewed source | Text | `24/7` | Related to `schedule` |
| `published_language_information` | Public statement concerning languages, interpretation, or translated access | Text | `Available in multiple languages` | Related to `language` or `interpretation_services` |
| `primary_source_url` | CPUC source used to identify the county, lead entity, and website | HTTPS URL | CPUC Bay Area 211 listing | Related to provenance metadata |
| `secondary_source_url` | Public 211 website reviewed for access-channel information | HTTPS URL | `https://211bayarea.org/` | Related to provenance metadata |
| `verified_on` | Date the public information was reviewed for this project | `YYYY-MM-DD` | `2026-08-04` | Project observation date; not equivalent to provider assurance |
| `notes` | Context needed to interpret the record correctly | Text | `Shared United Way Bay Area access site` | Project-specific documentation field |

## Missing-Information Convention

`Not observed on reviewed landing page` means that the information was not found in the public landing-page content reviewed for this project.

It does **not** establish that the service, feature, or information is unavailable. The information may exist elsewhere on the website or through another access channel.

## Validation Rules

1. Every record must contain a unique `record_id`.
2. Every record must identify one county.
3. The dataset must contain nine county records.
4. URL fields must use a complete web address.
5. `verified_on` must follow the `YYYY-MM-DD` format.
6. Every record must contain both a primary and secondary source URL.
7. Shared organizations and URLs must remain documented when they legitimately serve multiple counties.
8. Missing information must use a descriptive value rather than an unsupported assumption.

## HSDS Use

The dataset is informed by selected concepts from the Human Services Data Specification, including organizations, service areas, contact methods, schedules, languages, and metadata.

This is not a complete HSDS implementation or formal conformance assessment. The project uses a simplified, single-table structure appropriate for a limited public-source portfolio analysis.

## References

- [California Public Utilities Commission: Bay Area 211 Counties](https://www.cpuc.ca.gov/industries-and-topics/internet-and-phone/211-information-services/2-1-1-counties-in-the-bay-area)
- [Open Referral: Human Services Data Specification](https://docs.openreferral.org/en/latest/hsds/overview.html)
