# Data Dictionary

This document provides comprehensive schema documentation for all datasets in this repository.

---

## Final_Master_Dataset_Optimized.csv

**Purpose:** Unified intelligence timeline combining multiple data sources into a single queryable format.

**Records:** 2,152 rows  
**Time Horizon:** 2002-2029 (Primary focus: 2015-2025)

### Schema

| Column | Type | Description | Example Values |
|--------|------|-------------|----------------|
| `Master_Date` | String | Unified timeline key in YYYY-MM-DD or YYYY format | `2015-07-29`, `2015` |
| `Master_Entity` | String | Primary subject of the entry | `Elon Musk`, `Peter Thiel`, `GlobalFoundries`, `China (State)` |
| `Master_Text` | String | Core intelligence content—event description, news excerpt, or log entry | Full text of news headline and excerpt |
| `Master_Source` | String | Origin of the data—URL, PDF filename, or document title | `https://www.washingtonpost.com/...`, `GlobalFoundries_Audit.pdf` |
| `Dataset_Type` | String | Layer classification for filtering and analysis | See Dataset Types below |

### Dataset Types (Layers of Control)

| Type | Entries | Function |
|------|---------|----------|
| `System Log` | ~150 | "Control" timeline—China's state-driven AI/military/infrastructure advances |
| `Narrative Analysis` | ~124 | "Media" timeline—comparative framing analysis during critical windows |
| `Regulatory Intelligence` | 6 | "Smoking Gun" entries—specific loopholes and ownership structures |
| `News Article (Full)` | ~1,800 | "Noise"—full-text supporting documentation and raw source material |
| `News Article` | Variable | Abbreviated news entries without full text |

### Entity Standardization

Entities are standardized to the following canonical names:

**Individuals:**
- `Elon Musk`
- `Peter Thiel`
- `Larry Ellison`
- `David Ellison`
- `Donald Trump`
- `Jared Kushner`

**State Actors:**
- `China (State)` — For PRC government actions
- `China (PLA)` — For military-specific actions
- `Saudi Arabia` — For Kingdom-level actions
- `UAE` — For Emirati state actions
- `Russia` — For Russian state actions

**Corporate Entities:**
- `GlobalFoundries`
- `Oracle`
- `Palantir`
- `Anduril`
- `xAI`
- `SoftBank`
- `Mubadala`
- `PIF` — Saudi Public Investment Fund
- `G42`
- `HUMAIN`

**Investment Vehicles:**
- `Founders Fund`
- `Affinity Partners`
- `Sanabil Investments`
- `Vision Fund`

---

## Merged_Master_Dataset.csv

**Purpose:** Extended news article collection with full metadata.

**Records:** 2,343 rows  
**Time Horizon:** 2015-2025

### Schema

| Column | Type | Description |
|--------|------|-------------|
| `Master_Date` | String | Event date (YYYY or YYYY-MM-DD) |
| `Master_Entity` | String | Primary subject |
| `Master_Text` | String | Full article excerpt or headline |
| `Master_Source` | String | Source URL |
| `Dataset_Type` | String | Entry classification |

### Notes
- This dataset contains more raw news article entries than the optimized version
- May contain duplicate events with different source coverage
- Useful for comprehensive source verification

---

## Compiled_Data.csv

**Purpose:** Comparative media analysis mapping editorial divergence between The Washington Post and The Washington Times.

**Records:** 233 rows  
**Time Horizon:** 2015-2025  
**Subjects:** Trump, Musk, Ellison Family, Thiel

### Schema

| Column | Type | Description | Example Values |
|--------|------|-------------|----------------|
| `Unified_Date` | String | Event date (YYYY-MM-DD) | `2015-01-08` |
| `Person` | String | Subject of coverage | `Peter Thiel`, `Elon Musk`, `Ellison Family`, `Donald Trump` |
| `Outlet` | String | Publication source | `Washington Post`, `Washington Times`, `Multiple Sources` |
| `Unified_Narrative` | String | Comparative framing summary | `WaPo: Scandalous; WashTimes: Triumphant` |
| `Unified_Tone` | String | Editorial positioning classification | See Tone Categories below |

### Tone Categories

| Tone | Description | Typical Outlet |
|------|-------------|----------------|
| `Adversarial` | Critical framing, emphasis on scandal/threat | Washington Post |
| `Triumphant` | Celebratory framing, emphasis on achievement | Washington Times |
| `Neutral / Pragmatic` | Factual reporting without strong editorial positioning | Both |
| `Vindicated` | Framing subject as having been proven correct | Washington Times |
| `Scandalous` | Emphasis on ethical violations or corruption | Washington Post |
| `Strategic` | Focus on political/business strategy | Both |
| `Restorative` | Framing as returning order or tradition | Washington Times |

### Divergence Analysis Notes

Entries with `Outlet: Multiple Sources` contain comparative summaries of both outlets' coverage of the same event. These entries use the format:

```
WaPo Narrative: [summary] | WashTimes Narrative: [summary]
```

---

## Data Quality Notes

### Date Precision
- Year-only dates (`2015`) indicate events where exact date is unavailable or aggregated
- Full dates (`2015-07-29`) are verified to that precision
- Future dates (2026-2029) are projections from official announcements, not predictions

### Text Encoding
- All files use UTF-8 encoding
- Some entries may contain escaped characters from source scraping
- Quotation marks are standardized to ASCII double quotes

### Missing Values
- Empty cells indicate data not available or not applicable
- `N/A` is used for explicitly unavailable data (e.g., Kushner fund returns)
- `Unspecified` in tone columns indicates insufficient data for classification

### Source URL Validity
- URLs verified at time of data collection
- Some URLs may have become unavailable (paywalls, site changes)
- Archive.org backups recommended for critical sources

---

## Usage Examples

### Filter by Entity (Python/Pandas)
```python
import pandas as pd
df = pd.read_csv('Final_Master_Dataset_Optimized.csv')
thiel_entries = df[df['Master_Entity'] == 'Peter Thiel']
```

### Filter by Dataset Layer
```python
regulatory = df[df['Dataset_Type'] == 'Regulatory Intelligence']
```

### Date Range Query
```python
df['Master_Date'] = pd.to_datetime(df['Master_Date'], errors='coerce')
period = df[(df['Master_Date'] >= '2020-01-01') & (df['Master_Date'] <= '2022-12-31')]
```

### Narrative Divergence Analysis
```python
compiled = pd.read_csv('Compiled_Data.csv')
thiel_coverage = compiled[compiled['Person'] == 'Peter Thiel']
wapo = thiel_coverage[thiel_coverage['Outlet'] == 'Washington Post']
washtimes = thiel_coverage[thiel_coverage['Outlet'] == 'Washington Times']
```

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| v3 | December 2025 | Added international layer (Japan, SoftBank, China surge data) |
| v2 | November 2025 | Integrated narrative divergence analysis |
| v1 | October 2025 | Initial dataset with core entity timelines |

---

*Last Updated: February 2026*
