# eSDC 3.0 Rules Documentation

## Symbol Reference

The following symbol is used in this documentation. We use P90/P50/P10 as a generic symbol instead of using specific symbols such as R (GRR), C (Contingent), U (Prospective) for generic rules that apply equally to GRR, Contingent Resources, and Prospective Resources. In case of reserves, 1P/2P/3P is used.

| Symbols | Definition |
| --- | --- |
| $N^{\text{P90/P50/P10}}$ | Initial Oil in Place |
| $G^{\text{P90/P50/P10}}$ | Initial Gas in Place |
| $N_{p, g}$ | Oil Gross Cumulative Production |
| $N_{p, g}^c$ | Condensate Gross Cumulative Production |
| $G_{p, g}$ | Non Associated Gas Gross Cumulative Production|
| $G_{p, g}^a$ | Associated Gas Net Cumulative Production |
| $N_{p, n}$ | Oil Net Cumulative Production |
| $N_{p, n}^c$ | Condensate Net Cumulative Production |
| $G_{p, n}$ | Non Associated Gas Net Cumulative Production|
| $G_{p, n}^a$ | Associated Gas Net Cumulative Production |
| $N_{p, s}$ | Oil Sales Cumulative Production |
| $N_{p, s}^c$ | Condensate Sales Cumulative Production |
| $G_{p, s}$ | Non Associated Gas Sales Cumulative Production|
| $G_{p, s}^a$ | Associated Gas Sales Cumulative Production |
| $\Delta N_{p, n}^{\text{P90/P50/P10}}$| Oil GRR/CR/PR |
| $\Delta N_{p, n}^{c \text{ P90/P50/P10}}$ | Condensate GRR/CR/PR |
| $\Delta G_{p, n}^{\text{P90/P50/P10}}$ | Non Associated Gas GRR/CR/PR |
| $\Delta G_{p, n}^{a \text{ P90/P50/P10}}$ | Associated Gas GRR/CR/PR |
| $\Delta N_{p, s}^{\text{1P/2P/3P}}$| Oil Reserves |
| $\Delta N_{p, s}^{c \text{ 1P/2P/3P}}$ | Condensate Reserves |
| $\Delta G_{p, s}^{\text{1P/2P/3P}}$ | Non Associated Gas Reserves |
| $\Delta G_{p, s}^{a \text{ 1P/2P/3P}}$ | Associated Gas Reserves |
| $\Delta D_{N}^\text{um P90/P50/P10}$ | Oil Discrepancy from Update Model |
| $\Delta D_{N^c}^\text{um P90/P50/P10}$ | Condensate Discrepancy from Update Model |
| $\Delta D_{G}^\text{um P90/P50/P10}$ | Non Associated Gas Discrepancy from Update Model |
| $\Delta D_{G^a}^\text{um P90/P50/P10}$ | Associated Gas Discrepancy from Update Model |
| $\Delta D_{N}^\text{ppa P90/P50/P10}$ | Oil Discrepancy from Production Performance Analysis |
| $\Delta D_{N^c}^\text{ppa P90/P50/P10}$ | Condensate Discrepancy from Production Performance Analysis |
| $\Delta D_{G}^\text{ppa P90/P50/P10}$ | Non Associated Gas Discrepancy from Production Performance Analysis |
| $\Delta D_{G^a}^\text{ppa P90/P50/P10}$ | Associated Gas Discrepancy from Production Performance Analysis |
| $\Delta D_{N}^\text{wi P90/P50/P10}$ | Oil Discrepancy from Well Intervention |
| $\Delta D_{N^c}^\text{wi P90/P50/P10}$ | Condensate Discrepancy from Well Intervention |
| $\Delta D_{G}^\text{wi P90/P50/P10}$ | Non Associated Gas Discrepancy from Well Intervention |
| $\Delta D_{G^a}^\text{wi P90/P50/P10}$ | Associated Gas Discrepancy from Well Intervention |
| $q_{o, t \dots t_n}^{s}$ | Oil Sales yearly rate forecast|
| $q_{c, t \dots t_n}^{s}$ | Condensate Sales yearly rate forecast|
| $q_{a, t \dots t_n}^{s}$ | Associated Gas Sales yearly rate forecast|
| $q_{n, t \dots t_n}^{s}$ | Non Associated Gas Sales yearly rate forecast|
| $q_{o, t \dots t_n}^{\text{tp}}$ | Oil Total Potential yearly rate forecast|
| $q_{c, t \dots t_n}^{\text{tp}}$ | Condensate Total Potential yearly rate forecast|
| $q_{a, t \dots t_n}^{\text{tp}}$ | Associated Gas Total Potential yearly rate forecast|
| $q_{n, t \dots t_n}^{\text{tp}}$ | Non Associated Gas Total Potential yearly rate forecast|

## Keyword Reference

