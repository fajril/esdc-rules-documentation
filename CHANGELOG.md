# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).


## [1.1.0] - 2026-05-10

### Added

- **RE0059–RE0066**: Added project-level in-place ordering rules to RE0 - Volumetric:
  - RE0059: Project IOIP P50 — must equal zero when P90 equals zero.
  - RE0060: Project IOIP P10 — must equal zero when P90 equals zero.
  - RE0061: Project IGIP P50 — must equal zero when P90 equals zero.
  - RE0062: Project IGIP P10 — must equal zero when P90 equals zero.
  - RE0063: Project IOIP P90 — must be less than or equal to P50.
  - RE0064: Project IOIP P50 — must be less than or equal to P10.
  - RE0065: Project IGIP P90 — must be less than or equal to P50.
  - RE0066: Project IGIP P50 — must be less than or equal to P10.
- **References.md**: Added naming convention for field-level vs project-level symbols and rule title qualifiers.

### Changed

- **RE0054**: Changed title from "Project IOIP Middle" to "Project IOIP P50".
- **RE0057**: Changed title from "Project IGIP Middle" to "Project IGIP P50".

## [1.0.1] - 2026-05-08

### Changed

- **RE0–RE5**: Removed all Python code blocks (202 blocks). Formulas are now the single source of truth for rule logic.
- **References.md**: Replaced `import esdc` API section with Formula-to-Database Column Mapping table, Data Source Reference table, and Conventions (time reference, aggregation).
- **References.md**: Added mapping from formula symbols to database column names covering In-Place, Resources, Reserves, Cumulative Production, Discrepancy, Forecast, and Maturity Level categories.
- **RE0002–RE0042, RE0049–RE0058**: Added `al` pass/fail examples to all RE0 rules that previously had none (51 rules, 102 example blocks).
- **RE0001, RE0002**: Fixed title wording from "positive or equal to 0" to "greater than or equal to zero".
- **RE0007–RE0014**: Fixed title wording from "higher than or equal to 0" to "greater than or equal to zero".
- **RE0049–RE0052**: Fixed title wording from "higher than zero" to "greater than zero".
- **RE0053–RE0058**: Fixed title wording from "higher than" to "greater than".
- **RE0001, RE0002**: Fixed `al` example capitalization: `oil in place` → `Oil in Place`, `gas in place` → `Gas in Place`.
- **RE0043–RE0048**: Fixed `al` example capitalization: `Validation result` → `validation result`.
- **RE0052**: Fixed extra leading space in P-level superscripts (`^{\text{ 3P}}` → `^{\text{3P}}`, `^{\text{ 1P}}` → `^{\text{1P}}`; renders identically).
- **RE1001–RE1012**: Fixed title wording from "positive or equal to 0" to "greater than or equal to zero".
- **RE1013–RE1024**: Fixed title wording from "Can only increase or equal to previous Cumprod" to "Must be greater than or equal to previous Cumprod".
- **RE1045, RE1046**: Fixed title wording from "should equal to" to "should be equal to".
- **RE1001–RE1046** (excluding RE1017–RE1020): Added `al` pass/fail examples to all implemented RE1 rules (42 rules, 84 example blocks).
- **RE2025–RE2030**: Fixed title wording from "higher than" to "greater than".
- **RE2029, RE2030**: Fixed `al` example capitalization: lowercase variables changed to Title Case, removed extra blank lines, restructured multi-block examples to consistent pass/fail pattern.
- **RE2001–RE2028**: Added `al` pass/fail examples to all RE2 rules that previously had none (28 rules, 56 example blocks).
- **RE2029, RE2030**: Restructured existing `al` examples from inconsistent multi-block format to consistent pass/fail pattern (2 blocks each, from 5 and 6 respectively).

### Fixed

