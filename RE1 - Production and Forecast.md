# RE1 - Production and Forecast

## List of Rules

### RE1001 - Oil Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg} \geq 0$$

```python
import esdc

return esdc.cumprod['oil']['grs'][-1] >= 0
```

### RE1002 - Condensate Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg}^c \geq 0$$

```python
import esdc

return esdc.cumprod['con']['grs'][-1] >= 0
```

### RE1003 - Associated Gas Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg}^a \geq 0$$

```python
import esdc

return esdc.cumprod['ga']['grs'][-1] >= 0
```

### RE1004 - Non Associated Gas Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg} \geq 0$$

```python
import esdc

return esdc.cumprod['gn']['grs'][-1] >= 0
```

### RE1005 - Oil Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn} \geq 0$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] >= 0
```

### RE1006 - Condensate Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn}^c \geq 0$$

```python
import esdc

return esdc.cumprod['con']['net'][-1] >= 0
```

### RE1007 - Associated Gas Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn}^a \geq 0$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] >= 0
```

### RE1008 - Non Associated Gas Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn} \geq 0$$

```python
import esdc

return esdc.cumprod['gn']['net'][-1] >= 0
```

### RE1009 - Oil Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps} \geq 0$$

```python
import esdc

return esdc.cumprod['oil']['sls'][-1] >= 0
```

### RE1010 - Condensate Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps}^c \geq 0$$

```python
import esdc

return esdc.cumprod['con']['sls'][-1] >= 0
```

### RE1011 - Associated Gas Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps}^a \geq 0$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] >= 0
```

### RE1012 - Non Associated Gas Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps} \geq 0$$

```python
import esdc

return esdc.cumprod['gn']['net'][-1] >= 0
```

### RE1013 - Oil Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg, t} \geq N_{pg, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['grs'][-1] >= esdc.cumprod['oil']['grs'][-2]
```

### RE1014 - Condensate Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg, t}^c \geq N_{pg, t - 1}^c$$

```python
import esdc

return esdc.cumprod['con']['grs'][-1] >= esdc.cumprod['con']['grs'][-2]
```

### RE1015 - Associated Gas Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg, t}^a \geq G_{pg, t - 1}^a$$

```python
import esdc

return esdc.cumprod['ga']['grs'][-1] >= esdc.cumprod['ga']['grs'][-2]
```

### RE1016 - Non Associated Gas Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg, t} \geq G_{pg, t - 1}$$

```python
import esdc

return esdc.cumprod['gn']['grs'][-1] >= esdc.cumprod['gn']['grs'][-2]
```

### RE1017 - Oil Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn, t} \geq N_{pn, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] >= esdc.cumprod['oil']['net'][-2]
```

### RE1018 - Condensate Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn, t}^c \geq N_{pn, t - 1}^c$$

```python
import esdc

return esdc.cumprod['con']['net'][-1] >= esdc.cumprod['con']['net'][-2]
```

### RE1019 - Associated Gas Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn, t}^a \geq G_{pn, t - 1}^a$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] >= esdc.cumprod['ga']['net'][-2]
```

### RE1020 - Non Associated Gas Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn, t} \geq G_{pn, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] >= esdc.cumprod['oil']['net'][-2]
```

### RE1021 - Oil Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps, t} \geq N_{ps, t - 1}$$

```python
import esdc

return esdc.cumprod['oil']['sls'][-1] >= esdc.cumprod['oil']['sls'][-2]
```

### RE1022 - Condensate Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps, t}^c \geq N_{ps, t - 1}^c$$

```python
import esdc

return esdc.cumprod['con']['sls'][-1] >= esdc.cumprod['con']['sls'][-2]
```

### RE1023 - Associated Gas Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps, t}^a \geq G_{ps, t - 1}^a$$

```python
import esdc

return esdc.cumprod['ga']['sls'][-1] >= esdc.cumprod['ga']['sls'][-2]
```

### RE1024 - Non Associated Gas Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps, t} \geq G_{ps, t - 1}$$

```python
import esdc

return esdc.cumprod['gn']['sls'][-1] >= esdc.cumprod['gn']['sls'][-2]
```

### RE1025 - Oil Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn} \leq N_{pg}$$

```python
import esdc

return esdc.cumprod['oil']['net'][-1] <= esdc.cumprod['oil']['grs'][-1]
```

### RE1026 - Condensate Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn}^c \leq N_{pg}^c$$

```python
import esdc

return esdc.cumprod['con']['net'][-1] <= esdc.cumprod['con']['grs'][-1]
```

### RE1027 - Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn}^a \leq G_{pg}^a$$

```python
import esdc

return esdc.cumprod['ga']['net'][-1] <= esdc.cumprod['ga']['grs'][-1]
```

### RE1028 - Non Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn} \leq G_{pg}$$

```python
import esdc

return esdc.cumprod['gn']['net'][-1] <= esdc.cumprod['gn']['grs'][-1]
```

### RE1029 - Oil Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps} \leq N_{ps}$$

```python
import esdc