| Keyword | Filter | Aggregation | Agg Type | Description |
| --------- | --- | --- | --- | --- |
| `inplace` | fluid type, uncertainty, time reference | zone, field, working area | `sum` | Initial in Place |
| `cumprod` | fluid type, commerciality, time reference | project, field, working area | `sum` | Cumulative Production |
| `resources` | fluid type, uncertainty, time reference | project, field, working area | `sum` | GRR, Contingent Resources, Prospective Resources |
| `reserves` | fluid type, uncertainty, time reference | project, field, working area | `sum` | Reserves |
| `forecast` | fluid type, commerciality, time reference | project, field, working area | `sum` | Production Forecast |
| `discrepancy` | fluid type, uncertainty,  discrepancy sources, time reference | field, working area | `sum` | Discrepancy |
| `grv` | uncertainty | zone, field, working area | `sum` | Gross Rock Volume |
| `ntg` | uncertainty | zone, field, working area | `mean` | Net to Gross, weighted to GRV |
| `netpay` | uncertainty | zone, field, working area | `sum` | Net Pay |
| `poro_eff` | uncertainty | zone, field, working area | `mean` | Average Effective Porosity, weighted to GRV |
| `sat_oil_init` | uncertainty | zone, field, working area | `mean` | Initial Oil Saturation, weighted to GRV |
| `sat_gas_init` | uncertainty | zone, field, working area | `mean` | Initial Gas Saturation, weighted to GRV |
| `shrinkage_oil` | uncertainty | zone, field, working area | `har_mean` | Oil Shrinkage Factor |
| `shrinkage_gas` | uncertainty | zone, field, working area | `har_mean` | Gas Shrinkage Factor |
| `perm_abs` | uncertainty | zone, field, working area | `har_mean` | Absolute Permeability |
| `gcf_srock` | - | zone, field, working area | `mean` | GCF Source Rock |
| `depth_avg` | - | zone, field, working area, basin, vol. calc. method, all play elements | `mean`| Average Reservoir Depth

## Syntax for eSDC Rules

eSDC module API:

```python
import esdc

esdc.inplace[fluid_type][uncert_level][time_ref]
esdc.cumprod[commerciality][fluid_type][time_ref].groupby('field')
esdc.resources[fluid_type][uncert_level][time_ref].groupby('field')
```

## Rules Definition

| Rules Code | Description             |
| ---------- | ----------------------- |
| RE0        | Volumetric              |
| RE1        | Production and forecast |
| RE2        | Material Balance        |
| RE3        | Reservoir Properties    |
| RE4        | Analytics               |

### RE0001 - IOIP: Low Case must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$ N^{\text{P90}} \geq 0 $$

```python
import esdc

return esdc.inplace['oil']['low'][-1] >= 0
```

### RE0002 - IGIP: Low Case must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$ G^{\text{P90}} \geq 0 $$

```python
import esdc

return esdc.inplace['gn']['low'][-1] >= 0
```

### RE0003 - IOIP: Low Case must be less than or equal to Mid Case

Severity: `strict`

The following equation must be true:

$$N^{\text{P90}} < N^{\text{P50}}$$

```python
import esdc

return esdc.inplace['oil']['low'][-1] <= esdc.inplace['oil']['mid'][-1]
```

### RE0004 - IOIP: Mid Case must be less than or equal to High Case

Severity: `strict`

The following equation must be true:

$$N^{\text{P50}} < N^{\text{P10}}$$

```python
import esdc

return esdc.inplace['oil']['mid'][-1] <= esdc.inplace['oil']['hgh'][-1]
```

### RE0005 - IGIP: Low Case must be less than or equal to Mid Case

Severity: `strict`

The following equation must be true:

$$G^{\text{P90}} < G^{\text{P50}}$$

```python
import esdc

return esdc.inplace['gn']['low'][-1] <= esdc.inplace['gn']['mid'][-1]
```

### RE0006 - IGIP: Mid Case must be less or equal than High Case

Severity: `strict`

The following equation must be true:

$$G^{\text{P50}} < G^{\text{P10}}$$

```python
import esdc

return esdc.inplace['gn']['mid'][-1] <= esdc.inplace['gn']['hgh'][-1]
```

### RE0007 - Oil GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \geq 0$$

```python
import esdc

return esdc.resources['oil']['low'][-1] >= 0
```

### RE0008 - Condensate GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \geq 0$$

```python
import esdc

return esdc.resources['oil']['low'][-1] >= 0
```

### RE0009 - Associated Gas GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \geq 0$$

```python
import esdc

return esdc.resources['ga']['low'][-1] >= 0
```

### RE0010 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \geq 0$$

```python
import esdc

return esdc.resources['gn']['low'][-1] >= 0
```

### RE0011 - Oil Reserves: 1P must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \geq 0$$

```python
import esdc

return esdc.reserves['oil']['low'][-1] >= 0
```

### RE0012 - Condensate Reserves: 1P must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{c\text{ 1P}} \geq 0$$

```python
import esdc

return esdc.reserves['con']['low'][-1] >= 0
```

### RE0013 - Associated Gas Reserves: 1P must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \geq 0$$

```python
import esdc

return esdc.reserves['ga']['low'][-1] >= 0
```

### RE0014 - Non Associated Gas Reserves: 1P must be higher than or equal to 0

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{\text{ 1P}} \geq 0$$

```python
import esdc

return esdc.reserves['gn']['low'][-1] >= 0
```

### RE0015 - Oil GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity: `strict`

The following equation must be true:

$$\Delta N_{pn}^{\text{P90}} \leq \Delta N_{p}^{\text{P50}} $$

```python
import esdc

return esdc.resources['oil']['low'][-1] <= esdc.resources['oil']['mid'][-1]
```

### RE0016 - Oil GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity: `strict`

The following equation must be true:

$$\Delta N_{pn}^{\text{P50}} \leq \Delta N_{pn}^{\text{P10}} $$

```python
import esdc

return esdc.resources['oil']['mid'][-1] <= esdc.resources['oil']['hgh'][-1]
```

### RE0017 - Condensate GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity: `strict`

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P90}} \leq \Delta N_{pn}^{c \text{ P50}} $$

```python
import esdc

return esdc.resources['con']['low'][-1] <= esdc.resources['con']['mid'][-1]
```

### RE0018 - Condensate GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity: `strict`

The following equation must be true:

$$\Delta N_{pn}^{c \text{ P50}} \leq \Delta N_{pn}^{c \text{ P10}} $$

```python
import esdc

return esdc.resources['con']['mid'][-1] <= esdc.resources['con']['hgh'][-1]
```

