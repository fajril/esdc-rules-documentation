# RE2 - Material Balance

## List of Rules

### RE2001 - Oil GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P90}} = \Delta N_{pn,t - 1}^{\text{P90}} + \Delta D_{N}^\text{um P90} + \Delta D_{N}^\text{ppa P90} + \Delta D_{N}^\text{wi P90} + \Delta D_{N}^\text{uc P90} + \Delta D_{N}^\text{cio P90} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Oil GRR/CR/PR P90 Current = 1015
    Oil GRR/CR/PR P90 Previous = 1000
    Oil Discrepancy from Update Model P90 = 50
    Oil Discrepancy from Production Performance Analysis P90 = 30
    Oil Discrepancy from Well Intervention P90 = 20
    Oil Discrepancy from Unaccounted Changes P90 = 10
    Oil Discrepancy from Consumed in Operations P90 = 5
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR P90 Current = 900
    Oil GRR/CR/PR P90 Previous = 1000
    Oil Discrepancy from Update Model P90 = 50
    Oil Discrepancy from Production Performance Analysis P90 = 30
    Oil Discrepancy from Well Intervention P90 = 20
    Oil Discrepancy from Unaccounted Changes P90 = 10
    Oil Discrepancy from Consumed in Operations P90 = 5
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2002 - Condensate GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P90}} = \Delta N_{pn,t - 1}^{c \text{P90}} + \Delta D_{N^c}^\text{um P90} + \Delta D_{N^c}^\text{ppa P90} + \Delta D_{N^c}^\text{wi P90} + \Delta D_{N^c}^\text{uc P90} + \Delta D_{N^c}^\text{cio P90} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR P90 Current = 1015
    Condensate GRR/CR/PR P90 Previous = 1000
    Condensate Discrepancy from Update Model P90 = 50
    Condensate Discrepancy from Production Performance Analysis P90 = 30
    Condensate Discrepancy from Well Intervention P90 = 20
    Condensate Discrepancy from Unaccounted Changes P90 = 10
    Condensate Discrepancy from Consumed in Operations P90 = 5
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR P90 Current = 900
    Condensate GRR/CR/PR P90 Previous = 1000
    Condensate Discrepancy from Update Model P90 = 50
    Condensate Discrepancy from Production Performance Analysis P90 = 30
    Condensate Discrepancy from Well Intervention P90 = 20
    Condensate Discrepancy from Unaccounted Changes P90 = 10
    Condensate Discrepancy from Consumed in Operations P90 = 5
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2003 - Associated Gas GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P90}} = \Delta G_{pn,t - 1}^{a \text{P90}} + \Delta D_{G^a}^\text{um P90} + \Delta D_{G^a}^\text{ppa P90} + \Delta D_{G^a}^\text{wi P90} + \Delta D_{G^a}^\text{uc P90} + \Delta D_{G^a}^\text{cio P90} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR P90 Current = 1015
    Associated Gas GRR/CR/PR P90 Previous = 1000
    Associated Gas Discrepancy from Update Model P90 = 50
    Associated Gas Discrepancy from Production Performance Analysis P90 = 30
    Associated Gas Discrepancy from Well Intervention P90 = 20
    Associated Gas Discrepancy from Unaccounted Changes P90 = 10
    Associated Gas Discrepancy from Consumed in Operations P90 = 5
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR P90 Current = 900
    Associated Gas GRR/CR/PR P90 Previous = 1000
    Associated Gas Discrepancy from Update Model P90 = 50
    Associated Gas Discrepancy from Production Performance Analysis P90 = 30
    Associated Gas Discrepancy from Well Intervention P90 = 20
    Associated Gas Discrepancy from Unaccounted Changes P90 = 10
    Associated Gas Discrepancy from Consumed in Operations P90 = 5
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2004 - Non Associated Gas GRR/CR/PR: Current 1R/1C/1U must be consistent with previous 1R/1C/1U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P90}} = \Delta G_{pn,t - 1}^{\text{P90}} + \Delta D_{G}^\text{um P90} + \Delta D_{G}^\text{ppa P90} + \Delta D_{G}^\text{wi P90} + \Delta D_{G}^\text{uc P90} + \Delta D_{G}^\text{cio P90} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR P90 Current = 1015
    Non Associated Gas GRR/CR/PR P90 Previous = 1000
    Non Associated Gas Discrepancy from Update Model P90 = 50
    Non Associated Gas Discrepancy from Production Performance Analysis P90 = 30
    Non Associated Gas Discrepancy from Well Intervention P90 = 20
    Non Associated Gas Discrepancy from Unaccounted Changes P90 = 10
    Non Associated Gas Discrepancy from Consumed in Operations P90 = 5
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR P90 Current = 900
    Non Associated Gas GRR/CR/PR P90 Previous = 1000
    Non Associated Gas Discrepancy from Update Model P90 = 50
    Non Associated Gas Discrepancy from Production Performance Analysis P90 = 30
    Non Associated Gas Discrepancy from Well Intervention P90 = 20
    Non Associated Gas Discrepancy from Unaccounted Changes P90 = 10
    Non Associated Gas Discrepancy from Consumed in Operations P90 = 5
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2005 - Oil GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P50}} = \Delta N_{pn,t - 1}^{\text{P50}} + \Delta D_{N}^\text{um P50} + \Delta D_{N}^\text{ppa P50} + \Delta D_{N}^\text{wi P50} + \Delta D_{N}^\text{uc P50} + \Delta D_{N}^\text{cio P50} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Oil GRR/CR/PR P50 Current = 1015
    Oil GRR/CR/PR P50 Previous = 1000
    Oil Discrepancy from Update Model P50 = 50
    Oil Discrepancy from Production Performance Analysis P50 = 30
    Oil Discrepancy from Well Intervention P50 = 20
    Oil Discrepancy from Unaccounted Changes P50 = 10
    Oil Discrepancy from Consumed in Operations P50 = 5
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR P50 Current = 900
    Oil GRR/CR/PR P50 Previous = 1000
    Oil Discrepancy from Update Model P50 = 50
    Oil Discrepancy from Production Performance Analysis P50 = 30
    Oil Discrepancy from Well Intervention P50 = 20
    Oil Discrepancy from Unaccounted Changes P50 = 10
    Oil Discrepancy from Consumed in Operations P50 = 5
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2006 - Condensate GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P50}} = \Delta N_{pn,t - 1}^{c \text{P50}} + \Delta D_{N^c}^\text{um P50} + \Delta D_{N^c}^\text{ppa P50} + \Delta D_{N^c}^\text{wi P50} + \Delta D_{N^c}^\text{uc P50} + \Delta D_{N^c}^\text{cio P50} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR P50 Current = 1015
    Condensate GRR/CR/PR P50 Previous = 1000
    Condensate Discrepancy from Update Model P50 = 50
    Condensate Discrepancy from Production Performance Analysis P50 = 30
    Condensate Discrepancy from Well Intervention P50 = 20
    Condensate Discrepancy from Unaccounted Changes P50 = 10
    Condensate Discrepancy from Consumed in Operations P50 = 5
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR P50 Current = 900
    Condensate GRR/CR/PR P50 Previous = 1000
    Condensate Discrepancy from Update Model P50 = 50
    Condensate Discrepancy from Production Performance Analysis P50 = 30
    Condensate Discrepancy from Well Intervention P50 = 20
    Condensate Discrepancy from Unaccounted Changes P50 = 10
    Condensate Discrepancy from Consumed in Operations P50 = 5
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2007 - Associated Gas GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P50}} = \Delta G_{pn,t - 1}^{a \text{P50}} + \Delta D_{G^a}^\text{um P50} + \Delta D_{G^a}^\text{ppa P50} + \Delta D_{G^a}^\text{wi P50} + \Delta D_{G^a}^\text{uc P50} + \Delta D_{G^a}^\text{cio P50} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR P50 Current = 1015
    Associated Gas GRR/CR/PR P50 Previous = 1000
    Associated Gas Discrepancy from Update Model P50 = 50
    Associated Gas Discrepancy from Production Performance Analysis P50 = 30
    Associated Gas Discrepancy from Well Intervention P50 = 20
    Associated Gas Discrepancy from Unaccounted Changes P50 = 10
    Associated Gas Discrepancy from Consumed in Operations P50 = 5
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR P50 Current = 900
    Associated Gas GRR/CR/PR P50 Previous = 1000
    Associated Gas Discrepancy from Update Model P50 = 50
    Associated Gas Discrepancy from Production Performance Analysis P50 = 30
    Associated Gas Discrepancy from Well Intervention P50 = 20
    Associated Gas Discrepancy from Unaccounted Changes P50 = 10
    Associated Gas Discrepancy from Consumed in Operations P50 = 5
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2008 - Non Associated Gas GRR/CR/PR: Current 2R/2C/2U must be consistent with previous 2R/2C/2U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P50}} = \Delta G_{pn,t - 1}^{\text{P50}} + \Delta D_{G}^\text{um P50} + \Delta D_{G}^\text{ppa P50} + \Delta D_{G}^\text{wi P50} + \Delta D_{G}^\text{uc P50} + \Delta D_{G}^\text{cio P50} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR P50 Current = 1015
    Non Associated Gas GRR/CR/PR P50 Previous = 1000
    Non Associated Gas Discrepancy from Update Model P50 = 50
    Non Associated Gas Discrepancy from Production Performance Analysis P50 = 30
    Non Associated Gas Discrepancy from Well Intervention P50 = 20
    Non Associated Gas Discrepancy from Unaccounted Changes P50 = 10
    Non Associated Gas Discrepancy from Consumed in Operations P50 = 5
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR P50 Current = 900
    Non Associated Gas GRR/CR/PR P50 Previous = 1000
    Non Associated Gas Discrepancy from Update Model P50 = 50
    Non Associated Gas Discrepancy from Production Performance Analysis P50 = 30
    Non Associated Gas Discrepancy from Well Intervention P50 = 20
    Non Associated Gas Discrepancy from Unaccounted Changes P50 = 10
    Non Associated Gas Discrepancy from Consumed in Operations P50 = 5
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2009 - Oil GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P10}} = \Delta N_{pn,t - 1}^{\text{P10}} + \Delta D_{N}^\text{um P10} + \Delta D_{N}^\text{ppa P10} + \Delta D_{N}^\text{wi P10} + \Delta D_{N}^\text{uc P10} + \Delta D_{N}^\text{cio P10} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Oil GRR/CR/PR P10 Current = 1015
    Oil GRR/CR/PR P10 Previous = 1000
    Oil Discrepancy from Update Model P10 = 50
    Oil Discrepancy from Production Performance Analysis P10 = 30
    Oil Discrepancy from Well Intervention P10 = 20
    Oil Discrepancy from Unaccounted Changes P10 = 10
    Oil Discrepancy from Consumed in Operations P10 = 5
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR P10 Current = 900
    Oil GRR/CR/PR P10 Previous = 1000
    Oil Discrepancy from Update Model P10 = 50
    Oil Discrepancy from Production Performance Analysis P10 = 30
    Oil Discrepancy from Well Intervention P10 = 20
    Oil Discrepancy from Unaccounted Changes P10 = 10
    Oil Discrepancy from Consumed in Operations P10 = 5
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2010 - Condensate GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P10}} = \Delta N_{pn,t - 1}^{c \text{P10}} + \Delta D_{N^c}^\text{um P10} + \Delta D_{N^c}^\text{ppa P10} + \Delta D_{N^c}^\text{wi P10} + \Delta D_{N^c}^\text{uc P10} + \Delta D_{N^c}^\text{cio P10} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR P10 Current = 1015
    Condensate GRR/CR/PR P10 Previous = 1000
    Condensate Discrepancy from Update Model P10 = 50
    Condensate Discrepancy from Production Performance Analysis P10 = 30
    Condensate Discrepancy from Well Intervention P10 = 20
    Condensate Discrepancy from Unaccounted Changes P10 = 10
    Condensate Discrepancy from Consumed in Operations P10 = 5
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR P10 Current = 900
    Condensate GRR/CR/PR P10 Previous = 1000
    Condensate Discrepancy from Update Model P10 = 50
    Condensate Discrepancy from Production Performance Analysis P10 = 30
    Condensate Discrepancy from Well Intervention P10 = 20
    Condensate Discrepancy from Unaccounted Changes P10 = 10
    Condensate Discrepancy from Consumed in Operations P10 = 5
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2011 - Associated Gas GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P10}} = \Delta G_{pn,t - 1}^{a \text{P10}} + \Delta D_{G^a}^\text{um P10} + \Delta D_{G^a}^\text{ppa P10} + \Delta D_{G^a}^\text{wi P10} + \Delta D_{G^a}^\text{uc P10} + \Delta D_{G^a}^\text{cio P10} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR P10 Current = 1015
    Associated Gas GRR/CR/PR P10 Previous = 1000
    Associated Gas Discrepancy from Update Model P10 = 50
    Associated Gas Discrepancy from Production Performance Analysis P10 = 30
    Associated Gas Discrepancy from Well Intervention P10 = 20
    Associated Gas Discrepancy from Unaccounted Changes P10 = 10
    Associated Gas Discrepancy from Consumed in Operations P10 = 5
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR P10 Current = 900
    Associated Gas GRR/CR/PR P10 Previous = 1000
    Associated Gas Discrepancy from Update Model P10 = 50
    Associated Gas Discrepancy from Production Performance Analysis P10 = 30
    Associated Gas Discrepancy from Well Intervention P10 = 20
    Associated Gas Discrepancy from Unaccounted Changes P10 = 10
    Associated Gas Discrepancy from Consumed in Operations P10 = 5
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2012 - Non Associated Gas GRR/CR/PR: Current 3R/3C/3U must be consistent with previous 3R/3C/3U, all discrepancies, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P10}} = \Delta G_{pn,t - 1}^{\text{P10}} + \Delta D_{G}^\text{um P10} + \Delta D_{G}^\text{ppa P10} + \Delta D_{G}^\text{wi P10} + \Delta D_{G}^\text{uc P10} + \Delta D_{G}^\text{cio P10} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR P10 Current = 1015
    Non Associated Gas GRR/CR/PR P10 Previous = 1000
    Non Associated Gas Discrepancy from Update Model P10 = 50
    Non Associated Gas Discrepancy from Production Performance Analysis P10 = 30
    Non Associated Gas Discrepancy from Well Intervention P10 = 20
    Non Associated Gas Discrepancy from Unaccounted Changes P10 = 10
    Non Associated Gas Discrepancy from Consumed in Operations P10 = 5
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR P10 Current = 900
    Non Associated Gas GRR/CR/PR P10 Previous = 1000
    Non Associated Gas Discrepancy from Update Model P10 = 50
    Non Associated Gas Discrepancy from Production Performance Analysis P10 = 30
    Non Associated Gas Discrepancy from Well Intervention P10 = 20
    Non Associated Gas Discrepancy from Unaccounted Changes P10 = 10
    Non Associated Gas Discrepancy from Consumed in Operations P10 = 5
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2013 - Oil Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P90}} = \Delta N_{pn,t - 1}^{\text{P90}} + \Delta D_{N}^\text{gtr P90} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Oil Reserves 1P Current = 1100
    Oil Reserves 1P Previous = 1000
    Oil Discrepancy from Commerciality P90 = 200
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 1P Current = 1000
    Oil Reserves 1P Previous = 1000
    Oil Discrepancy from Commerciality P90 = 200
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2014 - Condensate Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P90}} = \Delta N_{pn,t - 1}^{c \text{P90}} + \Delta D_{N^c}^\text{gtr P90} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

