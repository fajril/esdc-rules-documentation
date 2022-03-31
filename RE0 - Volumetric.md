# RE0 - Volumetric Rules

## List of Rules

### RE0001 - IOIP: Low Case must be positive or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$ N^{\text{P90}} \geq 0 $$

```python
import esdc

return esdc.inplace['oil']['low'][-1] >= 0
```

The following example should pass:

``` al
if
    oil in place = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    oil in place = -1000
then
    validation result is False
```

### RE0002 - IGIP: Low Case must be positive or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$ G^{\text{P90}} \geq 0 $$

```python
import esdc

return esdc.inplace['gn']['low'][-1] >= 0
```

### RE0003 - IOIP: Low Case must be less than or equal to Mid Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$N^{\text{P90}} < N^{\text{P50}}$$

```python
import esdc

return esdc.inplace['oil']['low'][-1] <= esdc.inplace['oil']['mid'][-1]
```

### RE0004 - IOIP: Mid Case must be less than or equal to High Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$N^{\text{P50}} < N^{\text{P10}}$$

```python
import esdc

return esdc.inplace['oil']['mid'][-1] <= esdc.inplace['oil']['hgh'][-1]
```

### RE0005 - IGIP: Low Case must be less than or equal to Mid Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$G^{\text{P90}} < G^{\text{P50}}$$

```python
import esdc

return esdc.inplace['gn']['low'][-1] <= esdc.inplace['gn']['mid'][-1]
```

### RE0006 - IGIP: Mid Case must be less or equal than High Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$G^{\text{P50}} < G^{\text{P10}}$$

```python
import esdc

return esdc.inplace['gn']['mid'][-1] <= esdc.inplace['gn']['hgh'][-1]
```

### RE0007 - Oil GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \geq 0$$

```python
import esdc

return esdc.resources['oil']['low'][-1] >= 0
```

### RE0008 - Condensate GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \geq 0$$

```python
import esdc

return esdc.resources['oil']['low'][-1] >= 0
```

### RE0009 - Associated Gas GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \geq 0$$

```python
import esdc

return esdc.resources['ga']['low'][-1] >= 0
```

### RE0010 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \geq 0$$

```python
import esdc

return esdc.resources['gn']['low'][-1] >= 0
```

### RE0011 - Oil Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \geq 0$$

```python
import esdc

return esdc.reserves['oil']['low'][-1] >= 0
```

### RE0012 - Condensate Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c\text{ 1P}} \geq 0$$

```python
import esdc

return esdc.reserves['con']['low'][-1] >= 0
```

### RE0013 - Associated Gas Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \geq 0$$

```python
import esdc

return esdc.reserves['ga']['low'][-1] >= 0
```

### RE0014 - Non Associated Gas Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{ 1P}} \geq 0$$

```python
import esdc

return esdc.reserves['gn']['low'][-1] >= 0
```

### RE0015 - Oil GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \leq \Delta N_{p}^{\text{P50}} $$

```python
import esdc

return esdc.resources['oil']['low'][-1] <= esdc.resources['oil']['mid'][-1]
```

### RE0016 - Oil GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P50}} \leq \Delta N_{pn}^{\text{P10}} $$

```python
import esdc

return esdc.resources['oil']['mid'][-1] <= esdc.resources['oil']['hgh'][-1]
```

### RE0017 - Condensate GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \leq \Delta N_{pn}^{c \text{ P50}} $$

```python
import esdc

return esdc.resources['con']['low'][-1] <= esdc.resources['con']['mid'][-1]
```

### RE0018 - Condensate GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P50}} \leq \Delta N_{pn}^{c \text{ P10}} $$

```python
import esdc

return esdc.resources['con']['mid'][-1] <= esdc.resources['con']['hgh'][-1]
```

### RE0019 - Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \leq \Delta G_{pn}^{a \text{ P50}} $$

```python
import esdc

return esdc.resources['ga']['low'][-1] <= esdc.resources['ga']['mid'][-1]
```

### RE0020 - Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P50}} \leq \Delta G_{pn}^{a \text{ P10}} $$