### RE0019 - Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity: `strict`

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P90}} \leq \Delta G_{pn}^{a \text{ P50}} $$

```python
import esdc

return esdc.resources['ga']['low'][-1] <= esdc.resources['ga']['mid'][-1]
```

### RE0020 - Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity: `strict`

The following equation must be true:

$$\Delta G_{pn}^{a \text{ P50}} \leq \Delta G_{pn}^{a \text{ P10}} $$

```python
import esdc

return esdc.resources['ga']['mid'][-1] <= esdc.resources['ga']['hgh'][-1]
```

### RE0021 - Non Associated Gas GRR/CR/PR: 1R/1C/1U must be less than or equal to 2R/2C/2U

Severity: `strict`

The following equation must be true:

$$\Delta G_{pn}^{\text{P90}} \leq \Delta G_{pn}^{\text{P50}} $$

```python
import esdc

return esdc.resources['gn']['low'][-1] <= esdc.resources['gn']['mid'][-1]
```

### RE0022 - Non Associated Gas GRR/CR/PR: 2R/2C/2U must be less than or equal to 3R/3C/3U

Severity: `strict`

The following equation must be true:

$$\Delta G_{pn}^{\text{P50}} \leq \Delta G_{pn}^{\text{P10}} $$

```python
import esdc

return esdc.resources['gn']['mid'][-1] <= esdc.resources['gn']['hgh'][-1]
```

### RE0023 - Oil Reserves: 1P must be less than or equal to 2P

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{ps}^{\text{2P}} $$

```python
import esdc

return esdc.reserves['oil']['low'][-1] <= esdc.reserves['oil']['mid'][-1]
```

### RE0024 - Oil Reserves: 2P must be less than or equal to 3P

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{ps}^{\text{3P}} $$

```python
import esdc

return esdc.reserves['oil']['mid'][-1] <= esdc.reserves['oil']['hgh'][-1]
```

### RE0025 - Condensate Reserves: 1P must be less than or equal to 2P

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{ps}^{c \text{ 1P}} $$

```python
import esdc

return esdc.reserves['con']['low'][-1] <= esdc.reserves['con']['mid'][-1]
```

### RE0026 - Condensate Reserves: 2P must be less than or equal to 3P

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{ps}^{c \text{ 3P}} $$

```python
import esdc

return esdc.reserves['con']['mid'][-1] <= esdc.reserves['con']['hgh'][-1]
```

### RE0027 - Associated Gas Reserves: 1P must be less than or equal to 2P

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{ps}^{a \text{ 2P}} $$

```python
import esdc

return esdc.reserves['ga']['low'][-1] <= esdc.reserves['ga']['mid'][-1]
```

### RE0028 - Associated Gas Reserves: 2P must be less than or equal to 3P

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{ps}^{a \text{ 3P}} $$

```python
import esdc

return esdc.reserves['ga']['mid'][-1] <= esdc.reserves['ga']['hgh'][-1]
```

### RE0029 - Non Associated Gas Reserves: 1P must be less than or equal to 2P

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{ps}^{\text{2P}} $$

```python
import esdc

return esdc.reserves['gn']['low'][-1] <= esdc.reserves['gn']['mid'][-1]
```

### RE0030 - Non Associated Gas Reserves: 2P must be less than or equal to 3P

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{ps}^{\text{3P}} $$

```python
import esdc

return esdc.reserves['gn']['mid'][-1] <= esdc.reserves['gn']['hgh'][-1]
```

### RE0031 - Oil Reserves: 1P must be less than or equal to 1R

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{\text{1P}} \leq \Delta N_{pn}^{\text{1R}}$$

```python
import esdc

return esdc.reserves['oil']['low'][-1] <= esdc.resources['oil']['low'][-1]
```

### RE0032 - Oil Reserves: 2P must be less than or equal to 2R

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{\text{2P}} \leq \Delta N_{pn}^{\text{2R}}$$

```python
import esdc

return esdc.reserves['oil']['mid'][-1] <= esdc.resources['oil']['mid'][-1]
```

### RE0033 - Oil Reserves: 3P must be less than or equal to 3R

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{\text{3P}} \leq \Delta N_{pn}^{\text{3R}}$$

```python
import esdc

return esdc.reserves['oil']['hgh'][-1] <= esdc.resources['oil']['hgh'][-1]
```

### RE0034 - Condensate Reserves: 1P must be less than or equal to 1R

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 1P}} \leq \Delta N_{pn}^{c \text{ 1R}}$$

```python
import esdc

return esdc.reserves['con']['low'][-1] <= esdc.resources['con']['low'][-1]
```

### RE0035 - Condensate Reserves: 2P must be less than or equal to 2R

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 2P}} \leq \Delta N_{pn}^{c \text{ 2R}}$$

```python
import esdc

return esdc.reserves['con']['mid'][-1] <= esdc.resources['con']['mid'][-1]
```

### RE0036 - Condensate Reserves: 3P must be less than or equal to 3R

Severity: `strict`

The following equation must be true:

$$\Delta N_{ps}^{c \text{ 3P}} \leq \Delta N_{pn}^{c \text{ 3R}}$$

```python
import esdc

return esdc.reserves['con']['hgh'][-1] <= esdc.resources['con']['hgh'][-1]
```

### RE0037 - Associated Gas Reserves: 1P must be less than or equal to 1R

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 1P}} \leq \Delta G_{pn}^{a \text{ 1R}}$$

```python
import esdc

return esdc.reserves['ga']['low'][-1] <= esdc.resources['ga']['low'][-1]
```

### RE0038 - Associated Gas Reserves: 2P must be less than or equal to 2R

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 2P}} \leq \Delta G_{pn}^{a \text{ 2R}}$$

