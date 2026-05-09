# RE2 - Material Balance

## List of Rules

### RE2001 - Oil GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P90}} = \Delta N_{pn,t - 1}^{\text{P90}} + \Delta D_{N}^\text{um P90} + \Delta D_{N}^\text{ppa P90} + \Delta D_{N}^\text{wi P90} + \Delta D_{N}^\text{uc P90} + \Delta D_{N}^\text{cio P90} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['oil']['low']['um'][-1] + esdc.discrepancy['oil']['low']['ppa'][-1]
        + esdc.discrepancy['oil']['low']['wi'][-1] + esdc.discrepancy['oil']['low']['uc'][-1]
        + esdc.discrepancy['oil']['low']['cio'][-1]
prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['low'][-2] + discr - prod

return esdc.resources['oil']['low'][-1] == new_resources
```

### RE2002 - Condensate GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P90}} = \Delta N_{pn,t - 1}^{c \text{P90}} + \Delta D_{N^c}^\text{um P90} + \Delta D_{N^c}^\text{ppa P90} + \Delta D_{N^c}^\text{wi P90} + \Delta D_{N^c}^\text{uc P90} + \Delta D_{N^c}^\text{cio P90} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

```python
import esdc

discr = esdc.discrepancy['con']['low']['um'][-1] + esdc.discrepancy['con']['low']['ppa'][-1]
        + esdc.discrepancy['con']['low']['wi'][-1] + esdc.discrepancy['con']['low']['uc'][-1]
        + esdc.discrepancy['con']['low']['cio'][-1]
prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['low'][-2] + discr - prod

return esdc.resources['con']['low'][-1] == new_resources
```

### RE2003 - Associated Gas GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P90}} = \Delta G_{pn,t - 1}^{a \text{P90}} + \Delta D_{G^a}^\text{um P90} + \Delta D_{G^a}^\text{ppa P90} + \Delta D_{G^a}^\text{wi P90} + \Delta D_{G^a}^\text{uc P90} + \Delta D_{G^a}^\text{cio P90} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

```python
import esdc

discr = esdc.discrepancy['ga']['low']['um'][-1] + esdc.discrepancy['ga']['low']['ppa'][-1]
        + esdc.discrepancy['ga']['low']['wi'][-1] + esdc.discrepancy['ga']['low']['uc'][-1]
        + esdc.discrepancy['ga']['low']['cio'][-1]
prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['low'][-2] + discr - prod

return esdc.resources['ga']['low'][-1] == new_resources
```

### RE2004 - Non Associated Gas GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P90}} = \Delta G_{pn,t - 1}^{\text{P90}} + \Delta D_{G}^\text{um P90} + \Delta D_{G}^\text{ppa P90} + \Delta D_{G}^\text{wi P90} + \Delta D_{G}^\text{uc P90} + \Delta D_{G}^\text{cio P90} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['gn']['low']['um'][-1] + esdc.discrepancy['gn']['low']['ppa'][-1]
        + esdc.discrepancy['gn']['low']['wi'][-1] + esdc.discrepancy['gn']['low']['uc'][-1]
        + esdc.discrepancy['gn']['low']['cio'][-1]
prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['low'][-2] + discr - prod

return esdc.resources['gn']['low'][-1] == new_resources
```

### RE2005 - Oil GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P50}} = \Delta N_{pn,t - 1}^{\text{P50}} + \Delta D_{N}^\text{um P50} + \Delta D_{N}^\text{ppa P50} + \Delta D_{N}^\text{wi P50} + \Delta D_{N}^\text{uc P50} + \Delta D_{N}^\text{cio P50} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['oil']['mid']['um'][-1] + esdc.discrepancy['oil']['mid']['ppa'][-1]
        + esdc.discrepancy['oil']['mid']['wi'][-1] + esdc.discrepancy['oil']['mid']['uc'][-1]
        + esdc.discrepancy['oil']['mid']['cio'][-1]
prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['mid'][-2] + discr - prod

return esdc.resources['oil']['mid'][-1] == new_resources
```

### RE2006 - Condensate GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P50}} = \Delta N_{pn,t - 1}^{c \text{P50}} + \Delta D_{N^c}^\text{um P50} + \Delta D_{N^c}^\text{ppa P50} + \Delta D_{N^c}^\text{wi P50} + \Delta D_{N^c}^\text{uc P50} + \Delta D_{N^c}^\text{cio P50} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

```python
import esdc

discr = esdc.discrepancy['con']['mid']['um'][-1] + esdc.discrepancy['con']['mid']['ppa'][-1]
        + esdc.discrepancy['con']['mid']['wi'][-1] + esdc.discrepancy['con']['mid']['uc'][-1]
        + esdc.discrepancy['con']['mid']['cio'][-1]
prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['mid'][-2] + discr - prod

return esdc.resources['con']['mid'][-1] == new_resources
```

### RE2007 - Associated Gas GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P50}} = \Delta G_{pn,t - 1}^{a \text{P50}} + \Delta D_{G^a}^\text{um P50} + \Delta D_{G^a}^\text{ppa P50} + \Delta D_{G^a}^\text{wi P50} + \Delta D_{G^a}^\text{uc P50} + \Delta D_{G^a}^\text{cio P50} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

```python
import esdc

discr = esdc.discrepancy['ga']['mid']['um'][-1] + esdc.discrepancy['ga']['mid']['ppa'][-1]
        + esdc.discrepancy['ga']['mid']['wi'][-1] + esdc.discrepancy['ga']['mid']['uc'][-1]
        + esdc.discrepancy['ga']['mid']['cio'][-1]
prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['mid'][-2] + discr - prod

return esdc.resources['ga']['mid'][-1] == new_resources
```

### RE2008 - Non Associated Gas GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P50}} = \Delta G_{pn,t - 1}^{\text{P50}} + \Delta D_{G}^\text{um P50} + \Delta D_{G}^\text{ppa P50} + \Delta D_{G}^\text{wi P50} + \Delta D_{G}^\text{uc P50} + \Delta D_{G}^\text{cio P50} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['gn']['mid']['um'][-1] + esdc.discrepancy['gn']['mid']['ppa'][-1]
        + esdc.discrepancy['gn']['mid']['wi'][-1] + esdc.discrepancy['gn']['mid']['uc'][-1]
        + esdc.discrepancy['gn']['mid']['cio'][-1]
prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['mid'][-2] + discr - prod

return esdc.resources['gn']['mid'][-1] == new_resources
```

### RE2009 - Oil GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P10}} = \Delta N_{pn,t - 1}^{\text{P10}} + \Delta D_{N}^\text{um P10} + \Delta D_{N}^\text{ppa P10} + \Delta D_{N}^\text{wi P10} + \Delta D_{N}^\text{uc P10} + \Delta D_{N}^\text{cio P10} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['oil']['hgh']['um'][-1] + esdc.discrepancy['oil']['hgh']['ppa'][-1]
        + esdc.discrepancy['oil']['hgh']['wi'][-1] + esdc.discrepancy['oil']['hgh']['uc'][-1]
        + esdc.discrepancy['oil']['hgh']['cio'][-1]
prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['hgh'][-2] + discr - prod

return esdc.resources['oil']['hgh'][-1] == new_resources
```

### RE2010 - Condensate GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P10}} = \Delta N_{pn,t - 1}^{c \text{P10}} + \Delta D_{N^c}^\text{um P10} + \Delta D_{N^c}^\text{ppa P10} + \Delta D_{N^c}^\text{wi P10} + \Delta D_{N^c}^\text{uc P10} + \Delta D_{N^c}^\text{cio P10} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

```python
import esdc

discr = esdc.discrepancy['con']['hgh']['um'][-1] + esdc.discrepancy['con']['hgh']['ppa'][-1]
        + esdc.discrepancy['con']['hgh']['wi'][-1] + esdc.discrepancy['con']['hgh']['uc'][-1]
        + esdc.discrepancy['con']['hgh']['cio'][-1]
prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['hgh'][-2] + discr - prod

return esdc.resources['con']['hgh'][-1] == new_resources
```

### RE2011 - Associated Gas GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P10}} = \Delta G_{pn,t - 1}^{a \text{P10}} + \Delta D_{G^a}^\text{um P10} + \Delta D_{G^a}^\text{ppa P10} + \Delta D_{G^a}^\text{wi P10} + \Delta D_{G^a}^\text{uc P10} + \Delta D_{G^a}^\text{cio P10} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

```python
import esdc

discr = esdc.discrepancy['ga']['hgh']['um'][-1] + esdc.discrepancy['ga']['hgh']['ppa'][-1]
        + esdc.discrepancy['ga']['hgh']['wi'][-1] + esdc.discrepancy['ga']['hgh']['uc'][-1]
        + esdc.discrepancy['ga']['hgh']['cio'][-1]
prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['hgh'][-2] + discr - prod

return esdc.resources['ga']['hgh'][-1] == new_resources
```

### RE2012 - Non Associated Gas GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P10}} = \Delta G_{pn,t - 1}^{\text{P10}} + \Delta D_{G}^\text{um P10} + \Delta D_{G}^\text{ppa P10} + \Delta D_{G}^\text{wi P10} + \Delta D_{G}^\text{uc P10} + \Delta D_{G}^\text{cio P10} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['gn']['hgh']['um'][-1] + esdc.discrepancy['gn']['hgh']['ppa'][-1]
        + esdc.discrepancy['gn']['hgh']['wi'][-1] + esdc.discrepancy['gn']['hgh']['uc'][-1]
        + esdc.discrepancy['gn']['hgh']['cio'][-1]
prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['hgh'][-2] + discr - prod

return esdc.resources['gn']['hgh'][-1] == new_resources
```

