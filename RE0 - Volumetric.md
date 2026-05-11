# RE0 - Volumetric Rules

## List of Rules

### RE0001 - IOIP: Low Case must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$ N^{\text{P90}} \geq 0 $$

The following example should pass:

``` al
if
    Oil in Place = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil in Place = -1000
then
    validation result is False
```

### RE0002 - IGIP: Low Case must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$ G^{\text{P90}} \geq 0 $$

The following example should pass:

``` al
if
    Gas in Place = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Gas in Place = -1
then
    validation result is False
```

### RE0003 - IOIP: Low Case must be less than or equal to Mid Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$N^{\text{P90}} \leq N^{\text{P50}}$$

The following example should pass:

``` al
if
    Oil in Place Low = 500
    Oil in Place Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil in Place Low = 1500
    Oil in Place Mid = 1000
then
    validation result is False
```

### RE0004 - IOIP: Mid Case must be less than or equal to High Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$N^{\text{P50}} \leq N^{\text{P10}}$$

The following example should pass:

``` al
if
    Oil in Place Mid = 1000
    Oil in Place High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil in Place Mid = 2000
    Oil in Place High = 1500
then
    validation result is False
```

### RE0005 - IGIP: Low Case must be less than or equal to Mid Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$G^{\text{P90}} \leq G^{\text{P50}}$$

The following example should pass:

``` al
if
    Gas in Place Low = 500
    Gas in Place Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Gas in Place Low = 1500
    Gas in Place Mid = 1000
then
    validation result is False
```

### RE0006 - IGIP: Mid Case must be less than or equal to High Case

Severity:  `strict` :no_entry:

The following equation must be true:

$$G^{\text{P50}} \leq G^{\text{P10}}$$

The following example should pass:

``` al
if
    Gas in Place Mid = 1000
    Gas in Place High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Gas in Place Mid = 2000
    Gas in Place High = 1500
then
    validation result is False
```

### RE0007 - Oil GRR/CR/PR: 1R/1C/1U must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \geq 0$$

The following example should pass:

``` al
if
    Oil GRR/CR/PR Low = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR Low = -1
then
    validation result is False
```

### RE0008 - Condensate GRR/CR/PR: 1R/1C/1U must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \geq 0$$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR Low = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR Low = -1
then
    validation result is False
```

### RE0009 - Associated Gas GRR/CR/PR: 1R/1C/1U must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \geq 0$$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR Low = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR Low = -1
then
    validation result is False
```

### RE0010 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \geq 0$$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR Low = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR Low = -1
then
    validation result is False
```

### RE0011 - Oil Reserves: 1P must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \geq 0$$

The following example should pass:

``` al
if
    Oil Reserves 1P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 1P = -1
then
    validation result is False
```

### RE0012 - Condensate Reserves: 1P must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c\text{ 1P}} \geq 0$$

The following example should pass:

``` al
if
    Condensate Reserves 1P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 1P = -1
then
    validation result is False
```

### RE0013 - Associated Gas Reserves: 1P must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \geq 0$$

The following example should pass:

``` al
if
    Associated Gas Reserves 1P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 1P = -1
then
    validation result is False
```

### RE0014 - Non Associated Gas Reserves: 1P must be greater than or equal to zero

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \geq 0$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 1P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 1P = -1
then
    validation result is False
```

### RE0015 - Oil GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \leq \Delta N_{pn}^{\text{P50}} $$

The following example should pass:

``` al
if
    Oil GRR/CR/PR Low = 500
    Oil GRR/CR/PR Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR Low = 1500
    Oil GRR/CR/PR Mid = 1000
then
    validation result is False
```

### RE0016 - Oil GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{\text{P50}} \leq \Delta N_{pn}^{\text{P10}} $$

The following example should pass:

``` al
if
    Oil GRR/CR/PR Mid = 1000
    Oil GRR/CR/PR High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR Mid = 2000
    Oil GRR/CR/PR High = 1500
then
    validation result is False
```

### RE0017 - Condensate GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \leq \Delta N_{pn}^{c \text{ P50}} $$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR Low = 500
    Condensate GRR/CR/PR Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR Low = 1500
    Condensate GRR/CR/PR Mid = 1000
then
    validation result is False
```

### RE0018 - Condensate GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P50}} \leq \Delta N_{pn}^{c \text{ P10}} $$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR Mid = 1000
    Condensate GRR/CR/PR High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR Mid = 2000
    Condensate GRR/CR/PR High = 1500
then
    validation result is False
```