```python
import esdc

return esdc.reserves['ga']['mid'][-1] <= esdc.resources['ga']['mid'][-1]
```

### RE0039 - Associated Gas Reserves: 3P must be less than or equal to 3R

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{a \text{ 3P}} \leq \Delta G_{pn}^{a \text{ 3R}}$$

```python
import esdc

return esdc.reserves['ga']['hgh'][-1] <= esdc.resources['ga']['hgh'][-1]
```

### RE0040 - Non Associated Gas Reserves: 1P must be less than or equal to 1R

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{\text{1P}} \leq \Delta G_{pn}^{\text{1R}}$$

```python
import esdc

return esdc.reserves['gn']['low'][-1] <= esdc.resources['gn']['low'][-1]
```

### RE0041 - Non Associated Gas Reserves: 2P must be less than or equal to 2R

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{\text{2P}} \leq \Delta G_{pn}^{\text{2R}}$$

```python
import esdc

return esdc.reserves['gn']['mid'][-1] <= esdc.resources['gn']['mid'][-1]
```

### RE0042 - Associated Gas Reserves: 3P must be less than or equal to 3R

Severity: `strict`

The following equation must be true:

$$\Delta G_{ps}^{\text{3P}} \leq \Delta G_{pn}^{\text{3R}}$$

```python
import esdc

return esdc.reserves['gn']['hgh'][-1] <= esdc.resources['gn']['hgh'][-1]
```

### RE1001 - Oil Gross Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$N_{pg} \geq 0$$

```python
import esdc

return esdc.cumprod['oil']['grs'][-1] >= 0
```

### RE1002 - Condensate Gross Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$N_{pg}^c \geq 0$$

```python
import esdc

return esdc.cumprod['con']['grs'][-1] >= 0
```

### RE1003 - Associated Gas Gross Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$G_{pg}^a \geq 0$$

```python
import esdc

return esdc.cumprod['ga']['grs'][-1] >= 0
```

### RE1004 - Non Associated Gas Gross Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$G_{pg} \geq 0$$

```python
import esdc

return esdc.cumprod['gn']['grs'][-1] >= 0
```

### RE1005 - Oil Net Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$N_{pn} \geq 0$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] >= 0
```

### RE1006 - Condensate Net Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$N_{pn}^c \geq 0$$

```python
import esdc

return esdc.cumprod['con']['net'][-1] >= 0
```

### RE1007 - Associated Gas Net Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$G_{pn}^a \geq 0$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] >= 0
```

### RE1008 - Non Associated Gas Net Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$G_{pn} \geq 0$$

```python
import esdc

return esdc.cumprod['gn']['net'][-1] >= 0
```

### RE1009 - Oil Sales Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$N_{ps} \geq 0$$

```python
import esdc

return esdc.cumprod['oil']['sls'][-1] >= 0
```

### RE1010 - Condensate Sales Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$N_{ps}^c \geq 0$$

```python
import esdc

return esdc.cumprod['con']['sls'][-1] >= 0
```

### RE1011 - Associated Gas Sales Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$G_{ps}^a \geq 0$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] >= 0
```

### RE1012 - Non Associated Gas Sales Cumprod: Must be positive or equal to 0

Severity: `strict`

The following equation must be true:

$$G_{ps} \geq 0$$

```python
import esdc

return esdc.cumprod['gn']['net'][-1] >= 0
```

### RE1013 - Oil Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$N_{pg, t} \geq N_{pg, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['grs'][-1] >= esdc.cumprod['oil']['grs'][-2]
```

### RE1014 - Condensate Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$N_{pg, t}^c \geq N_{pg, t - 1}^c$$

```python
import esdc

return esdc.cumprod['con']['grs'][-1] >= esdc.cumprod['con']['grs'][-2]
```

### RE1015 - Associated Gas Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$G_{pg, t}^a \geq G_{pg, t - 1}^a$$

```python
import esdc

return esdc.cumprod['ga']['grs'][-1] >= esdc.cumprod['ga']['grs'][-2]
```

### RE1016 - Non Associated Gas Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$G_{pg, t} \geq G_{pg, t - 1}$$

```python
import esdc

return esdc.cumprod['gn']['grs'][-1] >= esdc.cumprod['gn']['grs'][-2]
```

### RE1017 - Oil Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$N_{pn, t} \geq N_{pn, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] >= esdc.cumprod['oil']['net'][-2]
```

### RE1018 - Condensate Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$N_{pn, t}^c \geq N_{pn, t - 1}^c$$

```python
import esdc

return esdc.cumprod['con']['net'][-1] >= esdc.cumprod['con']['net'][-2]
```

### RE1019 - Associated Gas Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$G_{pn, t}^a \geq G_{pn, t - 1}^a$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] >= esdc.cumprod['ga']['net'][-2]
```

### RE1020 - Non Associated Gas Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$G_{pn, t} \geq G_{pn, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] >= esdc.cumprod['oil']['net'][-2]
```

### RE1021 - Oil Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$N_{ps, t} \geq N_{ps, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['sls'][-1] >= esdc.cumprod['oil']['sls'][-2]
```

### RE1022 - Condensate Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$N_{ps, t}^c \geq N_{ps, t - 1}^c$$

```python
import esdc

return esdc.cumprod['con']['sls'][-1] >= esdc.cumprod['con']['sls'][-2]
```

### RE1023 - Associated Gas Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$G_{ps, t}^a \geq G_{ps, t - 1}^a$$

```python
import esdc

return esdc.cumprod['ga']['sls'][-1] >= esdc.cumprod['ga']['sls'][-2]
```

### RE1024 - Non Associated Gas Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict`

The following equation must be true:

$$G_{ps, t} \geq G_{ps, t - 1}$$