```python
import esdc

return esdc.resources['ga']['mid'][-1] <= esdc.resources['ga']['hgh'][-1]
```

### RE0021 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \leq \Delta G_{pn}^{\text{P50}} $$

```python
import esdc

return esdc.resources['gn']['low'][-1] <= esdc.resources['gn']['mid'][-1]
```

### RE0022 - Non Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P50}} \leq \Delta G_{pn}^{\text{P10}} $$

```python
import esdc

return esdc.resources['gn']['mid'][-1] <= esdc.resources['gn']['hgh'][-1]
```

### RE0023 - Oil Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{ps}^{\text{2P}} $$

```python
import esdc

return esdc.reserves['oil']['low'][-1] <= esdc.reserves['oil']['mid'][-1]
```

### RE0024 - Oil Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{ps}^{\text{3P}} $$

```python
import esdc

return esdc.reserves['oil']['mid'][-1] <= esdc.reserves['oil']['hgh'][-1]
```

### RE0025 - Condensate Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 1P}} $$

```python
import esdc

return esdc.reserves['con']['low'][-1] <= esdc.reserves['con']['mid'][-1]
```

### RE0026 - Condensate Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{ps}^{c \text{ 3P}} $$

```python
import esdc

return esdc.reserves['con']['mid'][-1] <= esdc.reserves['con']['hgh'][-1]
```

### RE0027 - Associated Gas Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{ps}^{a \text{ 2P}} $$

```python
import esdc

return esdc.reserves['ga']['low'][-1] <= esdc.reserves['ga']['mid'][-1]
```

### RE0028 - Associated Gas Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{ps}^{a \text{ 3P}} $$

```python
import esdc

return esdc.reserves['ga']['mid'][-1] <= esdc.reserves['ga']['hgh'][-1]
```

### RE0029 - Non Associated Gas Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{ps}^{\text{2P}} $$

```python
import esdc

return esdc.reserves['gn']['low'][-1] <= esdc.reserves['gn']['mid'][-1]
```

### RE0030 - Non Associated Gas Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{ps}^{\text{3P}} $$

```python
import esdc

return esdc.reserves['gn']['mid'][-1] <= esdc.reserves['gn']['hgh'][-1]
```

### RE0031 - Oil Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{pn}^{\text{1R}}$$

```python
import esdc

return esdc.reserves['oil']['low'][-1] <= esdc.resources['oil']['low'][-1]
```

### RE0032 - Oil Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{pn}^{\text{2R}}$$

```python
import esdc

return esdc.reserves['oil']['mid'][-1] <= esdc.resources['oil']['mid'][-1]
```

### RE0033 - Oil Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{3P}} \leq \Delta N_{pn}^{\text{3R}}$$

```python
import esdc

return esdc.reserves['oil']['hgh'][-1] <= esdc.resources['oil']['hgh'][-1]
```

### RE0034 - Condensate Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{pn}^{c \text{ 1R}}$$

```python
import esdc

return esdc.reserves['con']['low'][-1] <= esdc.resources['con']['low'][-1]
```

### RE0035 - Condensate Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{pn}^{c \text{ 2R}}$$

```python
import esdc

return esdc.reserves['con']['mid'][-1] <= esdc.resources['con']['mid'][-1]
```

### RE0036 - Condensate Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 3P}} \leq \Delta N_{pn}^{c \text{ 3R}}$$

```python
import esdc

return esdc.reserves['con']['hgh'][-1] <= esdc.resources['con']['hgh'][-1]
```

### RE0037 - Associated Gas Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{pn}^{a \text{ 1R}}$$

```python
import esdc

return esdc.reserves['ga']['low'][-1] <= esdc.resources['ga']['low'][-1]
```

### RE0038 - Associated Gas Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{pn}^{a \text{ 2R}}$$

```python
import esdc

return esdc.reserves['ga']['mid'][-1] <= esdc.resources['ga']['mid'][-1]
```

### RE0039 - Associated Gas Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 3P}} \leq \Delta G_{pn}^{a \text{ 3R}}$$

