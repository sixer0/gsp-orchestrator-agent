# ARSENAL Product Research Reference (Riset 1 + 2)

## Project Overview
- **Project:** ARSENAL Intrusion Detection System — TNI AL
- **Location:** 337 hectares perimeter
- **Kontraktor:** PT Gemilang Satria Perkasa (GSP)
- **Partner:** Heimdal Defence Pte Ltd (Singapore)
- **Path:** `/Users/mbp/Documents/Project/ARSENAL/`

## Riset 1: Product Knowledge Base (2026-07-15)
- **Path:** `docs/2026-07-15_arsenal_product_knowledge_compilation/`
- **Purpose:** Kompilasi base knowledge 22 produk ARSENAL
- **Total GSP SPH:** ~Rp 65.37 Miliar
- **Key:** OEM identification, EOL detection, TKDN gap, pricing

## Riset 2: Product Alternative Research (2026-07-16)
- **Path:** `docs/2026-07-15_arsenal_product_alternative_research/`
- **Purpose:** Solve issue produk, cari alternatif, mapping kompetitor, rebrand/enhancement
- **Potential Savings:** Rp 32.6 Miliar (OEM Direct)
- **Key:** 22 alternatif teridentifikasi, dual-track recommendation, TKDN roadmap

## OEM Rebrand Pattern (CONFIRMED)
```
Chinese Manufacturer (Uniview/Dahua/Brovotech/DingShen/Norden/Future Vision)
    ↓ FOB / White-label
Singapore Distributor (Heimdal Defence Pte Ltd)
    ↓ Import + Rebrand
Local Integrator (PT Gemilang Satria Perkasa)
    ↓ Bundling + Enhancement
TNI AL End User
```
**Markup Range:** 2-38× (tergantung kompleksitas integrasi)

## Critical Issues Tracker

| Issue | Status | Action Required |
|-------|--------|-----------------|
| P21 Sentinel BLACKOUT | CAUTION | Request datasheet dari GSP/Heimdal |
| UU PDP P13/P15/P16/P18 | UNDOCUMENTED | DPIA + DPO + consent mechanism |
| TKDN 0% (17/22) | GAP | Exemption pathway + 5-year roadmap |
| P20 base chassis only | WARNING | Verify pricing dengan I/O boards |
| HDD surge +46% | MARKET | Lock prices immediately |

## Top-5 Savings Opportunities

| Rank | Produk | Savings | Method |
|------|--------|---------|--------|
| 1 | P16 FR Camera (141u) | Rp 9.0B | OEM Direct Brovotech |
| 2 | P11 Thermal Camera (61u) | Rp 7-11B | Hybrid deployment |
| 3 | P15 FR Platform | Rp 5.8B | OEM Direct Dahua |
| 4 | P13 Deep Perimeter | Rp 3.6B | OEM Direct Uniview |
| 5 | P12 Thermal PIDS | Rp 3.5B | OEM Direct Dahua |

## TKDN Compliance Pathway

| Year | Target | Products |
|------|--------|----------|
| Y0 (2026) | 5/22 (22.7%) | P01, P02, P05, P08-AT, P19-LG |
| Y1 (2027) | 10/22 (45.5%) | +P06-ICA, P09-hybrid, P14-SPC, P17-hybrid, P03-lokal |
| Y2 (2028) | 14/22 (63.6%) | +P16-assembly, P11-assembly, P08-AT, P10-Lenovo |
| Y3 (2029) | 18/22 (81.8%) | +P12-hybrid, P13-hybrid, P15-hybrid, P18-lokal |
| Y4 (2030) | 20/22 (90.9%) | +P04-local, P21-local |
| Y5 (2031) | Full | P07, P22 |

## Documentation Structure
```
docs/
├── README.md                                              ← TOP INDEX
├── 2026-07-15_arsenal_product_knowledge_compilation/
│   ├── README.md                                          ← Riset 1 index
│   ├── report/report.md                                   ← Riset 1 report
│   └── implementation/02_category_*.md                    ← 22 produk base knowledge
└── 2026-07-15_arsenal_product_alternative_research/
    ├── README.md                                          ← Riset 2 index
    ├── report/report.md                                   ← Riset 2 report
    └── implementation/
        ├── 01_product_alternatives.md                     ← 22 produk alternatif
        ├── 02_competitor_mapping.md                       ← Vendor map
        ├── 03_rebrand_enhancement.md                      ← TKDN strategy
        └── 04_synthesis.md                                ← Sintesis
```
