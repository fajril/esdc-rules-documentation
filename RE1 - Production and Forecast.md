# RE1 - Production and Forecast

## List of Rules

### RE1001 - Oil Gross Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg} \geq 0$$

The following example should pass:

``` al
if
    Oil Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Gross Cumulative Production = -1
then
    validation result is False
```

### RE1002 - Condensate Gross Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg}^c \geq 0$$

The following example should pass:

``` al
if
    Condensate Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Gross Cumulative Production = -1
then
    validation result is False
```

### RE1003 - Associated Gas Gross Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg}^a \geq 0$$

The following example should pass:

``` al
if
    Associated Gas Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Gross Cumulative Production = -1
then
    validation result is False
```

### RE1004 - Non Associated Gas Gross Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg} \geq 0$$

The following example should pass:

``` al
if
    Non Associated Gas Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Gross Cumulative Production = -1
then
    validation result is False
```

### RE1005 - Oil Net Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn} \geq 0$$

The following example should pass:

``` al
if
    Oil Net Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Net Cumulative Production = -1
then
    validation result is False
```

### RE1006 - Condensate Net Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn}^c \geq 0$$

The following example should pass:

``` al
if
    Condensate Net Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Net Cumulative Production = -1
then
    validation result is False
```

### RE1007 - Associated Gas Net Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn}^a \geq 0$$

The following example should pass:

``` al
if
    Associated Gas Net Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Net Cumulative Production = -1
then
    validation result is False
```

### RE1008 - Non Associated Gas Net Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn} \geq 0$$

The following example should pass:

``` al
if
    Non Associated Gas Net Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Net Cumulative Production = -1
then
    validation result is False
```

### RE1009 - Oil Sales Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps} \geq 0$$

The following example should pass:

``` al
if
    Oil Sales Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Sales Cumulative Production = -1
then
    validation result is False
```

### RE1010 - Condensate Sales Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps}^c \geq 0$$

The following example should pass:

``` al
if
    Condensate Sales Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Sales Cumulative Production = -1
then
    validation result is False
```

### RE1011 - Associated Gas Sales Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps}^a \geq 0$$

The following example should pass:

``` al
if
    Associated Gas Sales Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Sales Cumulative Production = -1
then
    validation result is False
```

### RE1012 - Non Associated Gas Sales Cumprod: Must be greater than or equal to zero

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps} \geq 0$$

The following example should pass:

``` al
if
    Non Associated Gas Sales Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Sales Cumulative Production = -1
then
    validation result is False
```

### RE1013 - Oil Gross Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg, t} \geq N_{pg, t - 1}$$

The following example should pass:

``` al
if
    Oil Gross Cumulative Production Current = 1500
    Oil Gross Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Gross Cumulative Production Current = 800
    Oil Gross Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1014 - Condensate Gross Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg, t}^c \geq N_{pg, t - 1}^c$$

The following example should pass:

``` al
if
    Condensate Gross Cumulative Production Current = 1500
    Condensate Gross Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Gross Cumulative Production Current = 800
    Condensate Gross Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1015 - Associated Gas Gross Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg, t}^a \geq G_{pg, t - 1}^a$$

The following example should pass:

``` al
if
    Associated Gas Gross Cumulative Production Current = 1500
    Associated Gas Gross Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Gross Cumulative Production Current = 800
    Associated Gas Gross Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1016 - Non Associated Gas Gross Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg, t} \geq G_{pg, t - 1}$$

The following example should pass:

``` al
if
    Non Associated Gas Gross Cumulative Production Current = 1500
    Non Associated Gas Gross Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Gross Cumulative Production Current = 800
    Non Associated Gas Gross Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1017 - Oil Net Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$N_{pn, t} \geq N_{pn, t - 1}$$

### RE1018 - Condensate Net Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$N_{pn, t}^c \geq N_{pn, t - 1}^c$$

### RE1019 - Associated Gas Net Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$G_{pn, t}^a \geq G_{pn, t - 1}^a$$

### RE1020 - Non Associated Gas Net Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$G_{pn, t} \geq G_{pn, t - 1}$$

### RE1021 - Oil Sales Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps, t} \geq N_{ps, t - 1}$$

The following example should pass:

``` al
if
    Oil Sales Cumulative Production Current = 1500
    Oil Sales Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Sales Cumulative Production Current = 800
    Oil Sales Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1022 - Condensate Sales Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps, t}^c \geq N_{ps, t - 1}^c$$

The following example should pass:

``` al
if
    Condensate Sales Cumulative Production Current = 1500
    Condensate Sales Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Sales Cumulative Production Current = 800
    Condensate Sales Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1023 - Associated Gas Sales Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps, t}^a \geq G_{ps, t - 1}^a$$