The following example should pass:

``` al
if
    Condensate Reserves 1P Current = 1100
    Condensate Reserves 1P Previous = 1000
    Condensate Discrepancy from Commerciality P90 = 200
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 1P Current = 1000
    Condensate Reserves 1P Previous = 1000
    Condensate Discrepancy from Commerciality P90 = 200
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2015 - Associated Gas Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P90}} = \Delta G_{pn,t - 1}^{a \text{P90}} + \Delta D_{G^a}^\text{gtr P90} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

The following example should pass:

``` al
if
    Associated Gas Reserves 1P Current = 1100
    Associated Gas Reserves 1P Previous = 1000
    Associated Gas Discrepancy from Commerciality P90 = 200
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 1P Current = 1000
    Associated Gas Reserves 1P Previous = 1000
    Associated Gas Discrepancy from Commerciality P90 = 200
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2016 - Non Associated Gas Reserves: Current 1P must be consistent with previous 1P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P90}} = \Delta G_{pn,t - 1}^{\text{P90}} + \Delta D_{G}^\text{gtr P90} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 1P Current = 1100
    Non Associated Gas Reserves 1P Previous = 1000
    Non Associated Gas Discrepancy from Commerciality P90 = 200
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 1P Current = 1000
    Non Associated Gas Reserves 1P Previous = 1000
    Non Associated Gas Discrepancy from Commerciality P90 = 200
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2017 - Oil Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P50}} = \Delta N_{pn,t - 1}^{\text{P50}} + \Delta D_{N}^\text{gtr P50} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Oil Reserves 2P Current = 1100
    Oil Reserves 2P Previous = 1000
    Oil Discrepancy from Commerciality P50 = 200
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 2P Current = 1000
    Oil Reserves 2P Previous = 1000
    Oil Discrepancy from Commerciality P50 = 200
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2018 - Condensate Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P50}} = \Delta N_{pn,t - 1}^{c \text{P50}} + \Delta D_{N^c}^\text{gtr P50} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