```python
import esdc

return esdc.cumprod['gn']['sls'][-1] >= esdc.cumprod['gn']['sls'][-2]
```

### RE1025 - Oil Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$N_{pn} \leq N_{pg}$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] <= esdc.cumprod['oil']['grs'][-1]
```

### RE1026 - Condensate Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$N_{pn}^c \leq N_{pg}^c$$

```python
import esdc

return esdc.cumprod['con']['net'][-1] <= esdc.cumprod['con']['grs'][-1]
```

### RE1027 - Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$G_{pn}^a \leq G_{pg}^a$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] <= esdc.cumprod['ga']['grs'][-1]
```

### RE1028 - Non Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$G_{pn} \leq G_{pg}$$

```python
import esdc

return esdc.cumprod['gn']['net'][-1] <= esdc.cumprod['gn']['grs'][-1]
```

### RE1029 - Oil Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$N_{ps} \leq N_{ps}$$

```python
import esdc

return esdc.cumprod['oil']['sls'][-1] <= esdc.cumprod['oil']['grs'][-1]
```

### RE1030 - Condensate Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$N_{ps}^c \leq N_{pg}^c$$

```python
import esdc

return esdc.cumprod['con']['sls'][-1] <= esdc.cumprod['con']['grs'][-1]
```

### RE1031 - Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$G_{ps}^a \leq G_{pg}^a$$

```python
import esdc

return esdc.cumprod['ga']['sls'][-1] <= esdc.cumprod['ga']['grs'][-1]
```

### RE1032 - Non Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict`

The following equation must be true:

$$G_{ps} \leq G_{pg}$$

```python
import esdc

return esdc.cumprod['gn']['sls'][-1] <= esdc.cumprod['gn']['grs'][-1]
```

### RE1033 - Oil Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict`

The following equation must be true:

$$q_{o, t\dots t_n}^{s} \leq q_{o, t\dots t_n}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['oil']['sls'][-1] <= esdc.forecast['oil']['tp'][:][-1]
```

### RE1034 - Condensate Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict`

The following equation must be true:

$$q_{c, t\dots t_n}^{s} \leq q_{c, t\dots t_n}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['con']['sls'][-1] <= esdc.forecast['con']['tp'][:][-1]
```

### RE1035 - Associated Gas Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict`

The following equation must be true:

$$q_{a, t\dots t_n}^{s} \leq q_{a, t\dots t_n}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['ga']['sls'][-1] <= esdc.forecast['ga']['tp'][:][-1]
```

### RE1036 - Non Associated Gas Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict`

The following equation must be true:

$$q_{n, t}^{s} \leq q_{n, t}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['gn']['sls'][-1] <= esdc.forecast['gn']['tp'][:][-1]
```

### RE1037 - Oil Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{o, t}^{s} = \Delta N_{p, s}^{\text{2P}}$$

```python
import esdc

return esdc.forecast['oil']['sls'][-1].groupby('project') == esdc.reserves['oil']['mid'][-1]
```

### RE1038 - Condensate Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{c, t}^{s} = \Delta N_{p, s}^{c\text{ 2P}}$$

```python
import esdc

return esdc.forecast['con']['sls'][-1].groupby('project') == esdc.reserves['con']['mid'][-1]
```

### RE1039 - Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{a, t}^{s} = \Delta G_{p, s}^{a \text{ 2P}}$$

```python
import esdc

return esdc.forecast['ga']['sls'][-1].groupby('project') == esdc.reserves['ga']['mid'][-1]
```

### RE1040 - Non Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{n, t}^{s} = \Delta G_{p, s}^{\text{2P}}$$

```python
import esdc

return esdc.forecast['gn']['sls'][-1].groupby('project') == esdc.reserves['gn']['mid'][-1]
```

### RE1041 - Oil Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{o, t}^{\text{tp}} = \Delta N_{p, n}^{\text{P50}}$$

```python
import esdc

return esdc.forecast['oil']['tp'][-1].groupby('project').sum() == esdc.resources['oil']['mid'][-1]
```

### RE1042 - Condensate Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{c, t}^{\text{tp}} = \Delta N_{p, n}^{c\text{ P50}}$$

```python
import esdc

return esdc.forecast['con']['tp'][-1].groupby('project').sum() == esdc.resources['con']['mid'][-1]
```

### RE1043 - Associated  Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{a, t}^{\text{tp}} = \Delta G_{p, n}^{a\text{ P50}}$$

```python
import esdc

return esdc.forecast['ga']['tp'][-1].groupby('project').sum() == esdc.resources['ga']['mid'][-1]
```

### RE1044 - Non Associated Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict`

The following equation must be true:

$$\sum_{t=t}^n q_{a, t}^{\text{tp}} = \Delta G_{p, n}^{\text{P50}}$$

```python
import esdc

return esdc.forecast['gn']['tp'][-1].groupby('project').sum() == esdc.resources['gn']['mid'][-1]
```

### RE2001 - Oil GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{\text{P90}} = \Delta N_{p, n, t - 1}^{\text{P90}} + \Delta D_{N}^\text{um P90} + \Delta D_{N}^\text{ppa P90} + \Delta D_{N}^\text{wi P90} + \Delta D_{N}^\text{uc P90} - \left(N_{p, s, t} - N_{p, s, t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['oil']['low']['um'][-1] + esdc.discrepancy['oil']['low']['ppa'][-1]
        + esdc.discrepancy['oil']['low']['wi'][-1] + esdc.discrepancy['oil']['low']['uc'][-1]
prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['low'][-2] + discr + prod

