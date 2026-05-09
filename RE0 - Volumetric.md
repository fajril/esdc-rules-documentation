# RE0 - Volumetric Rules

## List of Rules

### RE0001 - IOIP: Low Case must be positive or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$ N^{\text{P90}} \geq 0 $$

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

### RE0003 - IOIP: Low Case must be less than or equal to Mid Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$N^{\text{P90}} \leq N^{\text{P50}}$$

### RE0004 - IOIP: Mid Case must be less than or equal to High Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$N^{\text{P50}} \leq N^{\text{P10}}$$

### RE0005 - IGIP: Low Case must be less than or equal to Mid Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$G^{\text{P90}} \leq G^{\text{P50}}$$

### RE0006 - IGIP: Mid Case must be less than or equal to High Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$G^{\text{P50}} \leq G^{\text{P10}}$$

### RE0007 - Oil GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \geq 0$$

### RE0008 - Condensate GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \geq 0$$

### RE0009 - Associated Gas GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \geq 0$$

### RE0010 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \geq 0$$

### RE0011 - Oil Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \geq 0$$

### RE0012 - Condensate Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c\text{ 1P}} \geq 0$$

### RE0013 - Associated Gas Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \geq 0$$

### RE0014 - Non Associated Gas Reserves: 1P must be higher than or equal to 0

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \geq 0$$

### RE0015 - Oil GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \leq \Delta N_{pn}^{\text{P50}} $$

### RE0016 - Oil GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P50}} \leq \Delta N_{pn}^{\text{P10}} $$

### RE0017 - Condensate GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \leq \Delta N_{pn}^{c \text{ P50}} $$

### RE0018 - Condensate GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P50}} \leq \Delta N_{pn}^{c \text{ P10}} $$

### RE0019 - Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \leq \Delta G_{pn}^{a \text{ P50}} $$

### RE0020 - Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P50}} \leq \Delta G_{pn}^{a \text{ P10}} $$

### RE0021 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \leq \Delta G_{pn}^{\text{P50}} $$

### RE0022 - Non Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P50}} \leq \Delta G_{pn}^{\text{P10}} $$

### RE0023 - Oil Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{ps}^{\text{2P}} $$

### RE0024 - Oil Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{ps}^{\text{3P}} $$

### RE0025 - Condensate Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 2P}} $$

### RE0026 - Condensate Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{ps}^{c \text{ 3P}} $$

### RE0027 - Associated Gas Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{ps}^{a \text{ 2P}} $$

### RE0028 - Associated Gas Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{ps}^{a \text{ 3P}} $$

### RE0029 - Non Associated Gas Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{ps}^{\text{2P}} $$

### RE0030 - Non Associated Gas Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{ps}^{\text{3P}} $$

### RE0031 - Oil Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{pn}^{\text{1R}}$$

### RE0032 - Oil Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{pn}^{\text{2R}}$$

### RE0033 - Oil Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{3P}} \leq \Delta N_{pn}^{\text{3R}}$$

### RE0034 - Condensate Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{pn}^{c \text{ 1R}}$$

### RE0035 - Condensate Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{pn}^{c \text{ 2R}}$$

### RE0036 - Condensate Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 3P}} \leq \Delta N_{pn}^{c \text{ 3R}}$$

### RE0037 - Associated Gas Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{pn}^{a \text{ 1R}}$$

### RE0038 - Associated Gas Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{pn}^{a \text{ 2R}}$$

### RE0039 - Associated Gas Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 3P}} \leq \Delta G_{pn}^{a \text{ 3R}}$$

### RE0040 - Non Associated Gas Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{pn}^{\text{1R}}$$

### RE0041 - Non Associated Gas Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{pn}^{\text{2R}}$$

### RE0042 - Non Associated Gas Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{3P}} \leq \Delta G_{pn}^{\text{3R}}$$

### RE0043 - IOIP Low: Sum of Project IOIP Low must be equal to IOIP Low

Severity:  `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$\sum_{i=1}^n N_{\text{prj},i}^{\text{P90}} = N^{\text{P90}}$$

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

$$\sum_{i=1}^n N_{\text{prj},i}^{\text{P50}} = N^{\text{P50}}$$

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

$$\sum_{i=1}^n N_{\text{prj},i}^{\text{P10}} = N^{\text{P10}}$$

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

$$\sum_{i=1}^n G_{\text{prj},i}^{\text{P90}} = G^{\text{P90}}$$

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

$$\sum_{i=1}^n G_{\text{prj},i}^{\text{P50}} = G^{\text{P50}}$$

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

$$\sum_{i=1}^n G_{\text{prj},i}^{\text{P10}} = G^{\text{P10}}$$

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
\Delta N_{ps}^{\text{3P}} > 0  \implies \Delta N_{ps}^{\text{1P}} > 0
$$

### RE0050 - Condensate Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta N_{ps}^{c \text{ 3P}} > 0  \implies \Delta N_{ps}^{c \text{ 1P}} > 0
$$

### RE0051 - Associated Gas Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta G_{ps}^{a \text{ 3P}} > 0  \implies \Delta G_{ps}^{a \text{ 1P}} > 0
$$

### RE0052 - Non Associated Gas Reserves: 1P should be higher than zero if 3P is higher than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta G_{ps}^{\text{ 3P}} > 0  \implies \Delta G_{ps}^{\text{ 1P}} > 0
$$

### RE0053 - Project IOIP Low: if P90 higher than zero then IOIP Low Value must be higher than sum of Gross Cumulative Production and 1P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
N_{\text{prj}}^{\text{P90}} > 0  \implies \Delta N_{ps}^{\text{1P}} + N_{pg} < N_{\text{prj}}^{\text{P90}}
$$

### RE0054 - Project IOIP Middle: if P50 higher than zero then IOIP Middle Value must be higher than sum of Gross Cumulative Production and 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
N_{\text{prj}}^{\text{P50}} > 0  \implies \Delta N_{ps}^{\text{2P}} + N_{pg} < N_{\text{prj}}^{\text{P50}}
$$

### RE0055 - Project IOIP High: if P10 higher than zero then IOIP High Value must be higher than sum of Gross Cumulative Production and 3P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
N_{\text{prj}}^{\text{P10}} > 0  \implies \Delta N_{ps}^{\text{3P}} + N_{pg} < N_{\text{prj}}^{\text{P10}}
$$

### RE0056 - Project IGIP Low: if P90 higher than zero then IGIP Low Value must be higher than sum of Gross Cumulative Production and 1P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
G_{\text{prj}}^{\text{P90}} > 0  \implies \Delta G_{ps}^{\text{1P}} + G_{pg} < G_{\text{prj}}^{\text{P90}}
$$

### RE0057 - Project IGIP Middle: if P50 higher than zero then IGIP Middle Value must be higher than sum of Gross Cumulative Production and 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
G_{\text{prj}}^{\text{P50}} > 0  \implies \Delta G_{ps}^{\text{2P}} + G_{pg} < G_{\text{prj}}^{\text{P50}}
$$

### RE0058 - Project IGIP High: if P10 higher than zero then IGIP High Value must be higher than sum of Gross Cumulative Production and 3P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
G_{\text{prj}}^{\text{P10}} > 0  \implies \Delta G_{ps}^{\text{3P}} + G_{pg} < G_{\text{prj}}^{\text{P10}}
$$

