# Permian Data

Tracking TCEQ air permits in the Permian Basin (Ward, Reeves, Pecos, Loving, Culberson, Jeff Davis counties) tied to behind-the-meter (BTM) on-site power generation for data centers.

Permit data is extracted from TCEQ NSR air permits, TCEQ records, and Oil & Gas Watch. Full documentation is here:
https://docs.google.com/document/d/1sfSRWn85biFFcatyVwM2cZgxOc-LavWNXVXr4WsUOLQ/edit?usp=sharing

## Identified data center sites

Permits flagged as BTM on-site data centers, with site and generation details.

| Site Name | County | Capacity (MW) | Turbine / Engine | OEM | Status | Sources |
| --- | --- | --- | --- | --- | --- | --- |
| Circe Energy Data Centers E Monahans Campus | Ward | 400 | HSK78G | Cummins | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Featherwood Energies Pecos Plant | Reeves | 931 | SGT-800 | Siemens Energy | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Rock House Draw Generating Station | Pecos | 576 | TM2500 Gen 8, TM2500+ | General Electric | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Xenergy Monahans 1 | Ward | 118.98 | HSI6CP350NG, 16M33D1280NG11 | Baudouin | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Poolside Data Center Pecos County II | Pecos | 332.28 | TM2500 Gen 8, TM2500+ | General Electric | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Pecos Power Generation | Reeves | 478 | SGT-800 | Siemens Energy | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Kilby Power Plant | Reeves | 2869 | 7HA.02, Titan 350, Titan 130 | General Electric, Solar Turbines | Permitted | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| GW Ranch Energy Center | Pecos | 5000 | SGT-800 | Siemens Energy | Announced | TCEQ NSR Air Permit, TCEQ Records, Oil and Gas Watch |
| Alpha Digital Campus | Reeves | 2000 | N/A | N/A | Announced | LandBridge Press Release |
<<<<<<< Updated upstream
=======

## Repository structure

```
permian-data/
├── data-center-list.csv        # Curated output: permits identified as BTM on-site data centers
├── air-permits/                # Raw TCEQ NSR air-permit exports, grouped by permit type
│   ├── std/                    # Standard permits (STDPMT)
│   │   ├── air-permit-6-std.csv      # Region 06 (El Paso)
│   │   └── air-permit-7-std.csv      # Region 07 (Midland)
│   ├── psd/                    # Prevention of Significant Deterioration (PSD) permits
│   │   ├── air-permit-6-psd.csv      # Region 06 (El Paso)
│   │   └── air-permit-7-psd.csv      # Region 07 (Midland)
│   ├── ghgpsd/                 # Greenhouse-gas PSD (GHGPSD) permits
│   │   ├── air-permit-6-ghgpsd.csv   # Region 06 (El Paso)
│   │   └── air-permit-7-ghgpsd.csv   # Region 07 (Midland)
│   └── turbine-list.xlsx       # Reference list of turbine/engine models and OEMs
├── .ipynb/
│   └── permit_extraction.ipynb # Notebook that filters raw permits into data-center-list.csv
├── pyproject.toml              # Python dependencies
└── uv.lock                     # Locked dependency versions
```

The raw exports in `air-permits/` are split by **permit type** (`std`, `psd`, `ghgpsd`) and by **TCEQ region** (`6` = Region 06 / El Paso, `7` = Region 07 / Midland). The extraction notebook reads these, filters to Permian Basin counties and BTM on-site data centers, and produces `data-center-list.csv`.