return esdc.resources['oil']['low'][-1] == new_resources
```

### RE2002 - Condensate GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{c\text{ P90}} = \Delta N_{p, n, t - 1}^{c\text{ P90}} + \Delta D_{N^c}^\text{um P90} + \Delta D_{N^c}^\text{ppa P90} + \Delta D_{N^c}^\text{wi P90} + \Delta D_{N^c}^\text{uc P90} - \left(N_{p, s, t}^c - N_{p, s, t - 1}^c\right)$$

```python
import esdc

discr = esdc.discrepancy['con']['low']['um'][-1] + esdc.discrepancy['con']['low']['ppa'][-1]
        + esdc.discrepancy['con']['low']['wi'][-1] + esdc.discrepancy['con']['low']['uc'][-1]
prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['low'][-2] + discr + prod

return esdc.resources['con']['low'][-1] == new_resources
```

### RE2003 - Associated Gas GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P90}} = \Delta G_{p, n, t - 1}^{a\text{ P90}} + \Delta D_{G^a}^\text{um P90} + \Delta D_{G^a}^\text{ppa P90} + \Delta D_{G^a}^\text{wi P90} + \Delta D_{G^a}^\text{uc P90} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

discr = esdc.discrepancy['ga']['low']['um'][-1] + esdc.discrepancy['ga']['low']['ppa'][-1]
        + esdc.discrepancy['con']['low']['wi'][-1] + esdc.discrepancy['ga']['low']['uc'][-1]
prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['low'][-2] + discr + prod

return esdc.resources['ga']['low'][-1] == new_resources
```

### RE2004 - Non Associated Gas GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{\text{P90}} = \Delta G_{p, n, t - 1}^{\text{ P90}} + \Delta D_{G}^\text{um P90} + \Delta D_{G}^\text{ppa P90} + \Delta D_{G}^\text{wi P90} + \Delta D_{G}^\text{uc P90} - \left(G_{p, s, t} - G_{p, s, t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['gn']['low']['um'][-1] + esdc.discrepancy['gn']['low']['ppa'][-1]
        + esdc.discrepancy['gn']['low']['wi'][-1] + esdc.discrepancy['gn']['low']['uc'][-1]
prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['low'][-2] + discr + prod

return esdc.resources['gn']['low'][-1] == new_resources
```

### RE2005 - Oil GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{\text{P50}} = \Delta N_{p, n, t - 1}^{\text{P50}} + \Delta D_{N}^\text{um P50} + \Delta D_{N}^\text{ppa P50} + \Delta D_{N}^\text{wi P50} + \Delta D_{N}^\text{uc P50} - \left(N_{p, s, t} - N_{p, s, t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['oil']['mid']['um'][-1] + esdc.discrepancy['oil']['mid']['ppa'][-1]
        + esdc.discrepancy['oil']['mid']['wi'][-1] + esdc.discrepancy['oil']['mid']['uc'][-1]
prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['mid'][-2] + discr - prod

return esdc.resources['oil']['mid'][-1] == new_resources
```

### RE2006 - Condensate GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{c\text{ P50}} = \Delta N_{p, n, t - 1}^{c\text{ P50}} + \Delta D_{N^c}^\text{um P50} + \Delta D_{N^c}^\text{ppa P50} + \Delta D_{N^c}^\text{wi P50} + \Delta D_{N^c}^\text{uc P50} - \left(N_{p, s, t}^c - N_{p, s, t - 1}^c\right)$$

```python
import esdc

discr = esdc.discrepancy['con']['mid']['um'][-1] + esdc.discrepancy['con']['mid']['ppa'][-1]
        + esdc.discrepancy['con']['mid']['wi'][-1] + esdc.discrepancy['con']['mid']['uc'][-1]
prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['mid'][-2] + discr - prod

return esdc.resources['con']['mid'][-1] == new_resources
```

### RE2007 - Associated Gas GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P50}} = \Delta G_{p, n, t - 1}^{a\text{ P50}} + \Delta D_{G^a}^\text{um P50} + \Delta D_{G^a}^\text{ppa P50} + \Delta D_{G^a}^\text{wi P50} + \Delta D_{G^a}^\text{uc P50} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

discr = esdc.discrepancy['ga']['mid']['um'][-1] + esdc.discrepancy['ga']['mid']['ppa'][-1]
        + esdc.discrepancy['con']['mid']['wi'][-1] + esdc.discrepancy['ga']['mid']['uc'][-1]
prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['mid'][-2] + discr - prod

return esdc.resources['ga']['mid'][-1] == new_resources
```

### RE2008 - Non Associated Gas GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{\text{P50}} = \Delta G_{p, n, t - 1}^{\text{ P50}} + \Delta D_{G}^\text{um P50} + \Delta D_{G}^\text{ppa P50} + \Delta D_{G}^\text{wi P50} + \Delta D_{G}^\text{uc P50} - \left(G_{p, s, t} - G_{p, s, t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['gn']['mid']['um'][-1] + esdc.discrepancy['gn']['mid']['ppa'][-1]
        + esdc.discrepancy['gn']['mid']['wi'][-1] + esdc.discrepancy['gn']['mid']['uc'][-1]
prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['mid'][-2] + discr - prod

return esdc.resources['gn']['mid'][-1] == new_resources
```

### RE2009 - Oil GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{\text{P10}} = \Delta N_{p, n, t - 1}^{\text{P10}} + \Delta D_{N}^\text{um P10} + \Delta D_{N}^\text{ppa P10} + \Delta D_{N}^\text{wi P10} + \Delta D_{N}^\text{uc P10} - \left(N_{p, s, t} - N_{p, s, t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['oil']['hgh']['um'][-1] + esdc.discrepancy['oil']['hgh']['ppa'][-1]
        + esdc.discrepancy['oil']['hgh']['wi'][-1] + esdc.discrepancy['oil']['hgh']['uc'][-1]
prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['hgh'][-2] + discr - prod

return esdc.resources['oil']['hgh'][-1] == new_resources
```

### RE2010 - Condensate GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{c\text{ P10}} = \Delta N_{p, n, t - 1}^{c\text{ P10}} + \Delta D_{N^c}^\text{um P10} + \Delta D_{N^c}^\text{ppa P10} + \Delta D_{N^c}^\text{wi P10} + \Delta D_{N^c}^\text{uc P10} - \left(N_{p, s, t}^c - N_{p, s, t - 1}^c\right)$$

```python
import esdc

discr = esdc.discrepancy['con']['hgh']['um'][-1] + esdc.discrepancy['con']['hgh']['ppa'][-1]
        + esdc.discrepancy['con']['hgh']['wi'][-1] + esdc.discrepancy['con']['hgh']['uc'][-1]
prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['hgh'][-2] + discr - prod

return esdc.resources['con']['hgh'][-1] == new_resources
```

### RE2011 - Associated Gas GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P10}} = \Delta G_{p, n, t - 1}^{a\text{ P10}} + \Delta D_{G^a}^\text{um P10} + \Delta D_{G^a}^\text{ppa P10} + \Delta D_{G^a}^\text{wi P10} + \Delta D_{G^a}^\text{uc P10} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

discr = esdc.discrepancy['ga']['hgh']['um'][-1] + esdc.discrepancy['ga']['hgh']['ppa'][-1]
        + esdc.discrepancy['con']['hgh']['wi'][-1] + esdc.discrepancy['ga']['hgh']['uc'][-1]
prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['hgh'][-2] + discr - prod

return esdc.resources['ga']['hgh'][-1] == new_resources
```

### RE2012 - Non Associated Gas GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{\text{P10}} = \Delta G_{p, n, t - 1}^{\text{ P10}} + \Delta D_{G}^\text{um P10} + \Delta D_{G}^\text{ppa P10} + \Delta D_{G}^\text{wi P10} + \Delta D_{G}^\text{uc P10} - \left(G_{p, s, t} - G_{p, s, t - 1}\right)$$

```python
import esdc

discr = esdc.discrepancy['gn']['hgh']['um'][-1] + esdc.discrepancy['gn']['hgh']['ppa'][-1]
        + esdc.discrepancy['gn']['hgh']['wi'][-1] + esdc.discrepancy['gn']['hgh']['uc'][-1]
prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['hgh'][-2] + discr - prod

return esdc.resources['gn']['hgh'][-1] == new_resources
```

### RE2013 - Oil Reserves: Current 1P must be consistent with previous 1P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{\text{P90}} = \Delta N_{p, n, t - 1}^{\text{P90}} + \Delta D_{N}^\text{gtr P90} - \left(N_{p, s, t} - N_{p, s, t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['low'][-2] + esdc.discrepancy['oil']['low']['gtr'][-1] - prod

return esdc.resources['oil']['low'][-1] == new_resources
```

### RE2014 - Condensate Reserves: Current 1P must be consistent with previous 1P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{c\text{ P90}} = \Delta N_{p, n, t - 1}^{c\text{ P90}} + \Delta D_{N^c}^\text{gtr P90} - \left(N_{p, s, t}^c - N_{p, s, t - 1}^c\right)$$

```python
import esdc

prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['low'][-2] + esdc.discrepancy['con']['low']['gtr'][-1] - prod

return esdc.resources['con']['low'][-1] == new_resources
```

### RE2015 - Associated Gas Reserves: Current 1P must be consistent with previous 1P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P90}} = \Delta G_{p, n, t - 1}^{a\text{ P90}} + \Delta D_{G^a}^\text{gtr P90} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['low'][-2] + esdc.discrepancy['ga']['low']['gtr'][-1] - prod

return esdc.resources['ga']['low'][-1] == new_resources
```

### RE2016 - Non Associated Gas Reserves: Current 1P must be consistent with previous 1P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{\text{P90}} = \Delta G_{p, n, t - 1}^{\text{P90}} + \Delta D_{G}^\text{gtr P90} - \left(G_{p, s, t} - G_{p, s, t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['low'][-2] + diesdc.discrepancy['gn']['low']['gtr'][-1]scr - prod

return esdc.resources['gn']['low'][-1] == new_resources
```

### RE2017 - Oil Reserves: Current 2P must be consistent with previous 2P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{\text{P50}} = \Delta N_{p, n, t - 1}^{\text{P50}} + \Delta D_{N}^\text{gtr P50} - \left(N_{p, s, t} - N_{p, s, t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['mid'][-2] + esdc.discrepancy['oil']['mid']['gtr'][-1] - prod

return esdc.resources['oil']['mid'][-1] == new_resources
```

### RE2018 - Condensate Reserves: Current 2P must be consistent with previous 2P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{c\text{ P50}} = \Delta N_{p, n, t - 1}^{c\text{ P50}} + \Delta D_{N^c}^\text{gtr P50} - \left(N_{p, s, t}^c - N_{p, s, t - 1}^c\right)$$

```python
import esdc

prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['mid'][-2] + esdc.discrepancy['con']['mid']['gtr'][-1] - prod

return esdc.resources['con']['mid'][-1] == new_resources
```

### RE2019 - Associated Gas Reserves: Current 2P must be consistent with previous 2P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P50}} = \Delta G_{p, n, t - 1}^{a\text{ P50}} + \Delta D_{G^a}^\text{gtr P50} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['mid'][-2] + esdc.discrepancy['ga']['mid']['gtr'][-1] - prod