The following example should pass:

``` al
if
    Condensate Reserves 2P Current = 1100
    Condensate Reserves 2P Previous = 1000
    Condensate Discrepancy from Commerciality P50 = 200
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 2P Current = 1000
    Condensate Reserves 2P Previous = 1000
    Condensate Discrepancy from Commerciality P50 = 200
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2019 - Associated Gas Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P50}} = \Delta G_{pn,t - 1}^{a \text{P50}} + \Delta D_{G^a}^\text{gtr P50} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

The following example should pass:

``` al
if
    Associated Gas Reserves 2P Current = 1100
    Associated Gas Reserves 2P Previous = 1000
    Associated Gas Discrepancy from Commerciality P50 = 200
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 2P Current = 1000
    Associated Gas Reserves 2P Previous = 1000
    Associated Gas Discrepancy from Commerciality P50 = 200
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2020 - Non Associated Gas Reserves: Current 2P must be consistent with previous 2P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P50}} = \Delta G_{pn,t - 1}^{\text{P50}} + \Delta D_{G}^\text{gtr P50} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 2P Current = 1100
    Non Associated Gas Reserves 2P Previous = 1000
    Non Associated Gas Discrepancy from Commerciality P50 = 200
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 2P Current = 1000
    Non Associated Gas Reserves 2P Previous = 1000
    Non Associated Gas Discrepancy from Commerciality P50 = 200
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2021 - Oil Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{\text{P10}} = \Delta N_{pn,t - 1}^{\text{P10}} + \Delta D_{N}^\text{gtr P10} - \left(N_{ps,t} - N_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Oil Reserves 3P Current = 1100
    Oil Reserves 3P Previous = 1000
    Oil Discrepancy from Commerciality P10 = 200
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Reserves 3P Current = 1000
    Oil Reserves 3P Previous = 1000
    Oil Discrepancy from Commerciality P10 = 200
    Oil Sales Cumulative Production Current = 200
    Oil Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2022 - Condensate Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta N_{pn,t}^{c \text{P10}} = \Delta N_{pn,t - 1}^{c \text{P10}} + \Delta D_{N^c}^\text{gtr P10} - \left(N_{ps,t}^c - N_{ps,t - 1}^c\right)$$

The following example should pass:

``` al
if
    Condensate Reserves 3P Current = 1100
    Condensate Reserves 3P Previous = 1000
    Condensate Discrepancy from Commerciality P10 = 200
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate Reserves 3P Current = 1000
    Condensate Reserves 3P Previous = 1000
    Condensate Discrepancy from Commerciality P10 = 200
    Condensate Sales Cumulative Production Current = 200
    Condensate Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2023 - Associated Gas Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{a \text{P10}} = \Delta G_{pn,t - 1}^{a \text{P10}} + \Delta D_{G^a}^\text{gtr P10} - \left(G_{ps,t}^a - G_{ps,t - 1}^a\right)$$

The following example should pass:

``` al
if
    Associated Gas Reserves 3P Current = 1100
    Associated Gas Reserves 3P Previous = 1000
    Associated Gas Discrepancy from Commerciality P10 = 200
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas Reserves 3P Current = 1000
    Associated Gas Reserves 3P Previous = 1000
    Associated Gas Discrepancy from Commerciality P10 = 200
    Associated Gas Sales Cumulative Production Current = 200
    Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2024 - Non Associated Gas Reserves: Current 3P must be consistent with previous 3P, Change from Commerciality, and production

Severity: `strict` :no_entry:

The following equation must be true:

$$\Delta G_{pn,t}^{\text{P10}} = \Delta G_{pn,t - 1}^{\text{P10}} + \Delta D_{G}^\text{gtr P10} - \left(G_{ps,t} - G_{ps,t - 1}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas Reserves 3P Current = 1100
    Non Associated Gas Reserves 3P Previous = 1000
    Non Associated Gas Discrepancy from Commerciality P10 = 200
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Reserves 3P Current = 1000
    Non Associated Gas Reserves 3P Previous = 1000
    Non Associated Gas Discrepancy from Commerciality P10 = 200
    Non Associated Gas Sales Cumulative Production Current = 200
    Non Associated Gas Sales Cumulative Production Previous = 100
then
    validation result is False
```

### RE2025 - IOIP Mid: IOIP Mid should be greater than Sum of all projects Oil Ultimate GRR/CR/PR 3R/3C/3U if Sum of all projects Oil Ultimate GRR/CR/PR 3R/3C/3U greater than zero

Severity: `warning` :warning:

The following equation should be true:

$$\sum_{i=1}^n \left(\Delta N_{pn,i}^{\text{P10}} + N_{ps,i}\right) > 0  \implies N^{\text{P50}} > \sum_{i=1}^n \left(\Delta N_{pn,i}^{\text{P10}} + N_{ps,i}\right)$$

The following example should pass:

``` al
if
    Oil GRR/CR/PR 3R/3C/3U = 1000
    IOIP Mid = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil GRR/CR/PR 3R/3C/3U = 1000
    IOIP Mid = 800
then
    validation result is False
```

### RE2026 - IGIP Mid: IGIP Mid should be greater than Sum of all projects Non Associated Gas Ultimate 3R/3C/3U if Sum of all projects Non Associated Gas Ultimate 3R/3C/3U greater than zero

Severity: `warning` :warning:

The following equation should be true:

$$ \sum_{i=1}^n \left(\Delta G_{pn,i}^{\text{P10}} + G_{ps,i}\right) > 0 \implies G^{\text{P50}} > \sum_{i=1}^n \left(\Delta G_{pn,i}^{\text{P10}} + G_{ps,i}\right)$$

The following example should pass:

``` al
if
    Non Associated Gas GRR/CR/PR 3R/3C/3U = 1000
    IGIP Mid = 1500
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas GRR/CR/PR 3R/3C/3U = 1000
    IGIP Mid = 800
then
    validation result is False
```

### RE2027 - IGIP Low: IGIP Low Case must be greater than zero if Sum of all projects Condensate GRR/CR/PR 3R/3C/3U greater than zero

Notes: _Corrected rules. Check eSDC._

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{i=1}^n \left( \Delta N_{pn,i}^{c \text{P10}} + N_{ps,i}^c \right) > 0 \implies G^{\text{P90}} > 0$$

The following example should pass:

``` al
if
    Condensate GRR/CR/PR 3R/3C/3U = 1000
    IGIP Low = 500
then
    validation result is True
```

The following example should fail:

``` al
if
    Condensate GRR/CR/PR 3R/3C/3U = 1000
    IGIP Low = 0
then
    validation result is False
```

### RE2028 - IOIP Low: IOIP Low Case must be greater than zero if Sum of all projects Associated Gas GRR/CR/PR 3R/3C/3U greater than zero

Notes: _Corrected rules. Check eSDC._

Severity: `strict` :no_entry:

The following equation must be true:

$$\sum_{i=1}^n \left( \Delta G_{pn,i}^{a \text{P10}} + G_{ps,i}^a \right) > 0 \implies N^{\text{P90}} > 0$$

The following example should pass:

``` al
if
    Associated Gas GRR/CR/PR 3R/3C/3U = 1000
    IOIP Low = 500
then
    validation result is True
```

The following example should fail:

``` al
if
    Associated Gas GRR/CR/PR 3R/3C/3U = 1000
    IOIP Low = 0
then
    validation result is False
```

### RE2029 - IOIP Low: IOIP Low Case must be greater than sum of all projects Oil EUR GRR/CR/PR 1R/1C/1U

Notes: _New Rules_

Severity: `strict` :no_entry:

The following equation must be true:

$$N^{\text{P90}} > \sum_{i=1}^n \left( \Delta N_{pn,i}^{\text{P90}} + N_{ps,i} \right) > 0 $$

The following example should pass:

``` al
if
    Oil Sales Cumulative Production = 500
    Oil GRR/CR/PR P90 = 500
    IOIP Low = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Oil Sales Cumulative Production = 500
    Oil GRR/CR/PR P90 = 500
    IOIP Low = 1000
then
    validation result is False
```

### RE2030 - IGIP Low: IGIP Low Case must be greater than sum of all projects Non Associated Gas EUR GRR/CR/PR 1R/1C/1U

Notes: _New Rules_

Severity: `strict` :no_entry:

The following equation must be true:

$$G^{\text{P90}} > \sum_{i=1}^n \left( \Delta G_{pn,i}^{\text{P90}} + G_{ps,i} \right) > 0 $$

The following example should pass:

``` al
if
    Non Associated Gas Sales Cumulative Production = 500
    Non Associated Gas GRR/CR/PR P90 = 500
    IGIP Low = 2000
then
    validation result is True
```

The following example should fail:

``` al
if
    Non Associated Gas Sales Cumulative Production = 500
    Non Associated Gas GRR/CR/PR P90 = 500
    IGIP Low = 1000
then
    validation result is False
```