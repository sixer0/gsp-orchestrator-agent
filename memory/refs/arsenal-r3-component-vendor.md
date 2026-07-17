# ARSENAL R3 — Component Decomposition & Vendor Optimization Reference

> Date: 16 Juli 2026
> Source: `/Users/mbp/Documents/Project/ARSENAL/docs/2026-07-16_arsenal_component_vendor_research/`

## Component Taxonomy (10 Categories)

| # | Category | Enum | Local-Sourcable | TKDN Weight | Products |
|---|----------|------|----------------|-------------|----------|
| 1 | Core Module / Board | CORE_MODULE | Low (import) | 0% (CBU) | All electronics |
| 2 | Housing / Enclosure | HOUSING | HIGH | 15% | 20/22 products |
| 3 | Power Supply | POWER_SUPPLY | Hybrid | 5% | 20/22 products |
| 4 | Connectivity | CONNECTIVITY | Low (import) | 0% | 14 products |
| 5 | Processing | PROCESSING | Low (import) | 0% | 15 products |
| 6 | Storage | STORAGE | Low (import) | 0% | 8 products |
| 7 | Optics / Sensor | OPTICS_SENSOR | LOW (import) | 0% | 6 products |
| 8 | Software / Firmware | SOFTWARE_FIRMWARE | Hybrid (ARSA) | 25-50% | 7 products |
| 9 | Cables / Connectors | CABLES_CONNECTORS | HIGH | 5% / >=40% native | All products |
| 10 | Accessories | ACCESSORIES | Hybrid | 0-5% | All products |

## 6-Dimension Vendor Scoring

| Dim | Name | Weight | Method |
|-----|------|--------|--------|
| D1 | Base Price | 0.30 | FOB/CIF normalized 1-5 |
| D2 | Quality | 0.20 | MTBF, certs, warranty 1-5 |
| D3 | Customs | 0.15 | BM rate inverse normalized |
| D4 | Transport | 0.10 | Lead time + cost |
| D5 | Regulation | 0.15 | TKDN + SNI + Postel |
| D6 | Operational | 0.10 | Maintenance + spare parts |

Composite = 0.30*D1 + 0.20*D2 + 0.15*D3 + 0.10*D4 + 0.15*D5 + 0.10*D6

## TKDN 3-Track Model
- **Track A (Native):** Supreme Cable 91-95%, Indorack >=40%, LG 43.25%, SPC 47.86%
- **Track B (Rakitan Lokal):** enclosure 15% + PSU 5% + cable 5% + assembly 10% + QA 5% = 40%
- **Track C (Software/SDK Lokal):** ARSA Technology 25-40%, Sentinel Corp

## Product-Component Summary

| XX | Product | Components | Local | Import | Hybrid | TKDN |
|----|---------|-----------|-------|--------|--------|------|
| 01 | Cable | 7 | 5 | 0 | 2 | >=40% |
| 02 | NYFGbY Cable | 7 | 5 | 0 | 2 | >=40% |
| 03 | Standing Rack | 7 | 7 | 0 | 0 | >=40% |
| 04 | Router Board | 8 | 1 | 5 | 2 | 0-27% |
| 05 | ATS | 12 | 4 | 4 | 4 | >=30% |
| 06 | UPS 100kVA | 10 | 3 | 4 | 3 | 30-40% |
| 07 | Genset | 13 | 5 | 2 | 6 | ~40% |
| 08 | Network Switch | 8 | 1 | 4 | 3 | 0-30% |
| 09 | Storage Server | 12 | 1 | 7 | 4 | ~40% |
| 10 | PC Desktop | 11 | 0 | 7 | 4 | 5-10% |
| 11 | Thermal Camera | 18 | 2 | 10 | 6 | 15-25% |
| 12 | Thermal PIDS | 16 | 3 | 6 | 7 | ~55% |
| 13 | Deep Perimeter | 16 | 3 | 10 | 3 | 15-40% |
| 14 | Junction Camera | 15 | 3 | 7 | 5 | 40-50% |
| 15 | FR Platform | 18 | 2 | 8 | 8 | 25-45% |
| 16 | FR Camera | 15 | 2 | 9 | 4 | 40-50% |
| 17 | NVR | 14 | 1 | 8 | 5 | ~45% |
| 18 | Visitor Mgmt | 14 | 2 | 7 | 5 | 40-60% |
| 19 | Screen Wall | 12 | 4 | 3 | 5 | 43-47% |
| 20 | Video Wall Ctrl | 12 | 0 | 10 | 2 | ~9% |
| 21 | Sentinel | 12 | 0 | 10 | 2 | 25-65% (spec) |
| 22 | COFDM | 13 | 1 | 8 | 4 | ~15% |
| **TOTAL** | | **270** | **56** | **118** | **81** | **17/22 PASS** |

## Budget Impact

| Area | Savings |
|------|---------|
| Standardization (volume bundling) | Rp 570M-1.2B |
| Heimdal bypass (OEM direct) | Rp 10-15B |
| HDD surge avoidance | Rp 350-500M |
| **Total** | **Rp 10.6-17.2B** |

## Compliance Gaps
- **UU PDP:** 4 products (P13, P15, P16, P18) — DPIA + DPO mandatory
- **BSSN:** 3 products (P12, P13, P21) — certification unverified
- **Postel/SDPPI:** 8 products — certification unverified
- **TKDN exemption:** 5 products (P04, P07, P10, P20, P22)
