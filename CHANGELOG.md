# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.2] - 2026-05-07

### Fixed

- **RE1011, RE1012**: Fixed Python code from `esdc.cumprod['ga/gn']['net']` to `['sls']` to match "Sales" title and formula.
- **RE1020**: Fixed Python code from `esdc.cumprod['oil']['net']` to `['gn']['net']` to match "Non Associated Gas Net" title.
- **RE1017–RE1020**: Added Notes: _Not Implemented_ for Net Cumprod rules.
- **RE1029**: Fixed tautological formula `$N_{ps} \leq N_{ps}$` to `$N_{ps} \leq N_{pg}$`.
- **RE1044**: Fixed formula variable from `$q_{a, t}^{\text{tp}}$` to `$q_{n, t}^{\text{tp}}$` to match "Non Associated Gas" title.
- **RE1033–RE1036, RE1045–RE1046**: Fixed set notation range from `$\lbrace t_R + 1, \dots, t_R + m/n \rbrace$` to `$\lbrace t_R + 1, \dots, t_m \rbrace$`.
- **RE1037–RE1044**: Fixed summation upper bound from `$m$` to `$t_m$` to match References.md symbol definition.
- **RE1037–RE1044**: Fixed subscript inconsistency: removed comma in `$N_{p, s}$` → `$N_{ps}$`, `$G_{p, n}$` → `$G_{pn}$`, etc.
- **RE1035**: Fixed title capitalization "for each year" → "For each year".
- **RE1036**: Fixed double space in title.
- **RE1043**: Fixed double space "Associated  Gas" → "Associated Gas".
- **RE1038, RE1042, RE1043**: Fixed superscript spacing consistency from `$c\text{ 2P}$` to `$c \text{2P}$`.

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
