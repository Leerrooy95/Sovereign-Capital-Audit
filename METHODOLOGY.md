# Research Methodology

## Overview

This investigation employs OSINT (Open Source Intelligence) methodology with emphasis on timeline correlation analysis, regulatory gap assessment, and multi-source verification. The research prioritizes documented facts over speculation and maintains explicit distinctions between correlation and causation.

---

## Analytical Framework

### Evidence Classification System

All findings are classified into three tiers:

**Tier 1: Documented Fact**
- Verified through primary sources
- Examples: SEC filings, government contract awards, official press releases
- Confidence: High
- Notation: Stated directly without qualification

**Tier 2: Verified Correlation**
- Statistical relationship established through temporal or quantitative analysis
- Requires minimum two independent data points
- Confidence: Medium
- Notation: "correlates with," "coincides with," "r=X.XX"

**Tier 3: Analytical Interpretation**
- Framework for understanding documented patterns
- Based on aggregated Tier 1 and Tier 2 findings
- Confidence: Analytical (not predictive)
- Notation: "suggests," "indicates pattern of," "consistent with hypothesis"

---

## Source Hierarchy

Sources are weighted according to reliability and verifiability:

### Primary Sources (Highest Weight)
1. SEC filings (10-K, 10-Q, 8-K, Schedule 13D/G)
2. Government contract databases (FPDS, USAspending.gov)
3. Congressional committee reports and testimony
4. CFIUS decisions and Commerce Department announcements
5. Official company investor presentations

### Secondary Sources (Verification Required)
1. Financial journalism (Bloomberg, WSJ, Reuters, Financial Times)
2. Defense trade publications (Defense News, Breaking Defense)
3. Semiconductor industry analysis (SemiAnalysis, Asianometry)
4. Court filings and legal documents

### Tertiary Sources (Context Only)
1. Opinion journalism
2. Social media statements
3. Anonymous sourcing (noted explicitly)

---

## Timeline Correlation Methodology

### Construction
1. Events are logged with ISO 8601 date formatting
2. Each entry requires:
   - Date (verified to available precision)
   - Entity (primary subject)
   - Event description (factual, non-interpretive)
   - Source (URL or document reference)
   - Dataset layer classification

### Correlation Analysis
- Temporal proximity alone does not establish causation
- Correlations require:
  - Documented mechanism (how could A cause B?)
  - Directional logic (does timeline support causation?)
  - Alternative explanation assessment
- Statistical correlations (r-values) require minimum n=10 data points

### Pattern Recognition
- Patterns are identified through:
  - Frequency analysis (how often does X precede Y?)
  - Entity network mapping (who connects to whom?)
  - Financial flow tracing (where does money originate/terminate?)
- Patterns are labeled as "observed" until mechanism is verified

---

## Narrative Analysis Standards

### Media Divergence Mapping
The Washington Post vs. Washington Times comparative analysis follows these protocols:

1. **Selection Criteria**: Articles must reference the same event or entity within 30-day windows
2. **Coding Categories**:
   - Tone: Adversarial, Neutral, Supportive, Triumphant
   - Frame: Scandal, Efficiency, Threat, Builder, Patriot
   - Attribution: Direct quotes vs. editorial characterization
3. **Divergence Score**: Calculated as categorical distance between outlet framings
4. **Significance Threshold**: Systematic divergence requires 70%+ consistency across subject's coverage

---

## Verification Protocols

### Cross-Verification Requirements
- Financial figures require minimum 2 independent sources
- Ownership percentages require SEC or equivalent regulatory filing
- Contract values require government database confirmation
- Personnel connections require official announcement or filing

### Red Flags Requiring Additional Verification
- Single-source claims
- Anonymous sourcing
- Figures cited only in opinion pieces
- Claims contradicting established corporate structure

---

## Limitations and Biases

### Acknowledged Limitations

**Data Availability**
- Private equity and venture capital structures often lack transparency
- Classified government contracts cannot be verified
- Non-US regulatory filings may not be accessible

**Geographic Scope**
- Primary focus on U.S., Saudi Arabia, UAE, China, Japan
- Limited coverage of Southeast Asia, Europe, Latin America

**Temporal Scope**
- Primary analysis: 2015-2025
- Historical context: 2002-2014 (less granular)
- Forward projections: 2025-2029 (analytical, not predictive)

**Media Sample**
- 106 events across 2 outlets for 4 subjects
- Does not claim comprehensive media landscape coverage

### Potential Biases

**Selection Bias**: Events selected for timeline may overrepresent dramatic or controversial moments

**Confirmation Bias Mitigation**: 
- Actively search for counter-evidence
- Document findings that contradict working hypotheses
- Maintain "unresolved questions" section

**Survivorship Bias**: Companies/transactions that failed may be underrepresented

---

## Ethical Standards

### Non-Accusatory Presentation
- Findings present documented patterns, not criminal accusations
- Language avoids implying illegal activity without court verification
- Distinction maintained between "appears to" and "demonstrates"

### Privacy Considerations
- Public figures analyzed in public capacity only
- Private individuals mentioned only when directly relevant to documented transactions
- No speculation about personal motivations

### Correction Protocol
- Errors identified post-publication will be corrected with version notation
- Original text preserved with strikethrough
- Correction date and nature documented

---

## Dataset Quality Control

### Entry Validation
Each dataset entry undergoes:
1. Date verification (is the date accurate?)
2. Source check (does the source exist and support the claim?)
3. Entity standardization (is naming consistent?)
4. Duplicate detection (is this entry already captured?)

### Periodic Audits
- Monthly review of 10% random sample
- Quarterly reconciliation against updated source material
- Annual comprehensive methodology review

---

## Reproducibility

All analyses can be reproduced by:
1. Accessing the raw CSV datasets
2. Applying the filtering/correlation methods described
3. Following the source hierarchy for verification

No proprietary tools or non-public data are required to verify findings.

---

*Last Updated: February 2026*
