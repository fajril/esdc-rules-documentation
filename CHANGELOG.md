# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.1] - 2026-05-08

### Fixed

#### RE0 - Volumetric
- **RE0003, RE0004, RE0005, RE0006**: Fixed formulas using strict inequality (`<`) to use non-strict (`\leq`) to match titles and code.
- **RE0006**: Fixed title wording "less or equal than" to "less than or equal to".
- **RE0008**: Fixed Python code from `esdc.resources['oil']` to `esdc.resources['con']` to match title "Condensate GRR/CR/PR" and formula.
- **RE0015**: Fixed RHS formula subscript from `\Delta N_{p}^{\text{P50}}` to `\Delta N_{pn}^{\text{P50}}`.
- **RE0025**: Fixed tautological formula `\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 1P}}` to `\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 2P}}`.
- **RE0042**: Fixed title from "Associated Gas Reserves" to "Non Associated Gas Reserves" to match formula and code.
- **RE0049**: Fixed formula from `ΔG_ps` (Non Associated Gas) to `ΔN_ps` (Oil) to match title "Oil Reserves". Replaced invalid `\u003e` Unicode escape with `>`.
- **RE0043–RE0048**: Fixed subscript/superscript order in formulas from `$X^{\text{Pxx}}_{\text{prj}}` to `$X_{\text{prj}}^{\text{Pxx}}`.
- **RE0043–RE0048**: Added missing index `i` to summation symbol (`N_{\text{prj}}` → `N_{\text{prj},i}`, `G_{\text{prj}}` → `G_{\text{prj},i}`).
- **RE0052**: Fixed title from "Non Associated Reserves" to "Non Associated Gas Reserves".
- **RE0053–RE0058**: Fixed titles and formulas:
  - Changed "Sales Cummulative Production" / "Cummulative Production" to "Gross Cumulative Production".
  - Fixed "Cummulative" spelling to "Cumulative".
  - RE0055 title: "IOIP Middle Value" → "IOIP High Value".
  - RE0058 title: "IGIP Middle Value" → "IGIP High Value".
  - Changed `$N_{proj}` / `$G_{proj}` to `$N_{\text{prj}}` / `$G_{\text{prj}}` for consistency.
  - Changed undefined `$N_{p,n,t}` / `$G_{p,n,t}` to existing notation `$N_{pg}` / `$G_{pg}` (Gross Cumulative Production).
- **References.md**:
  - Added subscript `\text{prj}` for Project IOIP and IGIP symbols.
  - Fixed `$G_{pg}^a$` definition from "Net" to "Gross" Cumulative Production.

#### RE1 - Production and Forecast
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

#### RE2 - Material Balance
- **RE2001–RE2012**: Fixed typo "discprepancies" → "discrepancies" in 12 rule titles.
- **RE2001–RE2004**: Fixed Python code sign error: `+ prod` → `- prod` for 1R/1C/1U consistency rules.
- **RE2003, RE2007, RE2011**: Fixed Python code fluid type `['con']` → `['ga']` for Associated Gas `wi` discrepancy.
- **RE2004, RE2008, RE2012, RE2029, RE2030**: Fixed extra space in P-level superscripts (`^{\text{ P90}}` → `^{\text{P90}}`, etc.).
- **RE2002, RE2006, RE2010**: Fixed Python code using `'ga'` (Associated Gas) for Well Intervention discrepancy in Condensate rules — changed to `'con'`.
- **RE2001–RE2012**: Added missing `cio` (Consumed in Operations) discrepancy term to Python code for all 12 GRR/CR/PR material balance rules. The formulas already included `cio`; only the Python code was missing it.
- **RE2022**: Fixed formula P-level from P50 to **P10** to match "3P" title (code already correct).
- **RE2024**: Rewrote entire rule for **Non Associated Gas** (was erroneous copy of RE2023/Associated Gas).
- **RE2027–RE2028**: Updated Python code to include `cumprod` in EUR sum check, matching formula.
- **RE2028**: Fixed Python code fluid type `['gn']` → `['ga']` for Associated Gas resources check.
- **RE2030**: Fixed typo "IOIP Low" → "IGIP Low" in example block.
- **RE2001–RE2030**: Standardized subscripts: removed commas in `$N_{p,n,t}$` → `$N_{pn,t}$`, `$G_{p,s,t}$` → `$G_{ps,t}$`, etc.
- **RE2001–RE2030**: Fixed superscript spacing for fluid modifiers (`$c\text{P90}$` → `$c \text{P90}$`, `$a\text{P50}$` → `$a \text{P50}$`).

