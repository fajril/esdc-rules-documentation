# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.1] - 2026-05-06

### Fixed

- **RE0006**: Fixed title wording "less or equal than" to "less than or equal to".
- **RE0003, RE0004, RE0005, RE0006**: Fixed formulas using strict inequality (`<`) to use non-strict (`\leq`) to match titles and code.
- **RE0015**: Fixed RHS formula subscript from `\Delta N_{p}^{\text{P50}}` to `\Delta N_{pn}^{\text{P50}}`.
- **RE0025**: Fixed tautological formula `\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 1P}}` to `\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 2P}}`.
- **RE0042**: Fixed title from "Associated Gas Reserves" to "Non Associated Gas Reserves" to match formula and code.
- **RE0043–RE0048**: Fixed subscript/superscript order in formulas from `$X^{\text{Pxx}}_{\text{prj}}` to `$X_{\text{prj}}^{\text{Pxx}}`.
- **RE0052**: Fixed title from "Non Associated Reserves" to "Non Associated Gas Reserves".
- **RE0053–RE0058**: Fixed titles:
  - Changed "Sales Cummulative Production" / "Cummulative Production" to "Gross Cumulative Production".
  - Fixed "Cummulative" spelling to "Cumulative".
  - RE0055 title: "IOIP Middle Value" corrected to "IOIP High Value".
  - RE0058 title: "IGIP Middle Value" corrected to "IGIP High Value".
- **RE0053–RE0058**: Fixed formulas:
  - Changed `$N_{proj}` / `$G_{proj}` to `$N_{\text{prj}}` / `$G_{\text{prj}}` for consistency.
  - Changed undefined `$N_{p,n,t}` / `$G_{p,n,t}` to existing notation `$N_{pg}` / `$G_{pg}` (Gross Cumulative Production).
- **RE0008**: Fixed Python code from `esdc.resources['oil']` to `esdc.resources['con']` to match title "Condensate GRR/CR/PR" and formula.
- **References.md**:
  - Added subscript `\text{prj}` for Project IOIP and IGIP symbols.
  - Fixed `$G_{pg}^a$` definition from "Net" to "Gross" Cumulative Production.

## [1.0.0] - 2026-05-06

### Added

- Initial release of eSDC Rules Documentation.
- Volumetric rules (RE0) covering IOIP, IGIP, GRR/CR/PR, Reserves, and project-level validation.
- Symbol, keyword, syntax, maturity level, and geological chance factor references.