The following example should pass:

``` al
if
    Associated Gas Sales Cumulative Production Current = 1500
    Associated Gas Sales Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Sales Cumulative Production Current = 800
    Associated Gas Sales Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1024 - Non Associated Gas Sales Cumprod: Must be greater than or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps, t} \geq G_{ps, t - 1}$$

The following example should pass:

``` al
if
    Non Associated Gas Sales Cumulative Production Current = 1500
    Non Associated Gas Sales Cumulative Production Previous = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Sales Cumulative Production Current = 800
    Non Associated Gas Sales Cumulative Production Previous = 1000
then
    validation result is False
```

### RE1025 - Oil Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn} \leq N_{pg}$$

The following example should pass:

``` al
if
    Oil Net Cumulative Production = 800
    Oil Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Net Cumulative Production = 1200
    Oil Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1026 - Condensate Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn}^c \leq N_{pg}^c$$

The following example should pass:

``` al
if
    Condensate Net Cumulative Production = 800
    Condensate Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Net Cumulative Production = 1200
    Condensate Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1027 - Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn}^a \leq G_{pg}^a$$

The following example should pass:

``` al
if
    Associated Gas Net Cumulative Production = 800
    Associated Gas Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Net Cumulative Production = 1200
    Associated Gas Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1028 - Non Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn} \leq G_{pg}$$

The following example should pass:

``` al
if
    Non Associated Gas Net Cumulative Production = 800
    Non Associated Gas Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Net Cumulative Production = 1200
    Non Associated Gas Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1029 - Oil Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps} \leq N_{pg}$$

The following example should pass:

``` al
if
    Oil Sales Cumulative Production = 800
    Oil Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Sales Cumulative Production = 1200
    Oil Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1030 - Condensate Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps}^c \leq N_{pg}^c$$

The following example should pass:

``` al
if
    Condensate Sales Cumulative Production = 800
    Condensate Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Sales Cumulative Production = 1200
    Condensate Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1031 - Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps}^a \leq G_{pg}^a$$

The following example should pass:

``` al
if
    Associated Gas Sales Cumulative Production = 800
    Associated Gas Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Sales Cumulative Production = 1200
    Associated Gas Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1032 - Non Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps} \leq G_{pg}$$

The following example should pass:

``` al
if
    Non Associated Gas Sales Cumulative Production = 800
    Non Associated Gas Gross Cumulative Production = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Sales Cumulative Production = 1200
    Non Associated Gas Gross Cumulative Production = 1000
then
    validation result is False
```

### RE1033 - Oil Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$ \forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{o, t}^{s} \leq q_{o, t}^{\text{tp}}$$

The following example should pass:

``` al
if
    Oil Sales Forecast 2025 = 500
    Oil Total Potential Forecast 2025 = 600
    Oil Sales Forecast 2026 = 700
    Oil Total Potential Forecast 2026 = 800
    Oil Sales Forecast 2027 = 900
    Oil Total Potential Forecast 2027 = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Sales Forecast 2025 = 500
    Oil Total Potential Forecast 2025 = 400
    Oil Sales Forecast 2026 = 700
    Oil Total Potential Forecast 2026 = 800
    Oil Sales Forecast 2027 = 900
    Oil Total Potential Forecast 2027 = 1000
then
    validation result is False
```

### RE1034 - Condensate Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{c, t}^{s} \leq q_{c, t}^{\text{tp}}$$

The following example should pass:

``` al
if
    Condensate Sales Forecast 2025 = 500
    Condensate Total Potential Forecast 2025 = 600
    Condensate Sales Forecast 2026 = 700
    Condensate Total Potential Forecast 2026 = 800
    Condensate Sales Forecast 2027 = 900
    Condensate Total Potential Forecast 2027 = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Sales Forecast 2025 = 500
    Condensate Total Potential Forecast 2025 = 400
    Condensate Sales Forecast 2026 = 700
    Condensate Total Potential Forecast 2026 = 800
    Condensate Sales Forecast 2027 = 900
    Condensate Total Potential Forecast 2027 = 1000
then
    validation result is False
```

### RE1035 - Associated Gas Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{a, t}^{s} \leq q_{a, t}^{\text{tp}}$$

The following example should pass:

``` al
if
    Associated Gas Sales Forecast 2025 = 500
    Associated Gas Total Potential Forecast 2025 = 600
    Associated Gas Sales Forecast 2026 = 700
    Associated Gas Total Potential Forecast 2026 = 800
    Associated Gas Sales Forecast 2027 = 900
    Associated Gas Total Potential Forecast 2027 = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Sales Forecast 2025 = 500
    Associated Gas Total Potential Forecast 2025 = 400
    Associated Gas Sales Forecast 2026 = 700
    Associated Gas Total Potential Forecast 2026 = 800
    Associated Gas Sales Forecast 2027 = 900
    Associated Gas Total Potential Forecast 2027 = 1000
then
    validation result is False
```