#### References.md
- Added `uc` = **Unaccounted Changes** to syntax reference table.
- Added 4 `uc` discrepancy symbols to Symbol Reference.
- Fixed pre-existing typo: row for `\Delta D_{G^a}` under Well Intervention incorrectly used `gtr` superscript → corrected to `wi`.

#### RE5 - Maturity Level
- **RE5011**: Fixed missing `E_3` in set `M_s` and corrected fail example from `E3` to `E4`.
- **RE5012**: Fixed typo in fail example: `X1. Production on Hold` → `E1. Production on Hold`.
- **RE5014**: Added missing period in title: `E7 Production not Viable` → `E7. Production not Viable`.
- **RE5018**: Fixed subscript consistency: `M_{t - 2}` → `M_{t_R - 2}`.
- **RE5023**: Added missing comma in title between `X1` and `X4`.
- **RE5025**: Fixed set notation: `M_s = \lbrace M_E, X_0, \dots X_4 \rbrace` → `M_s = M_E \cup \lbrace X_0, \dots, X_4 \rbrace`.
- **RE5031**: Fixed title to match formula: "higher than" → "higher than or equal to".
- **RE5043**: Fixed formula by adding `> 0` predicate after summation to match title intent.
- **RE5050**: Fixed typo in title: "an Seal" → "and Seal".
- **RE5051**: Fixed title, formula subscript (`P_{g,d}` → `P_{g,m}`), and all examples ("Trap and Seal" → "Dynamic").
- **RE5053**: Fixed title to include `E0` in allowed levels, matching formula: added "E0. On Production" to the list.
- **RE5054**: Fixed implication direction: `(has reserves) \implies M \in M_s` → `M \in M_s \implies (has reserves)`.
- **RE5055**: Rewrote title and formula to form iff with RE5054: "Maturity levels E4 through X6 must not have 1P reserves". Changed set from `{E1,E2,E3}` to `{E4,...,X6}` and direction to `M ∈ M_s ⟹ reserves = 0`. Added note about iff relationship. Updated examples.
- **RE5059–RE5061**: Standardized subscript: `N_{\text{project}}` → `N_{\text{prj}}`.
- **RE5062–RE5064**: Standardized subscript: `G_{\text{project}}` → `G_{\text{prj}}`.
- **RE5065**: Fixed formula predicate (`= 0` → `> 0`), subscript (`project` → `prj`), and superscript spacing (`\text{ P10}` → `\text{P10}`).
- **RE5066**: Fixed implication direction and corrected `\empty` → `\emptyset`.
- **RE5068**: Fixed discrepancy sign from `q - ΔD` to `q + ΔD` to match RE2 material balance convention. Fixed example 1 label from "should fail" to "should pass".
- **RE5053**: Redesigned pass example to test rule's consequent directly (all resources P10 = 0, M = E7) instead of vacuously true.
- **RE5054**: Redesigned pass example to test rule's consequent directly (M = E1 with 1P > 0) instead of vacuously true.
- **RE5066, RE5067**: Changed symbol `$t_{act}$` to `$t_{ons}$` for consistency.
- **RE5069**: Restored missing `if` block in fail example.
- **RE5068**: Removed duplicate rule entry without title.

#### References
- Added A1 (Dry) and A2 (Dissolved) to Project Maturity Level table.
- Added 2R/2C/2U = P50 equivalence definition to Symbol Reference paragraph.
- Added `$t_{ons}$` (Onstream actual date) to Symbol Reference table.
- Added Discrepancy Applicability note explaining why reserves rules (RE2013–RE2024) only include `gtr` while GRR/CR/PR rules (RE2001–RE2012) include all five discrepancy types.

## [1.0.0] - 2026-05-06

### Added

- Initial release of eSDC Rules Documentation.
- Volumetric rules (RE0) covering IOIP, IGIP, GRR/CR/PR, Reserves, and project-level validation.
- Symbol, keyword, syntax, maturity level, and geological chance factor references.