return esdc.resources['ga']['mid'][-1] == new_resources
```

### RE2020 - Non Associated Gas Reserves: Current 2P must be consistent with previous 2P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{\text{P50}} = \Delta G_{p, n, t - 1}^{\text{P50}} + \Delta D_{G}^\text{gtr P50} - \left(G_{p, s, t} - G_{p, s, t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['gn']['sls'][-1] - esdc.cumprod['gn']['sls'][-2]
new_resources = esdc.resources['gn']['mid'][-2] + esdc.discrepancy['gn']['mid']['gtr'][-1] - prod

return esdc.resources['gn']['mid'][-1] == new_resources
```

### RE2021 - Oil Reserves: Current 3P must be consistent with previous 3P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{\text{P10}} = \Delta N_{p, n, t - 1}^{\text{P10}} + \Delta D_{N}^\text{gtr P10} - \left(N_{p, s, t} - N_{p, s, t - 1}\right)$$

```python
import esdc

prod = esdc.cumprod['oil']['sls'][-1] - esdc.cumprod['oil']['sls'][-2]
new_resources = esdc.resources['oil']['hgh'][-2] + esdc.discrepancy['oil']['hgh']['gtr'][-1] - prod

return esdc.resources['oil']['hgh'][-1] == new_resources
```

### RE2022 - Condensate Reserves: Current 3P must be consistent with previous 3P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta N_{p, n, t}^{c\text{ P50}} = \Delta N_{p, n, t - 1}^{c\text{ P50}} + \Delta D_{N^c}^\text{gtr P50} - \left(N_{p, s, t}^c - N_{p, s, t - 1}^c\right)$$

```python
import esdc

prod = esdc.cumprod['con']['sls'][-1] - esdc.cumprod['con']['sls'][-2]
new_resources = esdc.resources['con']['hgh'][-2] + esdc.discrepancy['con']['hgh']['gtr'][-1] - prod

return esdc.resources['con']['hgh'][-1] == new_resources
```

### RE2023 - Associated Gas Reserves: Current 3P must be consistent with previous 3P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P10}} = \Delta G_{p, n, t - 1}^{a\text{ P10}} + \Delta D_{G^a}^\text{gtr P10} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['hgh'][-2] + esdc.discrepancy['ga']['hgh']['gtr'][-1] - prod

return esdc.resources['ga']['hgh'][-1] == new_resources
```

### RE2024 - Non Associated Gas Reserves: Current 3P must be consistent with previous 3P, all discprepancies, and production

Severity: `strict`

The following equation must be true:

$$\Delta G_{p, n, t}^{a\text{ P10}} = \Delta G_{p, n, t - 1}^{a\text{ P10}} + \Delta D_{G^a}^\text{gtr P10} - \left(G_{p, s, t}^a - G_{p, s, t - 1}^a\right)$$

```python
import esdc

prod = esdc.cumprod['ga']['sls'][-1] - esdc.cumprod['ga']['sls'][-2]
new_resources = esdc.resources['ga']['hgh'][-2] + esdc.discrepancy['ga']['hgh']['gtr'][-1] - prod

return esdc.resources['ga']['hgh'][-1] == new_resources
```

### RE2025 - IOIP Mid: IOIP Mid must be higher than Sum of all projects Oil Ultimate GRR/CR/PR 3R/3C/3U if Sum of all projects Oil Ultimate GRR/CR/PR 3R/3C/3U higher than 0

Severity: `strict`

$$\sum_{i=1}^n \left(\Delta N_{p, n, i}^{\text{P10}} + N_{p, s, i}\right) > 0  \implies N^{\text{P50}} > \sum_{i=1}^n \left(\Delta N_{p, n, i}^{\text{P10}} + N_{p, s, i}\right)$$

```python
import esdc

eur_P10 = esdc.resources['oil']['hgh'][-1].groupby('field').sum() + esdc.cumprod['oil']['sls'][-1]
return esdc.inplace['oil']['mid'][-1] > eur_P10 if eur_P10 > 0
```

### RE2026 - IGIP Mid: IGIP Mid must be higher than Sum of all projects Non Associated Gas Ultimate 3R/3C/3U if Sum of all projects Non Associated Gas Ultimate 3R/3C/3U higher than 0

Severity: `strict`

$$ \sum_{i=1}^n \left(\Delta G_{p, n, i}^{\text{P10}} + G_{p, s, i}\right) > 0 \implies G^{\text{P50}} > \sum_{i=1}^n \left(\Delta G_{p, n, i}^{\text{P10}} + G_{p, s, i}\right)$$

```python
import esdc

eur_P10 = esdc.resources['gn']['hgh'][-1].groupby('field').sum() + esdc.cumprod['gn']['sls'][-1]
return esdc.inplace['gn']['mid'][-1] > eur_P10 if eur_P10 > 0
```

### RE2027 - IGIP Low: IGIP Low Case must be higher than 0 if Sum of all projects Condensate GRR/CR/PR 3R/3C/3U higher than 0

$$\sum_{i=1}^n \left( \Delta N_{p, n, i}^{c\text{ P10}} + N_{p, s, i}^c \right) > 0 \implies G^{\text{P50}} > 0$$

```python
import esdc

return esdc.inplace['gn']['low'][-1] > 0 if esdc.resources['con']['hgh'][-1].groupby('field').sum() > 0
```

### RE2028 - IOIP Low: IOIP Low Case must be higher than 0 if Sum of all projects Associated Gas GRR/CR/PR 3R/3C/3U higher than 0

$$\sum_{i=1}^n \left( \Delta G_{p, n, i}^{a\text{ P10}} + G_{p, s, i}^a \right) > 0 \implies N^{\text{P50}} > 0$$

```python
import esdc

return esdc.inplace['oil']['low'][-1] > 0 if esdc.resources['gn']['hgh'][-1].groupby('field').sum() > 0
```
