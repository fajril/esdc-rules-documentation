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

### RE0043 - IOIP Low: Sum of Project IOIP Low must be equal to IOIP Low

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n N^{\text{P90}}_{\text{prj}} = N^{\text{P90}}$$

```python
import esdc
```

The following example should pass:

``` al
if
    project Apple IOIP Low = 1000
    project Mango IOIP Low = 500

    field Fruit IOIP Low = 1500

then
    Validation result is True
```

The following example should fail:

``` al
if
    project Apple IOIP Low = 1000
    project Mango IOIP Low = 500

    field Fruit IOIP Low = 2000

then
    Validation result is False
```

### RE0044 - IOIP Mid: Sum of Project IOIP Mid must be equal to IOIP Mid

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n N^{\text{P50}}_{\text{prj}} = N^{\text{P50}}$$

```python
import esdc
```

The following example should pass:

``` al
if
    project Apple IOIP Mid = 1000
    project Mango IOIP Mid = 500

    field Fruit IOIP Mid = 1500

then
    Validation result is True
```

The following example should fail:

``` al
if
    project Apple IOIP Mid = 1000
    project Mango IOIP Mid = 500

    field Fruit IOIP Mid = 2000

then
    Validation result is False
```

### RE0045 - IOIP High: Sum of Project IOIP High must be equal to IOIP High

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n N^{\text{P10}}_{\text{prj}} = N^{\text{P10}}$$

```python
import esdc
```

The following example should pass:

``` al
if
    project Apple IOIP High = 1000
    project Mango IOIP High = 500

    field Fruit IOIP High = 1500

then
    Validation result is True
```

The following example should fail:

``` al
if
    project Apple IOIP High = 1000
    project Mango IOIP High = 500

    field Fruit IOIP High = 2000

then
    Validation result is False
```

### RE0046 - IGIP Low: Sum of Project IGIP Low must be equal to IGIP Low

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n G^{\text{P90}}_{\text{prj}} = G^{\text{P90}}$$

```python
import esdc
```

The following example should pass:

``` al
if
    project Apple IGIP Low = 1000
    project Mango IGIP Low = 500

    field Fruit IGIP Low = 1500

then
    Validation result is True
```

The following example should fail:

``` al
if
    project Apple IGIP Low = 1000
    project Mango IGIP Low = 500

    field Fruit IGIP Low = 2000

then
    Validation result is False
```

### RE0047 - IGIP Mid: Sum of Project IGIP Mid must be equal to IGIP Mid

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n G^{\text{P50}}_{\text{prj}} = G^{\text{P50}}$$

```python
import esdc
```

The following example should pass:

``` al
if
    project Apple IGIP Mid = 1000
    project Mango IGIP Mid = 500

    field Fruit IGIP Mid = 1500

then
    Validation result is True
```

The following example should fail:

``` al
if
    project Apple IGIP Mid = 1000
    project Mango IGIP Mid = 500

    field Fruit IGIP Mid = 2000

then
    Validation result is False
```

### RE0048 - IGIP High: Sum of Project IGIP High must be equal to IGIP High

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n G^{\text{P10}}_{\text{prj}} = G^{\text{P10}}$$

```python
import esdc
```

The following example should pass:

``` al
if
    project Apple IGIP High = 1000
    project Mango IGIP High = 500

    field Fruit IGIP High = 1500

then
    Validation result is True
```

The following example should fail:

``` al
if
    project Apple IGIP High = 1000
    project Mango IGIP High = 500

    field Fruit IGIP High = 2000

then
    Validation result is False
```

### RE0049 - Oil Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta N_{ps}^{\text{ 3P}} > 0  \implies \Delta N_{ps}^{\text{ 1P}} > 0
$$

```python

import esdc
```

### RE0050 - Condensate Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta N_{ps}^{c \text{ 3P}} > 0  \implies \Delta N_{ps}^{c \text{ 1P}} > 0
$$

```python

import esdc
```

### RE0051 - Associated Gas Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta G_{ps}^{a \text{ 3P}} > 0  \implies \Delta G_{ps}^{a \text{ 1P}} > 0
$$

```python

import esdc
```

### RE0052 - Non Associated Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta G_{ps}^{\text{ 3P}} > 0  \implies \Delta G_{ps}^{\text{ 1P}} > 0
$$

```python

import esdc
```

### RE0053 - Project IOIP Low: if P90 higher than zero then IOIP Low Value must be higher than sum of Sales Cummulative Production and 1P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
N_{proj}^{\text{P90}} > 0  \implies \Delta N_{ps}^{\text{1P}} + N_{p, n, t} < N_{proj}^{\text{P90}}
$$

```python

import esdc
```

### RE0054 - Project IOIP Middle: if P50 higher than zero then IOIP Middle Value must be higher than sum of Cummulative Production and 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
N_{proj}^{\text{P50}} > 0  \implies \Delta N_{ps}^{\text{2P}} + N_{p, n, t} < N_{proj}^{\text{P50}}
$$

```python

import esdc
```

### RE0055 - Project IOIP High: if P10 higher than zero then IOIP Middle Value must be higher than sum of Cummulative Production and 3P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
N_{proj}^{\text{P10}} > 0  \implies \Delta N_{ps}^{\text{3P}} + N_{p, n, t} < N_{proj}^{\text{P10}}
$$

```python

import esdc
```

### RE0056 - Project IGIP Low: if P90 higher than zero then IGIP Low Value must be higher than sum of Sales Cummulative Production and 1P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
G_{proj}^{\text{P90}} > 0  \implies \Delta G_{ps}^{\text{1P}} + G_{p, n, t} < G_{proj}^{\text{P90}}
$$

```python

import esdc
```

### RE0057 - Project IGIP Middle: if P50 higher than zero then IGIP Middle Value must be higher than sum of Cummulative Production and 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
G_{proj}^{\text{P50}} > 0  \implies \Delta G_{ps}^{\text{2P}} + G_{p, n, t} < G_{proj}^{\text{P50}}
$$

```python

import esdc
```

### RE0058 - Project IGIP High: if P10 higher than zero then IGIP Middle Value must be higher than sum of Cummulative Production and 3P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
G_{proj}^{\text{P10}} > 0  \implies \Delta G_{ps}^{\text{3P}} + G_{p, n, t} < G_{proj}^{\text{P10}}
$$

```python

import esdc
```