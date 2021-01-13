# eSDC References

## Symbol Reference

The following symbol is used in this documentation. We use P90/P50/P10 as a generic symbol instead of using specific symbols such as R (GRR), C (Contingent), U (Prospective) for generic rules that apply equally to GRR, Contingent Resources, and Prospective Resources. In case of reserves, 1P/2P/3P is used.

| Symbols | Definition |
| --- | --- |
| $N^{\text{P90/P50/P10}}$ | Initial Oil in Place |
| $G^{\text{P90/P50/P10}}$ | Initial Gas in Place |
| $N_{pg}$ | Oil Gross Cumulative Production |
| $N_{pg}^c$ | Condensate Gross Cumulative Production |
| $G_{pg}$ | Non Associated Gas Gross Cumulative Production|
| $G_{pg}^a$ | Associated Gas Net Cumulative Production |
| $N_{pn}$ | Oil Net Cumulative Production |
| $N_{pn}^c$ | Condensate Net Cumulative Production |
| $G_{pn}$ | Non Associated Gas Net Cumulative Production|
| $G_{pn}^a$ | Associated Gas Net Cumulative Production |
| $N_{ps}$ | Oil Sales Cumulative Production |
| $N_{ps}^c$ | Condensate Sales Cumulative Production |
| $G_{ps}$ | Non Associated Gas Sales Cumulative Production|
| $G_{ps}^a$ | Associated Gas Sales Cumulative Production |
| $\Delta N_{pn}^{\text{P90/P50/P10}}$| Oil GRR/CR/PR |
| $\Delta N_{pn}^{c \text{ P90/P50/P10}}$ | Condensate GRR/CR/PR |
| $\Delta G_{pn}^{\text{P90/P50/P10}}$ | Non Associated Gas GRR/CR/PR |
| $\Delta G_{pn}^{a \text{ P90/P50/P10}}$ | Associated Gas GRR/CR/PR |
| $\Delta N_{ps}^{\text{1P/2P/3P}}$| Oil Reserves |
| $\Delta N_{ps}^{c \text{ 1P/2P/3P}}$ | Condensate Reserves |
| $\Delta G_{ps}^{\text{1P/2P/3P}}$ | Non Associated Gas Reserves |
| $\Delta G_{ps}^{a \text{ 1P/2P/3P}}$ | Associated Gas Reserves |
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
| $\Delta D_{G^a}^\text{gtr P90/P50/P10}$ | Associated Gas Discrepancy from Well Intervention |
| $\Delta D_{N}^\text{gtr P90/P50/P10}$ | Oil Discrepancy from Commerciality |
| $\Delta D_{N^c}^\text{gtr P90/P50/P10}$ | Condensate Discrepancy from Commerciality |
| $\Delta D_{G}^\text{gtr P90/P50/P10}$ | Non Associated Gas Discrepancy from Commerciality |
| $\Delta D_{G^a}^\text{gtr P90/P50/P10}$ | Associated Gas Discrepancy from Commerciality |
| $\Delta D_{N}^\text{cio P90/P50/P10}$ | Oil Discrepancy from Consumed in Operations |
| $\Delta D_{N^c}^\text{cio P90/P50/P10}$ | Condensate Discrepancy from Consumed in Operations |
| $\Delta D_{G}^\text{cio P90/P50/P10}$ | Non Associated Gas Discrepancy from Consumed in Operations |
| $\Delta D_{G^a}^\text{cioConsumed in Operations P90/P50/P10}$ | Associated Gas Discrepancy from Consumed in Operations |
| $q_{o, t \dots t_m}^{s}$ | Oil Sales yearly rate forecast|
| $q_{c, t \dots t_m}^{s}$ | Condensate Sales yearly rate forecast|
| $q_{a, t \dots t_m}^{s}$ | Associated Gas Sales yearly rate forecast|
| $q_{n, t \dots t_m}^{s}$ | Non Associated Gas Sales yearly rate forecast|
| $q_{o, t \dots t_m}^{\text{tp}}$ | Oil Total Potential yearly rate forecast|
| $q_{c, t \dots t_m}^{\text{tp}}$ | Condensate Total Potential yearly rate forecast|
| $q_{a, t \dots t_m}^{\text{tp}}$ | Associated Gas Total Potential yearly rate forecast|
| $q_{n, t \dots t_m}^{\text{tp}}$ | Non Associated Gas Total Potential yearly rate forecast|
| $q_{oc, t \dots t_m}^{\text{wpnb}}$ | Oil + Condensate yearly rate forecast reported in WP&B|
| $q_{an, t \dots t_m}^{\text{wpnb}}$ | Associated + Non Associated Gas yearly rate forecast reported in WP&B |

## Keyword Reference

| Keyword | Filter | Aggregation | Agg Type | Description |
| --------- | --- | --- | --- | --- |
| `inplace` | fluid type, uncertainty, time reference | zone, field, working area | `sum` | Initial in Place |
| `cumprod` | fluid type, commerciality, time reference | project, field, working area | `sum` | Cumulative Production |
| `resources` | fluid type, uncertainty, time reference | project, field, working area | `sum` | GRR, Contingent Resources, Prospective Resources |
| `reserves` | fluid type, uncertainty, time reference | project, field, working area | `sum` | Reserves |
| `forecast` | fluid type, commerciality, time reference | project, field, working area | `sum` | Production Forecast |
| `forecast_wpnb` | - | working area | `sum` | reported WP&B production forecast |
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

## Syntax reference
| Keyword | Group Type | Description |
| ------- | ---------- | --- |
| `oil`   | fluid_type | Oil         |
| `con`   | fluid_type | Condensate  |
| `ga`    | fluid_type | Associated Gas |
| `gn`    | fluid_type | Non Associated Gas |
| `grs`   | commerciality | Gross |
| `sls`   | commerciality | Sales |
| `um`    | discrepancy | Update Model |
| `ppa`   | discrepancy | Production Performance Analysis |
| `wi`    | discrepancy | Well Intervention |
| `gtr`   | discrepancy | GRR to Reserves |
| `cio`   | discrepancy | Consumed in Operations |

## Syntax for eSDC Rules

eSDC module API:

```python
import esdc

esdc.inplace[fluid_type][uncert_level][time_ref]
esdc.cumprod[fluid_type][commerciality][time_ref].groupby('') # group by field, working area
esdc.resources[fluid_type][uncert_level][time_ref].groupby('') # group by field, working area
esdc.forecast[fluid_type][commerciality][time_ref][forecast_time].groupby('') # group by field, working area
esdc.forecast_wpnb[time_ref][forecast_time]
esdc.discrepancy[fluid_type]
```

## Rules Definition

| Rules Code | Description             |
| ---------- | ----------------------- |
| RE0        | Volumetric              |
| RE1        | Production and forecast |
| RE2        | Material Balance        |
| RE3        | Reservoir Properties    |
| RE4        | Analytics               |