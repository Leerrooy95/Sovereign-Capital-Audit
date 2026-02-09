# Contributing Guidelines

Thank you for your interest in contributing to this research project. This document outlines the standards and processes for contributing data, analysis, or corrections.

---

## Types of Contributions

### 1. Data Corrections
If you identify factual errors in the datasets:
- Open an issue with the label `correction`
- Provide the specific row/entry containing the error
- Include primary source documentation for the correct information
- Reference the source hierarchy in METHODOLOGY.md

### 2. New Data Entries
If you have documented events that should be included:
- Ensure the event meets the relevance criteria (see below)
- Format the entry according to DATA_DICTIONARY.md schema
- Provide primary source verification
- Submit via pull request to the `data/` directory

### 3. Analysis Contributions
If you have analytical insights based on the data:
- Reference specific dataset entries supporting your analysis
- Maintain the Tier 1/2/3 evidence classification system
- Distinguish clearly between correlation and causation
- Submit to the `analysis/` directory

### 4. Source Verification
If you can verify or challenge existing sources:
- Archive.org links for articles behind paywalls
- Alternative sources for cross-verification
- Government database confirmations

---

## Relevance Criteria

New data entries should meet at least one of the following criteria:

1. **Entity Relevance**: Involves a tracked entity (see Primary Entities in README)
2. **Temporal Relevance**: Falls within 2015-2025 primary window (or provides historical context)
3. **Thematic Relevance**: Relates to:
   - Sovereign wealth investment in U.S. tech/defense
   - CFIUS/regulatory actions
   - Defense technology contracting
   - Media framing of tracked entities
   - China technology penetration of allied markets

---

## Formatting Standards

### Dataset Entries

```csv
Master_Date,Master_Entity,Master_Text,Master_Source,Dataset_Type
2025-06-15,GlobalFoundries,"Event description here...",https://source-url.com,News Article
```

### Date Formatting
- Use ISO 8601: `YYYY-MM-DD` or `YYYY` for year-only
- Do not use relative dates ("last month")

### Entity Naming
- Use canonical names from DATA_DICTIONARY.md
- If entity is new, propose standardized name in PR description

### Source URLs
- Full URL including https://
- Archive.org backup URL preferred for paywalled content

---

## Review Process

1. **Initial Review**: Maintainer checks formatting compliance
2. **Source Verification**: Primary source confirmed accessible and accurate
3. **Relevance Assessment**: Entry meets thematic/temporal criteria
4. **Integration**: Merged into appropriate dataset

Timeline: Reviews typically completed within 7 days.

---

## Evidentiary Standards

All contributions must adhere to the evidentiary standards in METHODOLOGY.md:

- **No speculation**: Claims must be sourced
- **No accusation**: Present patterns, not guilt
- **Correlation ≠ causation**: Maintain distinction explicitly
- **Multi-source preference**: Financial figures require 2+ sources

---

## What We Don't Accept

- Unverified claims from social media
- Anonymous tips without documentation
- Speculative analysis without data foundation
- Content that makes criminal accusations without court records
- Personally identifiable information about private individuals

---

## Communication

- **Issues**: For corrections, questions, or discussion
- **Pull Requests**: For data/analysis contributions
- **Discussions**: For methodology questions or broader topics

---

## Acknowledgment

Significant contributors will be acknowledged in the repository. All contributions remain subject to the MIT License.

---

*Last Updated: February 2026*