#### RE0 - Volumetric
- **RE0003, RE0004, RE0005, RE0006**: Fixed formulas using strict inequality $<$ to non-strict $\leq$ to match titles and code.
- **RE0006**: Fixed title wording "less or equal than" to "less than or equal to".
- **RE0008**: Fixed formula fluid type from Oil to Condensate to match title "Condensate GRR/CR/PR".
- **RE0015**: Fixed RHS formula subscript from $\Delta N_{p}^{\text{P50}}$ to $\Delta N_{pn}^{\text{P50}}$.
- **RE0025**: Fixed tautological formula $\Delta N_{ps}^{c\,\text{1P}} \leq \Delta N_{ps}^{c\,\text{1P}}$ to $\Delta N_{ps}^{c\,\text{1P}} \leq \Delta N_{ps}^{c\,\text{2P}}$.
- **RE0042**: Fixed title from "Associated Gas Reserves" to "Non Associated Gas Reserves" to match formula and code.
- **RE0049**: Fixed formula from $\Delta G_{ps}$ (Non Associated Gas) to $\Delta N_{ps}$ (Oil) to match title "Oil Reserves". Replaced invalid `\u003e` Unicode escape with `>`.
- **RE0043–RE0048**: Fixed subscript/superscript order in formulas: `X^{\text{Pxx}}_{\text{prj}}` → `X_{\text{prj}}^{\text{Pxx}}` (LaTeX source order only; renders identically).
- **RE0043–RE0048**: Added missing index $i$ to summation symbol ($N_{\text{prj}}$ → $N_{\text{prj},i}$, $G_{\text{prj}}$ → $G_{\text{prj},i}$).
- **RE0052**: Fixed title from "Non Associated Reserves" to "Non Associated Gas Reserves".
- **RE0053–RE0058**: Fixed titles and formulas:
  - Changed "Sales Cummulative Production" / "Cummulative Production" to "Gross Cumulative Production".
  - Fixed "Cummulative" spelling to "Cumulative".
  - RE0055 title: "IOIP Middle Value" → "IOIP High Value".
  - RE0058 title: "IGIP Middle Value" → "IGIP High Value".
  - Changed $N_{proj}$ / $G_{proj}$ to $N_{\text{prj}}$ / $G_{\text{prj}}$ for consistency.
  - Changed undefined $N_{p,n,t}$ / $G_{p,n,t}$ to existing notation $N_{pg}$ / $G_{pg}$ (Gross Cumulative Production).
- **References.md**:
  - Added subscript $\text{prj}$ for Project IOIP and IGIP symbols.
  - Fixed $G_{pg}^{a}$ definition from "Net" to "Gross" Cumulative Production.

#### RE1 - Production and Forecast
- **RE1011, RE1012**: Fixed commerciality mapping from Net to Sales to match title and formula.
- **RE1020**: Fixed formula fluid type from Oil to Non Associated Gas and commerciality from Net to Sales.
- **RE1017–RE1020**: Added Notes: _Not Implemented_ for Net Cumprod rules.
- **RE1029**: Fixed tautological formula $N_{ps} \leq N_{ps}$ to $N_{ps} \leq N_{pg}$.
- **RE1044**: Fixed formula variable from $q_{a,t}^{\text{tp}}$ to $q_{n,t}^{\text{tp}}$ to match "Non Associated Gas" title.
- **RE1033–RE1036, RE1045–RE1046**: Fixed set notation range from $\lbrace t_R + 1, \dots, t_R + m/n \rbrace$ to $\lbrace t_R + 1, \dots, t_m \rbrace$.
- **RE1037–RE1044**: Fixed summation upper bound from $m$ to $t_m$ to match References.md symbol definition.
- **RE1037–RE1044**: Fixed subscript inconsistency: removed comma in $N_{p,s}$ → $N_{ps}$, $G_{p,n}$ → $G_{pn}$, etc.
- **RE1035**: Fixed title capitalization "for each year" → "For each year".
- **RE1036**: Fixed double space in title.
- **RE1043**: Fixed double space "Associated  Gas" → "Associated Gas".
- **RE1038, RE1042, RE1043**: Fixed spacing between fluid modifier and P-level: `c\text{2P}` → `c \text{2P}` (space moved outside `\text{}`; renders identically).

#### RE2 - Material Balance
- **RE2001–RE2012**: Fixed typo "discprepancies" → "discrepancies" in 12 rule titles.
- **RE2001–RE2004**: Fixed formula sign convention: production subtracted from resources (consistency with material balance).
- **RE2003, RE2007, RE2011**: Fixed Associated Gas Well Intervention discrepancy: fluid type must be Gas, not Condensate.
- **RE2004, RE2008, RE2012, RE2029, RE2030**: Fixed extra leading space inside `\text{}` in P-level superscripts (`^{\text{ P90}}` → `^{\text{P90}}`, etc.; renders identically).
- **RE2002, RE2006, RE2010**: Fixed Condensate Well Intervention discrepancy: fluid type must be Condensate, not Associated Gas.
- **RE2001–RE2012**: Confirmed `cio` (Consumed in Operations) discrepancy term is present in all 12 GRR/CR/PR formulas.
- **RE2022**: Fixed formula P-level from P50 to **P10** to match "3P" title.
- **RE2024**: Rewrote entire rule for **Non Associated Gas** (was erroneous copy of RE2023/Associated Gas).
- **RE2027–RE2028**: Fixed EUR validation: included cumulative production in the sum check.
- **RE2028**: Fixed Associated Gas resources check: fluid type must be Associated Gas, not Non Associated Gas.
- **RE2030**: Fixed typo "IOIP Low" → "IGIP Low" in example block.
- **RE2001–RE2030**: Standardized subscripts: removed commas in $N_{p,n,t}$ → $N_{pn,t}$, $G_{p,s,t}$ → $G_{ps,t}$, etc.
- **RE2001–RE2030**: Fixed spacing between fluid modifier and P-level: `c\text{P90}` → `c \text{P90}`, `a\text{P50}` → `a \text{P50}` (space moved outside `\text{}`; renders identically).

