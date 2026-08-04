# Connected Bay Area

### A Community Resource Access Data Audit

**Status:** In development  
**Observation date:** August 4, 2026

## Executive Summary

Bay Area counties use multiple organizations and online entry points to connect residents with 211 community resources. This project creates a nine-record, public-source dataset of county-level 211 access points, evaluates how consistently essential access information is published, and proposes a lightweight standardized record informed by the Human Services Data Specification (HSDS).

## Project Question

How consistently do Bay Area 211 entry points publish the information people and digital systems need to locate help, and how could a standardized data structure make that information easier to find and exchange?

## Why This Matters

Community-resource information may be accessed through websites, phone services, text services, and referral systems. Clear and consistently structured information can help people and digital systems determine where and how to begin searching for assistance.

HSDS provides a structure for exchanging machine-readable information about health, human, and social services. This project applies selected HSDS concepts to a small public-source dataset without claiming full HSDS compliance.

## Scope and Unit of Analysis

- **Geographic scope:** Nine Bay Area counties identified by the California Public Utilities Commission
- **Unit of analysis:** One county-level 211 access record
- **Information reviewed:** Public websites and publicly displayed access information
- **Observation date:** August 4, 2026
- **Excluded:** Individual client information, internal databases, referral outcomes, and service-quality evaluations

Some counties share the same lead organization or online access point. These relationships will be documented rather than automatically classified as duplicate records.

## Data Fields

The working dataset will document:

- County
- Lead organization
- Public access URL
- Phone access
- Text access
- Published availability
- Published language information
- Source URL
- Verification date
- Research notes

The final data dictionary will explain each field, its expected format, and its relationship to relevant HSDS concepts.

## Data-Quality Method

| Dimension | Project Check |
|---|---|
| Accuracy | Compare recorded values with the cited public source; no independent verification of service performance |
| Completeness | Determine whether each selected access field is publicly available |
| Uniqueness | Identify repeated records while preserving legitimate shared access points |
| Consistency | Compare naming, formatting, and access-channel descriptions across records |
| Timeliness | Record the observation date and note whether source-update information is displayed |
| Validity | Check whether values follow the expected field type or format |

## Planned Measures

The project will report separate measures rather than combine unrelated fields into one arbitrary score.

- **Field completion rate:** populated records ÷ 9 county records × 100
- **Source traceability rate:** records containing a source URL ÷ 9 × 100
- **Access-channel coverage:** records publishing each access channel ÷ 9 × 100
- **Language-information coverage:** records containing a public language statement ÷ 9 × 100

All reported percentages will include their numerator, denominator, and calculation.

## Project Deliverables

- `data/bay_area_211_access_points.csv` — structured public-source dataset
- `docs/data_dictionary.md` — field definitions and HSDS connections
- `sql/data_quality_checks.sql` — beginner-friendly SQL quality checks
- `docs/system_flow.md` — Mermaid diagram of the proposed information flow
- `findings.md` — results, limitations, and recommendations

## Reproducing the Review

When the project is complete, another user will be able to:

1. Review the data dictionary and source definitions.
2. Open the CSV dataset.
3. Import the dataset into SQLite or another SQL-compatible tool.
4. Run the documented quality-check queries.
5. Compare the query results with the published findings.

## Authoritative Sources and Standards

- [California Public Utilities Commission: Bay Area 211 Counties](https://www.cpuc.ca.gov/industries-and-topics/internet-and-phone/211-information-services/2-1-1-counties-in-the-bay-area)
- [211 Bay Area](https://211bayarea.org/)
- [Open Referral Human Services Data Specification](https://docs.openreferral.org/en/latest/hsds/overview.html)
- [Government Data Quality Framework](https://www.gov.uk/government/news/meet-the-data-quality-dimensions)

## Limitations

This is a limited review of information visible on public webpages at a specific point in time. It does not examine complete 211 resource databases, test referral outcomes, evaluate service providers, or establish formal HSDS conformance. Public information may change after the observation date.

## Independence

This is an independently developed portfolio project using publicly available information. It is not affiliated with or endorsed by any listed organization, service provider, government agency, or standards body.