### RE1036 - Non Associated Gas Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{n, t}^{s} \leq q_{n, t}^{\text{tp}}$$

The following example should pass:

``` al
if
    Non Associated Gas Sales Forecast 2025 = 500
    Non Associated Gas Total Potential Forecast 2025 = 600
    Non Associated Gas Sales Forecast 2026 = 700
    Non Associated Gas Total Potential Forecast 2026 = 800
    Non Associated Gas Sales Forecast 2027 = 900
    Non Associated Gas Total Potential Forecast 2027 = 1000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Sales Forecast 2025 = 500
    Non Associated Gas Total Potential Forecast 2025 = 400
    Non Associated Gas Sales Forecast 2026 = 700
    Non Associated Gas Total Potential Forecast 2026 = 800
    Non Associated Gas Sales Forecast 2027 = 900
    Non Associated Gas Total Potential Forecast 2027 = 1000
then
    validation result is False
```

### RE1037 - Oil Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{o, t}^{s} = \Delta N_{ps}^{\text{2P}}$$

The following example should pass:

``` al
if
    Oil Sales Forecast 2025 = 500
    Oil Sales Forecast 2026 = 700
    Oil Sales Forecast 2027 = 800
    Oil Reserves 2P = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Sales Forecast 2025 = 500
    Oil Sales Forecast 2026 = 700
    Oil Sales Forecast 2027 = 800
    Oil Reserves 2P = 1500
then
    validation result is False
```

### RE1038 - Condensate Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{c, t}^{s} = \Delta N_{ps}^{c \text{2P}}$$

The following example should pass:

``` al
if
    Condensate Sales Forecast 2025 = 500
    Condensate Sales Forecast 2026 = 700
    Condensate Sales Forecast 2027 = 800
    Condensate Reserves 2P = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Sales Forecast 2025 = 500
    Condensate Sales Forecast 2026 = 700
    Condensate Sales Forecast 2027 = 800
    Condensate Reserves 2P = 1500
then
    validation result is False
```

### RE1039 - Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{a, t}^{s} = \Delta G_{ps}^{a \text{2P}}$$

The following example should pass:

``` al
if
    Associated Gas Sales Forecast 2025 = 500
    Associated Gas Sales Forecast 2026 = 700
    Associated Gas Sales Forecast 2027 = 800
    Associated Gas Reserves 2P = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Sales Forecast 2025 = 500
    Associated Gas Sales Forecast 2026 = 700
    Associated Gas Sales Forecast 2027 = 800
    Associated Gas Reserves 2P = 1500
then
    validation result is False
```

### RE1040 - Non Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{n, t}^{s} = \Delta G_{ps}^{\text{2P}}$$

The following example should pass:

``` al
if
    Non Associated Gas Sales Forecast 2025 = 500
    Non Associated Gas Sales Forecast 2026 = 700
    Non Associated Gas Sales Forecast 2027 = 800
    Non Associated Gas Reserves 2P = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Sales Forecast 2025 = 500
    Non Associated Gas Sales Forecast 2026 = 700
    Non Associated Gas Sales Forecast 2027 = 800
    Non Associated Gas Reserves 2P = 1500
then
    validation result is False
```

### RE1041 - Oil Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{o, t}^{\text{tp}} = \Delta N_{pn}^{\text{P50}}$$

The following example should pass:

``` al
if
    Oil Total Potential Forecast 2025 = 500
    Oil Total Potential Forecast 2026 = 700
    Oil Total Potential Forecast 2027 = 800
    Oil GRR/CR/PR P50 = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Total Potential Forecast 2025 = 500
    Oil Total Potential Forecast 2026 = 700
    Oil Total Potential Forecast 2027 = 800
    Oil GRR/CR/PR P50 = 1500
then
    validation result is False
```

### RE1042 - Condensate Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{c, t}^{\text{tp}} = \Delta N_{pn}^{c \text{P50}}$$

The following example should pass:

``` al
if
    Condensate Total Potential Forecast 2025 = 500
    Condensate Total Potential Forecast 2026 = 700
    Condensate Total Potential Forecast 2027 = 800
    Condensate GRR/CR/PR P50 = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Total Potential Forecast 2025 = 500
    Condensate Total Potential Forecast 2026 = 700
    Condensate Total Potential Forecast 2027 = 800
    Condensate GRR/CR/PR P50 = 1500
then
    validation result is False
```