### RE0019 - Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \leq \Delta G_{pn}^{a \text{ P50}} $$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR Low = 500
    Associated Gas GRR/CR/PR Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR Low = 1500
    Associated Gas GRR/CR/PR Mid = 1000
then
    validation result is False
```

### RE0020 - Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P50}} \leq \Delta G_{pn}^{a \text{ P10}} $$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR Mid = 1000
    Associated Gas GRR/CR/PR High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR Mid = 2000
    Associated Gas GRR/CR/PR High = 1500
then
    validation result is False
```

### RE0021 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \leq \Delta G_{pn}^{\text{P50}} $$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR Low = 500
    Non Associated Gas GRR/CR/PR Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR Low = 1500
    Non Associated Gas GRR/CR/PR Mid = 1000
then
    validation result is False
```

### RE0022 - Non Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn}^{\text{P50}} \leq \Delta G_{pn}^{\text{P10}} $$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR Mid = 1000
    Non Associated Gas GRR/CR/PR High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR Mid = 2000
    Non Associated Gas GRR/CR/PR High = 1500
then
    validation result is False
```

### RE0023 - Oil Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{ps}^{\text{2P}} $$

The following example should pass:

``` al
if
    Oil Reserves 1P = 500
    Oil Reserves 2P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 1P = 1500
    Oil Reserves 2P = 1000
then
    validation result is False
```

### RE0024 - Oil Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{ps}^{\text{3P}} $$

The following example should pass:

``` al
if
    Oil Reserves 2P = 1000
    Oil Reserves 3P = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 2P = 2000
    Oil Reserves 3P = 1500
then
    validation result is False
```

### RE0025 - Condensate Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 2P}} $$

The following example should pass:

``` al
if
    Condensate Reserves 1P = 500
    Condensate Reserves 2P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 1P = 1500
    Condensate Reserves 2P = 1000
then
    validation result is False
```

### RE0026 - Condensate Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{ps}^{c \text{ 3P}} $$

The following example should pass:

``` al
if
    Condensate Reserves 2P = 1000
    Condensate Reserves 3P = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 2P = 2000
    Condensate Reserves 3P = 1500
then
    validation result is False
```

### RE0027 - Associated Gas Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{ps}^{a \text{ 2P}} $$

The following example should pass:

``` al
if
    Associated Gas Reserves 1P = 500
    Associated Gas Reserves 2P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 1P = 1500
    Associated Gas Reserves 2P = 1000
then
    validation result is False
```

### RE0028 - Associated Gas Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{ps}^{a \text{ 3P}} $$

The following example should pass:

``` al
if
    Associated Gas Reserves 2P = 1000
    Associated Gas Reserves 3P = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 2P = 2000
    Associated Gas Reserves 3P = 1500
then
    validation result is False
```

### RE0029 - Non Associated Gas Reserves: 1P must be less than or equal to 2P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{ps}^{\text{2P}} $$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 1P = 500
    Non Associated Gas Reserves 2P = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 1P = 1500
    Non Associated Gas Reserves 2P = 1000
then
    validation result is False
```

### RE0030 - Non Associated Gas Reserves: 2P must be less than or equal to 3P

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{ps}^{\text{3P}} $$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 2P = 1000
    Non Associated Gas Reserves 3P = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 2P = 2000
    Non Associated Gas Reserves 3P = 1500
then
    validation result is False
```

### RE0031 - Oil Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{pn}^{\text{1R}}$$

The following example should pass:

``` al
if
    Oil Reserves 1P = 500
    Oil GRR/CR/PR 1R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 1P = 1500
    Oil GRR/CR/PR 1R = 1000
then
    validation result is False
```

### RE0032 - Oil Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{pn}^{\text{2R}}$$

The following example should pass:

``` al
if
    Oil Reserves 2P = 500
    Oil GRR/CR/PR 2R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 2P = 1500
    Oil GRR/CR/PR 2R = 1000
then
    validation result is False
```

### RE0033 - Oil Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{\text{3P}} \leq \Delta N_{pn}^{\text{3R}}$$

The following example should pass:

``` al
if
    Oil Reserves 3P = 500
    Oil GRR/CR/PR 3R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 3P = 1500
    Oil GRR/CR/PR 3R = 1000
then
    validation result is False
```

### RE0034 - Condensate Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{pn}^{c \text{ 1R}}$$

The following example should pass:

``` al
if
    Condensate Reserves 1P = 500
    Condensate GRR/CR/PR 1R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 1P = 1500
    Condensate GRR/CR/PR 1R = 1000
then
    validation result is False
```

### RE0035 - Condensate Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{pn}^{c \text{ 2R}}$$

The following example should pass:

``` al
if
    Condensate Reserves 2P = 500
    Condensate GRR/CR/PR 2R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 2P = 1500
    Condensate GRR/CR/PR 2R = 1000
then
    validation result is False
```

### RE0036 - Condensate Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 3P}} \leq \Delta N_{pn}^{c \text{ 3R}}$$

The following example should pass:

``` al
if
    Condensate Reserves 3P = 500
    Condensate GRR/CR/PR 3R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 3P = 1500
    Condensate GRR/CR/PR 3R = 1000
then
    validation result is False
```

### RE0037 - Associated Gas Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{pn}^{a \text{ 1R}}$$

The following example should pass:

``` al
if
    Associated Gas Reserves 1P = 500
    Associated Gas GRR/CR/PR 1R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 1P = 1500
    Associated Gas GRR/CR/PR 1R = 1000
then
    validation result is False
```

### RE0038 - Associated Gas Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{pn}^{a \text{ 2R}}$$

The following example should pass:

``` al
if
    Associated Gas Reserves 2P = 500
    Associated Gas GRR/CR/PR 2R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 2P = 1500
    Associated Gas GRR/CR/PR 2R = 1000
then
    validation result is False
```

### RE0039 - Associated Gas Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 3P}} \leq \Delta G_{pn}^{a \text{ 3R}}$$

The following example should pass:

``` al
if
    Associated Gas Reserves 3P = 500
    Associated Gas GRR/CR/PR 3R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 3P = 1500
    Associated Gas GRR/CR/PR 3R = 1000
then
    validation result is False
```

### RE0040 - Non Associated Gas Reserves: 1P must be less than or equal to 1R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{pn}^{\text{1R}}$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 1P = 500
    Non Associated Gas GRR/CR/PR 1R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 1P = 1500
    Non Associated Gas GRR/CR/PR 1R = 1000
then
    validation result is False
```

### RE0041 - Non Associated Gas Reserves: 2P must be less than or equal to 2R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{pn}^{\text{2R}}$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 2P = 500
    Non Associated Gas GRR/CR/PR 2R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 2P = 1500
    Non Associated Gas GRR/CR/PR 2R = 1000
then
    validation result is False
```

### RE0042 - Non Associated Gas Reserves: 3P must be less than or equal to 3R

Severity:  `strict` :no_entry:

The following equation must be true:

$$\Delta G_{ps}^{\text{3P}} \leq \Delta G_{pn}^{\text{3R}}$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 3P = 500
    Non Associated Gas GRR/CR/PR 3R = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 3P = 1500
    Non Associated Gas GRR/CR/PR 3R = 1000
then
    validation result is False
```

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
    validation result is True
```

The following example should fail:

``` al
if
    project Apple IOIP Low = 1000
    project Mango IOIP Low = 500

    field Fruit IOIP Low = 2000

then
    validation result is False
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
    validation result is True
```

The following example should fail:

``` al
if
    project Apple IOIP Mid = 1000
    project Mango IOIP Mid = 500

    field Fruit IOIP Mid = 2000

then
    validation result is False
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
    validation result is True
```

The following example should fail:

``` al
if
    project Apple IOIP High = 1000
    project Mango IOIP High = 500

    field Fruit IOIP High = 2000

then
    validation result is False
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
    validation result is True
```

The following example should fail:

``` al
if
    project Apple IGIP Low = 1000
    project Mango IGIP Low = 500

    field Fruit IGIP Low = 2000

then
    validation result is False
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
    validation result is True
```

The following example should fail:

``` al
if
    project Apple IGIP Mid = 1000
    project Mango IGIP Mid = 500

    field Fruit IGIP Mid = 2000

then
    validation result is False
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
    validation result is True
```

The following example should fail:

``` al
if
    project Apple IGIP High = 1000
    project Mango IGIP High = 500

    field Fruit IGIP High = 2000

then
    validation result is False
```

### RE0049 - Oil Reserves: 1P should be greater than zero if 3P is greater than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta N_{ps}^{\text{3P}} > 0  \implies \Delta N_{ps}^{\text{1P}} > 0
$$

The following example should pass:

``` al
if
    Oil Reserves 3P = 100
    Oil Reserves 1P = 50
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 3P = 100
    Oil Reserves 1P = 0
then
    validation result is False
```