```python
import esdc

return esdc.reserves['ga']['hgh'][-1] <= esdc.resources['ga']['hgh'][-1]
```

### RE0040 - Non Associated Gas Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{pn}^{\text{1R}}$$

```python
import esdc

return esdc.reserves['gn']['low'][-1] <= esdc.resources['gn']['low'][-1]
```

### RE0041 - Non Associated Gas Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{pn}^{\text{2R}}$$

```python
import esdc

return esdc.reserves['gn']['mid'][-1] <= esdc.resources['gn']['mid'][-1]
```

### RE0042 - Associated Gas Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{3P}} \leq \Delta G_{pn}^{\text{3R}}$$

```python
import esdc

return esdc.reserves['gn']['hgh'][-1] <= esdc.resources['gn']['hgh'][-1]
```

### RE0043 - Oil, Condensate, Associated Gas, Non Associated Gas GRR/CR/PR P10: If project does not have hydrocarbon volume then the project level must be either E7, E8, A1, or A2

Severity:  `strict` :no_entry:

The following equation must be true:

$$
M_s = \left\{E_7, E_8, A_1, A_2 \right\} \\
\Delta N_{pn}^{\text{ P10}} = \Delta N_{pn}^{c \text{ P10}} = \Delta G_{pn}^{a \text{ P10}} = \Delta G_{pn}^{\text{P10}} = 0 \implies M_{t_R} \in M_s
$$

```python

import esdc
```

The following example should pass:

``` al
if
    Oil GRR/CR/PR High Value = 1000
    project level is E0. On Production

then
    Validation result is True

```

The following example should fail:

``` al
if
    Oil GRR/CR/PR High Value = 0
    con GRR/CR/PR High Value = 0
    ga GRR/CR/PR High Value = 0
    gn GRR/CR/PR High Value = 0
    project level is E0. On Production

then
    Validation result is False

```

### RE0044 - Oil, Condensate, Associated Gas, Non Associated Gas Reserves 1P: Project must have reserves for project maturity level E0, E1, E2, E3

Severity:  `strict` :no_entry:

The following equation must be true:

$$
M_s = \left\{E_0, E_1, E_2, E_3 \right\} \\
\left( \Delta N_{ps}^{\text{ 1P}} > 0 \right) \lor \left(\Delta N_{ps}^{c \text{ 1P}} > 0 \right) \lor \left(\Delta G_{ps}^{a \text{ 1P}} > 0 \right) \lor \left(\Delta G_{ps}^{\text{1P}} > 0 \right) \implies M_{t_R} \in M_s
$$

```python

import esdc
```

The following example should pass:

``` al
if
    Oil Reserves 1P = 1000
    project level is E0. On Production

then
    Validation result is True

```

The following example should fail:

``` al
if
    Oil reserves 1P = 0
    con reserves 1P = 0
    ga reserves 1P = 0
    gn reserves 1P = 0

    project level is E0. On Production

then
    Validation result is False
```

### RE0045 - Oil, Condensate, Associated Gas, Non Associated Gas Reserves 1P: Project must not have reserves for project maturity level E4 to X6

Severity:  `strict` :no_entry:

The following equation must be true:

$$
M_s = \left\{E_0, E_1, E_2, E_3 \right\} \\
\left( \Delta N_{ps}^{\text{ 1P}} = \Delta N_{ps}^{c \text{ 1P}} = \Delta G_{ps}^{a \text{ 1P}} = \Delta G_{ps}^{\text{1P}} = 0 \right) \implies M_{t_R} \notin M_s
$$

```python

import esdc
```

The following example should pass:

``` al
if
    Oil reserves 1P = 0
    con reserves 1P = 0
    ga reserves 1P = 0
    gn reserves 1P = 0

    project level is X0. Development Pending

then
    Validation result is True
```

The following example should fail:

``` al
if
    Oil reserves 1P = 0
    con reserves 1P = 0
    ga reserves 1P = 0
    gn reserves 1P = 0

    project level is E3. Justified for Development

then
    Validation result is False
```