### RE2013 - Oil Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P90}} = \Delta N_{pn,t - 1}^{\text{P90}} + \Delta D_{N}^\text{gtr P90} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['low'][-2] + esdc.discrepancy['oil']['low']['gtr'][-1] - prod

return esdc.resources['oil']['low'][-1] == new_resources
```

### RE2014 - Condensate Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P90}} = \Delta N_{pn,t - 1}^{c \text{P90}} + \Delta D_{N^c}^\text{gtr P90} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

```python
import esdc

prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['low'][-2] + esdc.discrepancy['con']['low']['gtr'][-1] - prod

return esdc.resources['con']['low'][-1] == new_resources
```

### RE2015 - Associated Gas Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P90}} = \Delta G_{pn,t - 1}^{a \text{P90}} + \Delta D_{G^a}^\text{gtr P90} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['low'][-2] + esdc.discrepancy['ga']['low']['gtr'][-1] - prod

return esdc.resources['ga']['low'][-1] == new_resources
```

### RE2016 - Non Associated Gas Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P90}} = \Delta G_{pn,t - 1}^{\text{P90}} + \Delta D_{G}^\text{gtr P90} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['low'][-2] + esdc.discrepancy['gn']['low']['gtr'][-1] - prod

return esdc.resources['gn']['low'][-1] == new_resources
```

### RE2017 - Oil Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P50}} = \Delta N_{pn,t - 1}^{\text{P50}} + \Delta D_{N}^\text{gtr P50} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['mid'][-2] + esdc.discrepancy['oil']['mid']['gtr'][-1] - prod

return esdc.resources['oil']['mid'][-1] == new_resources
```

### RE2018 - Condensate Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P50}} = \Delta N_{pn,t - 1}^{c \text{P50}} + \Delta D_{N^c}^\text{gtr P50} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

```python
import esdc

prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['mid'][-2] + esdc.discrepancy['con']['mid']['gtr'][-1] - prod

return esdc.resources['con']['mid'][-1] == new_resources
```

### RE2019 - Associated Gas Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P50}} = \Delta G_{pn,t - 1}^{a \text{P50}} + \Delta D_{G^a}^\text{gtr P50} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['mid'][-2] + esdc.discrepancy['ga']['mid']['gtr'][-1] - prod

return esdc.resources['ga']['mid'][-1] == new_resources
```

### RE2020 - Non Associated Gas Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P50}} = \Delta G_{pn,t - 1}^{\text{P50}} + \Delta D_{G}^\text{gtr P50} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['mid'][-2] + esdc.discrepancy['gn']['mid']['gtr'][-1] - prod

return esdc.resources['gn']['mid'][-1] == new_resources
```

### RE2021 - Oil Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P10}} = \Delta N_{pn,t - 1}^{\text{P10}} + \Delta D_{N}^\text{gtr P10} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['hgh'][-2] + esdc.discrepancy['oil']['hgh']['gtr'][-1] - prod

return esdc.resources['oil']['hgh'][-1] == new_resources
```

### RE2022 - Condensate Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P10}} = \Delta N_{pn,t - 1}^{c \text{P10}} + \Delta D_{N^c}^\text{gtr P10} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

```python
import esdc

prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['hgh'][-2] + esdc.discrepancy['con']['hgh']['gtr'][-1] - prod

return esdc.resources['con']['hgh'][-1] == new_resources
```

### RE2023 - Associated Gas Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P10}} = \Delta G_{pn,t - 1}^{a \text{P10}} + \Delta D_{G^a}^\text{gtr P10} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['hgh'][-2] + esdc.discrepancy['ga']['hgh']['gtr'][-1] - prod

return esdc.resources['ga']['hgh'][-1] == new_resources
```

### RE2024 - Non Associated Gas Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P10}} = \Delta G_{pn,t - 1}^{\text{P10}} + \Delta D_{G}^\text{gtr P10} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['hgh'][-2] + esdc.discrepancy['gn']['hgh']['gtr'][-1] - prod

return esdc.resources['gn']['hgh'][-1] == new_resources
```

### RE2025 - IOIP Mid: IOIP Mid should be higher than Sum of all projects Oil Ultimate GRR/CR/PR 3R/3C/3U if Sum of all projects Oil Ultimate GRR/CR/PR 3R/3C/3U higher than 0

Severity: `warning` :warning:

The following equation should be true:

$$\sum_{i=1}^n \left(\Delta N_{pn,i}^{\text{P10}} + N_{ps,i}\right) > 0  \implies N^{\text{P50}} > \sum_{i=1}^n \left(\Delta N_{pn,i}^{\text{P10}} + N_{ps,i}\right)$$

```python
import esdc

