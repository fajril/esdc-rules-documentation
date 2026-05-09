# RE1 - Production and Forecast

## List of Rules

### RE1001 - Oil Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg} \geq 0$$

### RE1002 - Condensate Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg}^c \geq 0$$

### RE1003 - Associated Gas Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg}^a \geq 0$$

### RE1004 - Non Associated Gas Gross Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg} \geq 0$$

### RE1005 - Oil Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn} \geq 0$$

### RE1006 - Condensate Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn}^c \geq 0$$

### RE1007 - Associated Gas Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn}^a \geq 0$$

### RE1008 - Non Associated Gas Net Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn} \geq 0$$

### RE1009 - Oil Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps} \geq 0$$

### RE1010 - Condensate Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps}^c \geq 0$$

### RE1011 - Associated Gas Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps}^a \geq 0$$

### RE1012 - Non Associated Gas Sales Cumprod: Must be positive or equal to 0

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps} \geq 0$$

### RE1013 - Oil Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg, t} \geq N_{pg, t - 1}$$

### RE1014 - Condensate Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pg, t}^c \geq N_{pg, t - 1}^c$$

### RE1015 - Associated Gas Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg, t}^a \geq G_{pg, t - 1}^a$$

### RE1016 - Non Associated Gas Gross Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pg, t} \geq G_{pg, t - 1}$$

### RE1017 - Oil Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$N_{pn, t} \geq N_{pn, t - 1}$$

### RE1018 - Condensate Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$N_{pn, t}^c \geq N_{pn, t - 1}^c$$

### RE1019 - Associated Gas Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$G_{pn, t}^a \geq G_{pn, t - 1}^a$$

### RE1020 - Non Associated Gas Net Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

Notes: _Not Implemented_

The following equation must be true:

$$G_{pn, t} \geq G_{pn, t - 1}$$

### RE1021 - Oil Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps, t} \geq N_{ps, t - 1}$$

### RE1022 - Condensate Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps, t}^c \geq N_{ps, t - 1}^c$$

### RE1023 - Associated Gas Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps, t}^a \geq G_{ps, t - 1}^a$$

### RE1024 - Non Associated Gas Sales Cumprod: Can only increase or equal to previous Cumprod

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps, t} \geq G_{ps, t - 1}$$

### RE1025 - Oil Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn} \leq N_{pg}$$

### RE1026 - Condensate Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{pn}^c \leq N_{pg}^c$$

### RE1027 - Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn}^a \leq G_{pg}^a$$

### RE1028 - Non Associated Gas Cumprod: Net Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{pn} \leq G_{pg}$$

### RE1029 - Oil Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps} \leq N_{pg}$$

### RE1030 - Condensate Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$N_{ps}^c \leq N_{pg}^c$$

### RE1031 - Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps}^a \leq G_{pg}^a$$

### RE1032 - Non Associated Gas Cumprod: Sales Volume must be less than or equal to Gross Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$G_{ps} \leq G_{pg}$$

### RE1033 - Oil Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$ \forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{o, t}^{s} \leq q_{o, t}^{\text{tp}}$$

### RE1034 - Condensate Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{c, t}^{s} \leq q_{c, t}^{\text{tp}}$$

### RE1035 - Associated Gas Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{a, t}^{s} \leq q_{a, t}^{\text{tp}}$$

### RE1036 - Non Associated Gas Sales Forecast: For each year, yearly Sales Volume must be less than or equal to Yearly Total Potential Volume

Severity: `strict` :no_entry:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{n, t}^{s} \leq q_{n, t}^{\text{tp}}$$

### RE1037 - Oil Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{o, t}^{s} = \Delta N_{ps}^{\text{2P}}$$

### RE1038 - Condensate Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{c, t}^{s} = \Delta N_{ps}^{c \text{2P}}$$

### RE1039 - Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{a, t}^{s} = \Delta G_{ps}^{a \text{2P}}$$

### RE1040 - Non Associated Gas Sales Forecast: Sum of Yearly Forecast must be equal to 2P Reserves

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{n, t}^{s} = \Delta G_{ps}^{\text{2P}}$$

### RE1041 - Oil Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{o, t}^{\text{tp}} = \Delta N_{pn}^{\text{P50}}$$

### RE1042 - Condensate Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{c, t}^{\text{tp}} = \Delta N_{pn}^{c \text{P50}}$$

### RE1043 - Associated Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{a, t}^{\text{tp}} = \Delta G_{pn}^{a \text{P50}}$$

### RE1044 - Non Associated Gas Total Potential Forecast: Sum of Yearly Forecast must be equal to 2R GRR/CR/PR

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{t=t_R + 1}^{t_m} q_{n, t}^{\text{tp}} = \Delta G_{pn}^{\text{P50}}$$

### RE1045 - Sum of Oil + Condensate Sales Forecast per year: sum of Oil + Condensate Sales Forecast per year should equal to reported WP&B Forecast per year

Severity: `warning` :warning:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{oc, t}^{\text{wpnb}} = \left. q_{o, t}^{s} \right \vert_{\sum \text{Working Area}} + \left. q_{c, t}^{s} \right \vert_{\sum \text{Working Area}}$$

### RE1046 - Sum of Associated Gas + Non Associated Gas Sales Forecast per year: sum of Associated Gas + Non Associated Gas Sales Forecast per year should equal to reported WP&B Forecast per year

Severity: `warning` :warning:

The following equation must be true:

$$\forall t \in \lbrace t_R + 1, \dots , t_m \rbrace \mid q_{an, t}^{\text{wpnb}} = \left. q_{a, t}^{s} \right \vert_{\sum \text{Working Area}} + \left. q_{n, t}^{s} \right \vert_{\sum \text{Working Area}}$$