#### References.md
- Added `uc` = **Unaccounted Changes** to syntax reference table.
- Added 4 `uc` discrepancy symbols to Symbol Reference.
- Fixed pre-existing typo: row for $\Delta D_{G^a}$ under Well Intervention incorrectly used `gtr` superscript → corrected to `wi`.

#### RE0 - Volumetric
- **RE0063–RE0066**: Simplified formulas by removing redundant `P90 > 0` implication condition. RE0059–RE0062 already cover the P90=0 case (P50=P10=0), so RE0063–RE0066 only need to enforce the ordering unconditionally. Titles updated accordingly.

#### RE5 - Maturity Level
- **RE5056–RE5064, RE5066, RE5067**: Added `al` pass/fail examples to 11 rules that previously had none (11 rules, 22 example blocks).
- **RE5011**: Fixed missing $E_3$ in set $M_s$ and corrected fail example from `E3` to `E4`.
- **RE5012**: Fixed typo in fail example: `X1. Production on Hold` → `E1. Production on Hold`.
- **RE5014**: Added missing period in title: `E7 Production not Viable` → `E7. Production not Viable`.
- **RE5018**: Fixed subscript consistency: $M_{t-2}$ → $M_{t_R-2}$.
- **RE5023**: Added missing comma in title between `X1` and `X4`.
- **RE5025**: Fixed set notation: $M_s = \lbrace M_E, X_0, \dots X_4 \rbrace$ → $M_s = M_E \cup \lbrace X_0, \dots, X_4 \rbrace$.
- **RE5031**: Fixed title to match formula: "higher than" → "higher than or equal to".
- **RE5043**: Fixed formula by adding $> 0$ predicate after summation to match title intent.
- **RE5050**: Fixed typo in title: "an Seal" → "and Seal".
- **RE5051**: Fixed title, formula subscript ($P_{g,d}$ → $P_{g,m}$), and all examples ("Trap and Seal" → "Dynamic").
- **RE5053**: Fixed title to include $E_0$ in allowed levels, matching formula: added "E0. On Production" to the list.
- **RE5054**: Fixed implication direction: $(has\;reserves) \implies M \in M_s$ → $M \in M_s \implies (has\;reserves)$.
- **RE5055**: Rewrote title and formula to form iff with RE5054: "Maturity levels E4 through X6 must not have 1P reserves". Changed set from $\lbrace E_1, E_2, E_3 \rbrace$ to $\lbrace E_4, \dots, X_6 \rbrace$ and direction to $M \in M_s \implies \text{reserves} = 0$. Added note about iff relationship. Updated examples.
- **RE5059–RE5061**: Standardized subscript: $N_{\text{project}}$ → $N_{\text{prj}}$.
- **RE5062–RE5064**: Standardized subscript: $G_{\text{project}}$ → $G_{\text{prj}}$.
- **RE5065**: Fixed formula predicate ($= 0$ → $> 0$), subscript ($\text{project}$ → $\text{prj}$), and superscript spacing (`\text{ P10}` → `\text{P10}`; renders identically).
- **RE5066**: Fixed implication direction and corrected `$\empty$` → `$\emptyset$`.
- **RE5068**: Fixed discrepancy sign from $q - \Delta D$ to $q + \Delta D$ to match RE2 material balance convention. Fixed example 1 label from "should fail" to "should pass".
- **RE5053**: Redesigned pass example to test rule's consequent directly (all resources P10 = 0, M = E7) instead of vacuously true.
- **RE5054**: Redesigned pass example to test rule's consequent directly (M = E1 with 1P > 0) instead of vacuously true.
- **RE5066, RE5067**: Changed symbol $t_{act}$ to $t_{ons}$ for consistency.
- **RE5069**: Restored missing `if` block in fail example.
- **RE5068**: Removed duplicate rule entry without title.

#### References
- Added A1 (Dry) and A2 (Dissolved) to Project Maturity Level table.
- Added 2R/2C/2U = P50 equivalence definition to Symbol Reference paragraph.
- Added $t_{ons}$ (Onstream actual date) to Symbol Reference table.
- Added Discrepancy Applicability note explaining why reserves rules (RE2013–RE2024) only include `gtr` while GRR/CR/PR rules (RE2001–RE2012) include all five discrepancy types.

## [1.0.0] - 2026-05-06

### Added

- Initial release of eSDC Rules Documentation.
- Volumetric rules (RE0) covering IOIP, IGIP, GRR/CR/PR, Reserves, and project-level validation.
- Symbol, keyword, syntax, maturity level, and geological chance factor references.