### RE1043 - Associated Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{a, t}^{\text{tp}} = \Delta G_{pn}^{a \text{P50}}$$

The following example should pass:

``` al
if
    Associated Gas Total Potential Forecast 2025 = 500
    Associated Gas Total Potential Forecast 2026 = 700
    Associated Gas Total Potential Forecast 2027 = 800
    Associated Gas GRR/CR/PR P50 = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Total Potential Forecast 2025 = 500
    Associated Gas Total Potential Forecast 2026 = 700
    Associated Gas Total Potential Forecast 2027 = 800
    Associated Gas GRR/CR/PR P50 = 1500
then
    validation result is False
```

### RE1044 - Non Associated Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{n, t}^{\text{tp}} = \Delta G_{pn}^{\text{P50}}$$

The following example should pass:

``` al
if
    Non Associated Gas Total Potential Forecast 2025 = 500
    Non Associated Gas Total Potential Forecast 2026 = 700
    Non Associated Gas Total Potential Forecast 2027 = 800
    Non Associated Gas GRR/CR/PR P50 = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Total Potential Forecast 2025 = 500
    Non Associated Gas Total Potential Forecast 2026 = 700
    Non Associated Gas Total Potential Forecast 2027 = 800
    Non Associated Gas GRR/CR/PR P50 = 1500
then
    validation result is False
```

### RE1045 - Sum of Oil + Condensate Sales Forecast per year: sum of Oil + Condensate Sales Forecast per year should be equal to reported WP&B Forecast per year

Severity: `warning` :warning:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{oc, t}^{\text{wpnb}} = \left. q_{o, t}^{s} \right \vert_{\sum \text{Working Area}} + \left. q_{c, t}^{s} \right \vert_{\sum \text{Working Area}}$$

The following example should pass:

``` al
if
    Oil + Condensate WP&B Forecast 2025 = 1200
    Oil Sales Forecast 2025 = 800
    Condensate Sales Forecast 2025 = 400
    Oil + Condensate WP&B Forecast 2026 = 1500
    Oil Sales Forecast 2026 = 1000
    Condensate Sales Forecast 2026 = 500
    Oil + Condensate WP&B Forecast 2027 = 1800
    Oil Sales Forecast 2027 = 1200
    Condensate Sales Forecast 2027 = 600
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil + Condensate WP&B Forecast 2025 = 1200
    Oil Sales Forecast 2025 = 800
    Condensate Sales Forecast 2025 = 500
    Oil + Condensate WP&B Forecast 2026 = 1500
    Oil Sales Forecast 2026 = 1000
    Condensate Sales Forecast 2026 = 500
    Oil + Condensate WP&B Forecast 2027 = 1800
    Oil Sales Forecast 2027 = 1200
    Condensate Sales Forecast 2027 = 600
then
    validation result is False
```

### RE1046 - Sum of Associated Gas + Non Associated Gas Sales Forecast per year: sum of Associated Gas + Non Associated Gas Sales Forecast per year should be equal to reported WP&B Forecast per year

Severity: `warning` :warning:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{an, t}^{\text{wpnb}} = \left. q_{a, t}^{s} \right \vert_{\sum \text{Working Area}} + \left. q_{n, t}^{s} \right \vert_{\sum \text{Working Area}}$$

The following example should pass:

``` al
if
    Associated + Non Associated Gas WP&B Forecast 2025 = 1200
    Associated Gas Sales Forecast 2025 = 800
    Non Associated Gas Sales Forecast 2025 = 400
    Associated + Non Associated Gas WP&B Forecast 2026 = 1500
    Associated Gas Sales Forecast 2026 = 1000
    Non Associated Gas Sales Forecast 2026 = 500
    Associated + Non Associated Gas WP&B Forecast 2027 = 1800
    Associated Gas Sales Forecast 2027 = 1200
    Non Associated Gas Sales Forecast 2027 = 600
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated + Non Associated Gas WP&B Forecast 2025 = 1200
    Associated Gas Sales Forecast 2025 = 800
    Non Associated Gas Sales Forecast 2025 = 500
    Associated + Non Associated Gas WP&B Forecast 2026 = 1500
    Associated Gas Sales Forecast 2026 = 1000
    Non Associated Gas Sales Forecast 2026 = 500
    Associated + Non Associated Gas WP&B Forecast 2027 = 1800
    Associated Gas Sales Forecast 2027 = 1200
    Non Associated Gas Sales Forecast 2027 = 600
then
    validation result is False
```