### RE0050 - Condensate Reserves: 1P should be greater than zero if 3P is greater than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta N_{ps}^{c \text{ 3P}} > 0  \implies \Delta N_{ps}^{c \text{ 1P}} > 0
$$

The following example should pass:

``` al
if
    Condensate Reserves 3P = 100
    Condensate Reserves 1P = 50
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 3P = 100
    Condensate Reserves 1P = 0
then
    validation result is False
```

### RE0051 - Associated Gas Reserves: 1P should be greater than zero if 3P is greater than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta G_{ps}^{a \text{ 3P}} > 0  \implies \Delta G_{ps}^{a \text{ 1P}} > 0
$$

The following example should pass:

``` al
if
    Associated Gas Reserves 3P = 100
    Associated Gas Reserves 1P = 50
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 3P = 100
    Associated Gas Reserves 1P = 0
then
    validation result is False
```

### RE0052 - Non Associated Gas Reserves: 1P should be greater than zero if 3P is greater than zero

Severity: `strict` :no_entry:

Notes: _Implemented for reporting status of 31.12.2022_

The following equation must be true:

$$
\Delta G_{ps}^{\text{3P}} > 0  \implies \Delta G_{ps}^{\text{1P}} > 0
$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 3P = 100
    Non Associated Gas Reserves 1P = 50
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 3P = 100
    Non Associated Gas Reserves 1P = 0
then
    validation result is False
```

### RE0053 - Project IOIP Low: if P90 greater than zero then IOIP Low Value must be greater than sum of Gross Cumulative Production and 1P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
N_{\text{prj}}^{\text{P90}} > 0  \implies \Delta N_{ps}^{\text{1P}} + N_{pg} < N_{\text{prj}}^{\text{P90}}
$$

The following example should pass:

``` al
if
    Project IOIP Low = 1000
    Oil Reserves 1P = 200
    Oil Gross Cumulative Production = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP Low = 1000
    Oil Reserves 1P = 800
    Oil Gross Cumulative Production = 300
then
    validation result is False
```

### RE0054 - Project IOIP P50: if P50 greater than zero then IOIP P50 Value must be greater than sum of Gross Cumulative Production and 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
N_{\text{prj}}^{\text{P50}} > 0  \implies \Delta N_{ps}^{\text{2P}} + N_{pg} < N_{\text{prj}}^{\text{P50}}
$$

The following example should pass:

``` al
if
    Project IOIP Mid = 1000
    Oil Reserves 2P = 200
    Oil Gross Cumulative Production = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP Mid = 1000
    Oil Reserves 2P = 800
    Oil Gross Cumulative Production = 300
then
    validation result is False
```

### RE0055 - Project IOIP High: if P10 greater than zero then IOIP High Value must be greater than sum of Gross Cumulative Production and 3P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
N_{\text{prj}}^{\text{P10}} > 0  \implies \Delta N_{ps}^{\text{3P}} + N_{pg} < N_{\text{prj}}^{\text{P10}}
$$

The following example should pass:

``` al
if
    Project IOIP High = 1000
    Oil Reserves 3P = 200
    Oil Gross Cumulative Production = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP High = 1000
    Oil Reserves 3P = 800
    Oil Gross Cumulative Production = 300
then
    validation result is False
```

### RE0056 - Project IGIP Low: if P90 greater than zero then IGIP Low Value must be greater than sum of Gross Cumulative Production and 1P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$
G_{\text{prj}}^{\text{P90}} > 0  \implies \Delta G_{ps}^{\text{1P}} + G_{pg} < G_{\text{prj}}^{\text{P90}}
$$

The following example should pass:

``` al
if
    Project IGIP Low = 1000
    Non Associated Gas Reserves 1P = 200
    Non Associated Gas Gross Cumulative Production = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP Low = 1000
    Non Associated Gas Reserves 1P = 800
    Non Associated Gas Gross Cumulative Production = 300
then
    validation result is False
```

### RE0057 - Project IGIP P50: if P50 greater than zero then IGIP P50 Value must be greater than sum of Gross Cumulative Production and 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
G_{\text{prj}}^{\text{P50}} > 0  \implies \Delta G_{ps}^{\text{2P}} + G_{pg} < G_{\text{prj}}^{\text{P50}}
$$

The following example should pass:

``` al
if
    Project IGIP Mid = 1000
    Non Associated Gas Reserves 2P = 200
    Non Associated Gas Gross Cumulative Production = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP Mid = 1000
    Non Associated Gas Reserves 2P = 800
    Non Associated Gas Gross Cumulative Production = 300