### RE0046 - Oil Reserves: 1P should be higher than zero if 2P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta N_{ps}^{\text{ 2P}} > 0  \implies \Delta N_{ps}^{\text{ 1P}} > 0
$$

```python

import esdc
```

### RE0047 - Condensate Reserves: 1P should be higher than zero if 2P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta N_{ps}^{c \text{ 2P}} > 0  \implies \Delta N_{ps}^{c \text{ 1P}} > 0
$$

```python

import esdc
```

### RE0048 - Associated Gas Reserves: 1P should be higher than zero if 2P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta G_{ps}^{a \text{ 2P}} > 0  \implies \Delta G_{ps}^{a \text{ 1P}} > 0
$$

```python

import esdc
```

### RE0049 - Non Associated Reserves: 1P should be higher than zero if 2P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta G_{ps}^{\text{ 2P}} > 0  \implies \Delta G_{ps}^{\text{ 1P}} > 0
$$

```python

import esdc
```

### RE0050 - Oil Reserves: 2P should be higher than zero if 3P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta N_{ps}^{\text{ 3P}} > 0  \implies \Delta N_{ps}^{\text{ 2P}} > 0
$$

```python

import esdc
```

### RE0051 - Condensate Reserves: 2P should be higher than zero if 3P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta N_{ps}^{c \text{ 3P}} > 0  \implies \Delta N_{ps}^{c \text{ 2P}} > 0
$$

```python

import esdc
```

### RE0052 - Associated Gas Reserves: 2P should be higher than zero if 3P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta G_{ps}^{a \text{ 3P}} > 0  \implies \Delta G_{ps}^{a \text{ 2P}} > 0
$$

```python

import esdc
```

### RE0053 - Non Associated Gas Reserves: 2P should be higher than zero if 3P is higher than zero

Severity: `warning` :warning:

The following equation should be true:

$$
\Delta G_{ps}^{\text{ 3P}} > 0  \implies \Delta G_{ps}^{\text{ 2P}} > 0
$$

```python

import esdc
```

### RE0054 - IOIP: Low Case value should be equal to the result of GGR Study Report

severity: `warning` :warning:

The following equation should be true:

$$
N^{\text{P90}}_{\text{study, field}} \neq \empty \implies N^{\text{P90}} = N^{\text{P90}}_{\text{study, field}}
$$

```python
import esdc
```

### RE0055 - IOIP: Mid Case value should be equal to the result of GGR Study Report

severity: `warning` :warning:

The following equation should be true:

$$
N^{\text{P50}}_{\text{study, field}} \neq \empty \implies N^{\text{P50}} = N^{\text{P50}}_{\text{study, field}}
$$

```python
import esdc
```

### RE0056 - IOIP: High Case value should be equal to the result of GGR Study Report

severity: `warning` :warning:

The following equation should be true:

$$
N^{\text{P10}}_{\text{study, field}} \neq \empty \implies N^{\text{P10}} = N^{\text{P10}}_{\text{study, field}}
$$

```python
import esdc
```

### RE0057 - IGIP: Low Case value should be equal to the result of GGR Study Report

severity: `warning` :warning:

The following equation should be true:

$$
G^{\text{P90}}_{\text{study, field}} \neq \empty \implies G^{\text{P90}} = G^{\text{P90}}_{\text{study, field}}
$$

```python
import esdc
```

### RE0058 - IGIP: Mid Case value should be equal to the result of GGR Study Report

severity: `warning` :warning:

The following equation should be true:

$$
G^{\text{P50}}_{\text{study, field}}\neq \empty \implies G^{\text{P50}} = G^{\text{P50}}_{\text{study, field}}
$$

```python
import esdc
```

### RE0059 - IGIP: High Case value should be equal to the result of GGR Study Report

severity: `warning` :warning:

The following equation should be true:

$$
G^{\text{P10}}_{\text{study, field}} \neq \empty \implies G^{\text{P10}} = G^{\text{P10}}_{\text{study, field}}
$$

```python
import esdc
```