eur_P10 = esdc.resources['oil']['hgh'][-1].groupby('field').sum() + esdc.cumprod['oil']['sls'][-1]
return esdc.inplace['oil']['mid'][-1] > eur_P10 if eur_P10 > 0
```

### RE2026 - IGIP Mid: IGIP Mid should be higher than Sum of all projects Non Associated Gas Ultimate 3R/3C/3U if Sum of all projects Non Associated Gas Ultimate 3R/3C/3U higher than 0

Severity: `warning` :warning:

The following equation should be true:

$$ \sum_{i=1}^n \left(\Delta G_{pn,i}^{\text{P10}} + G_{ps,i}\right) > 0 \implies G^{\text{P50}} > \sum_{i=1}^n \left(\Delta G_{pn,i}^{\text{P10}} + G_{ps,i}\right)$$

```python
import esdc

eur_P10 = esdc.resources['gn']['hgh'][-1].groupby('field').sum() + esdc.cumprod['gn']['sls'][-1]
return esdc.inplace['gn']['mid'][-1] > eur_P10 if eur_P10 > 0
```

### RE2027 - IGIP Low: IGIP Low Case must be higher than 0 if Sum of all projects Condensate GRR/CR/PR 3R/3C/3U higher than 0

Notes: _Corrected rules. Check eSDC._

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{i=1}^n \left( \Delta N_{pn,i}^{c \text{P10}} + N_{ps,i}^c \right) > 0 \implies G^{\text{P90}} > 0$$

```python
import esdc

eur_P10 = esdc.resources['con']['hgh'][-1].groupby('field').sum() + esdc.cumprod['con']['sls'][-1]
return esdc.inplace['gn']['low'][-1] > 0 if eur_P10 > 0
```

### RE2028 - IOIP Low: IOIP Low Case must be higher than 0 if Sum of all projects Associated Gas GRR/CR/PR 3R/3C/3U higher than 0

Notes: _Corrected rules. Check eSDC._

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{i=1}^n \left( \Delta G_{pn,i}^{a \text{P10}} + G_{ps,i}^a \right) > 0 \implies N^{\text{P90}} > 0$$

```python
import esdc

eur_P10 = esdc.resources['ga']['hgh'][-1].groupby('field').sum() + esdc.cumprod['ga']['sls'][-1]
return esdc.inplace['oil']['low'][-1] > 0 if eur_P10 > 0
```

### RE2029 - IOIP Low: IOIP Low Case must be higher than sum of all projects oil EUR GRR/CR/PR 1R/1C/1U

Notes: _New Rules_

Severity: `strict` :no_entry:

The following equation must be true:

$$N^{\text{P90}} > \sum_{i=1}^n \left( \Delta N_{pn,i}^{\text{P90}} + N_{ps,i} \right) > 0 $$

```python
import esdc
```

The following example should pass:

``` al
if 
    Oil sales cumulative production = 1000
    IOIP Low = 1500

then
    validation result is True
```

``` al
if 
    Oil GRR/CR/PR = 1000
    IOIP Low = 1500

then
    validation result is True
```

The following example should fail:

``` al
if 
    Oil sales cumulative production = 1000
    IOIP Low = 0

then
    validation result is False
```

``` al
if 
    Oil GRR/CR/PR = 1000
    IOIP Low = 0

then
    validation result is False
```

### RE2030 - IGIP Low: IGIP Low Case must be higher than sum of all projects non associated gas EUR GRR/CR/PR 1R/1C/1U

Notes: _New Rules_

Severity: `strict` :no_entry:

The following equation must be true:

$$G^{\text{P90}} > \sum_{i=1}^n \left( \Delta G_{pn,i}^{\text{P90}} + G_{ps,i} \right) > 0 $$

```python
import esdc
```

The following example should pass:

``` al
if 
    non associated gas sales cumulative production = 1000
    IGIP Low = 1500

then
    validation result is True
```

``` al
if 
    non associated gas GRR/CR/PR = 1000
    IGIP Low = 1500

then
    validation result is True
```

``` al
if 
    non associated gas GRR/CR/PR = 1000
    IGIP Low = 0

then
    validation result is False
```

The following example should fail:

``` al
if 
    non associated gas sales cumulative production = 1000
    IGIP Low = 0

then
    validation result is False
```

``` al
if 
    non associated gas GRR/CR/PR = 1000
    IGIP Low = 0

then
    validation result is False
```