return esdc.cumprod['oil']['sls'][-1] <= esdc.cumprod['oil']['grs'][-1]
```

### RE1030 - Condensate Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps}^c \leq N_{pg}^c$$

```python
import esdc

return esdc.cumprod['con']['sls'][-1] <= esdc.cumprod['con']['grs'][-1]
```

### RE1031 - Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps}^a \leq G_{pg}^a$$

```python
import esdc

return esdc.cumprod['ga']['sls'][-1] <= esdc.cumprod['ga']['grs'][-1]
```

### RE1032 - Non Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps} \leq G_{pg}$$

```python
import esdc

return esdc.cumprod['gn']['sls'][-1] <= esdc.cumprod['gn']['grs'][-1]
```

### RE1033 - Oil Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$q_{o, t\dots t_m}^{s} \leq q_{o, t\dots t_m}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['oil']['sls'][-1] <= esdc.forecast['oil']['tp'][:][-1]
```

### RE1034 - Condensate Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$q_{c, t\dots t_m}^{s} \leq q_{c, t\dots t_m}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['con']['sls'][-1] <= esdc.forecast['con']['tp'][:][-1]
```

### RE1035 - Associated Gas Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$q_{a, t\dots t_m}^{s} \leq q_{a, t\dots t_m}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['ga']['sls'][-1] <= esdc.forecast['ga']['tp'][:][-1]
```

### RE1036 - Non Associated Gas Sales Forecast: Yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$q_{n, t}^{s} \leq q_{n, t}^{\text{tp}}$$

```python
import esdc

return esdc.forecast['gn']['sls'][-1] <= esdc.forecast['gn']['tp'][:][-1]
```

### RE1037 - Oil Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{o, t}^{s} = \Delta N_{p, s}^{\text{2P}}$$

```python
import esdc

return esdc.forecast['oil']['sls'][-1].groupby('project') == esdc.reserves['oil']['mid'][-1]
```

### RE1038 - Condensate Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{c, t}^{s} = \Delta N_{p, s}^{c\text{ 2P}}$$

```python
import esdc

return esdc.forecast['con']['sls'][-1].groupby('project') == esdc.reserves['con']['mid'][-1]
```

### RE1039 - Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{a, t}^{s} = \Delta G_{p, s}^{a \text{ 2P}}$$

```python
import esdc

return esdc.forecast['ga']['sls'][-1].groupby('project') == esdc.reserves['ga']['mid'][-1]
```

### RE1040 - Non Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{n, t}^{s} = \Delta G_{p, s}^{\text{2P}}$$

```python
import esdc

return esdc.forecast['gn']['sls'][-1].groupby('project') == esdc.reserves['gn']['mid'][-1]
```

### RE1041 - Oil Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{o, t}^{\text{tp}} = \Delta N_{p, n}^{\text{P50}}$$

```python
import esdc

return esdc.forecast['oil']['tp'][-1].groupby('project').sum() == esdc.resources['oil']['mid'][-1]
```

### RE1042 - Condensate Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{c, t}^{\text{tp}} = \Delta N_{p, n}^{c\text{ P50}}$$

```python
import esdc

return esdc.forecast['con']['tp'][-1].groupby('project').sum() == esdc.resources['con']['mid'][-1]
```

### RE1043 - Associated  Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{a, t}^{\text{tp}} = \Delta G_{p, n}^{a\text{ P50}}$$

```python
import esdc

return esdc.forecast['ga']['tp'][-1].groupby('project').sum() == esdc.resources['ga']['mid'][-1]
```

### RE1044 - Non Associated Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t}^m q_{a, t}^{\text{tp}} = \Delta G_{p, n}^{\text{P50}}$$

```python
import esdc

return esdc.forecast['gn']['tp'][-1].groupby('project').sum() == esdc.resources['gn']['mid'][-1]
```

### RE1045 - Sum of Oil + Condensate Sales Forecast per year: sum of Oil + Condensate Sales Forecast per year should equal to reported WP&B Forecast per year

Severity: `warning` :warning:

The following equation must be true:

$$q_{oc, t \dots t_m}^{\text{wpnb}} = \left. q_{o, t \dots t_n}^{s} \right \vert_{\sum \text{Working Area}} + \left. q_{c, t \dots t_n}^{s} \right \vert_{\sum \text{Working Area}}$$

```python
import esdc

```

### RE1046 - Sum of Associated Gas + Non Associated Gas Sales Forecast per year: sum of Associated Gas + Non Associated Gas Sales Forecast per year should equal to reported WP&B Forecast per year

Severity: `warning` :warning:

The following equation must be true:

$$q_{an, t \dots t_m}^{\text{wpnb}} = \left. q_{a, t \dots t_m}^{s} \right \vert_{\sum \text{Working Area}} + \left. q_{c, t \dots t_m}^{s} \right \vert_{\sum \text{Working Area}}$$

```python
import esdc

```