then
    validation result is False
```

### RE0058 - Project IGIP High: if P10 greater than zero then IGIP High Value must be greater than sum of Gross Cumulative Production and 3P Reserves

Severity: `strict` :no_entry:

The following equation must be true:


$$
G_{\text{prj}}^{\text{P10}} > 0  \implies \Delta G_{ps}^{\text{3P}} + G_{pg} < G_{\text{prj}}^{\text{P10}}
$$

The following example should pass:

``` al
if
    Project IGIP High = 1000
    Non Associated Gas Reserves 3P = 200
    Non Associated Gas Gross Cumulative Production = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP High = 1000
    Non Associated Gas Reserves 3P = 800
    Non Associated Gas Gross Cumulative Production = 300
then
    validation result is False
```

### RE0059 - Project IOIP P50: Must equal zero when P90 equals zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$N_{\text{prj}}^{\text{P90}} = 0 \implies N_{\text{prj}}^{\text{P50}} = 0$$

The following example should pass:

``` al
if
    Project IOIP Low = 0
    Project IOIP Mid = 0
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP Low = 0
    Project IOIP Mid = 500
then
    validation result is False
```

### RE0060 - Project IOIP P10: Must equal zero when P90 equals zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$N_{\text{prj}}^{\text{P90}} = 0 \implies N_{\text{prj}}^{\text{P10}} = 0$$

The following example should pass:

``` al
if
    Project IOIP Low = 0
    Project IOIP High = 0
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP Low = 0
    Project IOIP High = 1000
then
    validation result is False
```

### RE0061 - Project IGIP P50: Must equal zero when P90 equals zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$G_{\text{prj}}^{\text{P90}} = 0 \implies G_{\text{prj}}^{\text{P50}} = 0$$

The following example should pass:

``` al
if
    Project IGIP Low = 0
    Project IGIP Mid = 0
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP Low = 0
    Project IGIP Mid = 500
then
    validation result is False
```

### RE0062 - Project IGIP P10: Must equal zero when P90 equals zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$G_{\text{prj}}^{\text{P90}} = 0 \implies G_{\text{prj}}^{\text{P10}} = 0$$

The following example should pass:

``` al
if
    Project IGIP Low = 0
    Project IGIP High = 0
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP Low = 0
    Project IGIP High = 1000
then
    validation result is False
```

### RE0063 - Project IOIP P90: Must be less than or equal to P50 when greater than zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$N_{\text{prj}}^{\text{P90}} > 0 \implies N_{\text{prj}}^{\text{P90}} \leq N_{\text{prj}}^{\text{P50}}$$

The following example should pass:

``` al
if
    Project IOIP Low = 500
    Project IOIP Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP Low = 1500
    Project IOIP Mid = 1000
then
    validation result is False
```

### RE0064 - Project IOIP P50: Must be less than or equal to P10 when P90 greater than zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$N_{\text{prj}}^{\text{P90}} > 0 \implies N_{\text{prj}}^{\text{P50}} \leq N_{\text{prj}}^{\text{P10}}$$

The following example should pass:

``` al
if
    Project IOIP Mid = 1000
    Project IOIP High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IOIP Mid = 2000
    Project IOIP High = 1500
then
    validation result is False
```

### RE0065 - Project IGIP P90: Must be less than or equal to P50 when greater than zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$G_{\text{prj}}^{\text{P90}} > 0 \implies G_{\text{prj}}^{\text{P90}} \leq G_{\text{prj}}^{\text{P50}}$$

The following example should pass:

``` al
if
    Project IGIP Low = 500
    Project IGIP Mid = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP Low = 1500
    Project IGIP Mid = 1000
then
    validation result is False
```

### RE0066 - Project IGIP P50: Must be less than or equal to P10 when P90 greater than zero

Severity:  `strict` :no_entry:

Notes: _Added on 10 May 2026_

The following equation must be true:

$$G_{\text{prj}}^{\text{P90}} > 0 \implies G_{\text{prj}}^{\text{P50}} \leq G_{\text{prj}}^{\text{P10}}$$

The following example should pass:

``` al
if
    Project IGIP Mid = 1000
    Project IGIP High = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Project IGIP Mid = 2000
    Project IGIP High = 1500
then
    validation result is False
```

