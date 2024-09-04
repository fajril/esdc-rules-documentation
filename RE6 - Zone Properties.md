# Zone Properties

## List  of Rules

### RE6001 - Porosity: Low Value must be greater than zero

Severity: `Strict` :no_entry:

The following rule must be true:

$$
\phi^{P90} > 0
$$

### RE6002 - Porosity: High Value must be lower than or equal to 0.476

Severity: `Strict` :no_entry:

The following rule must be true:

$$
\phi^{P10} \leq 0.467
$$

### RE6003 - Porosity: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
\phi^{P90} \leq \phi^{P50}
$$

### RE6004 - Porosity: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
\phi^{P50} \leq \phi^{P10}
$$

### RE6005 - Permeability: Low Value must be greater than zero

Severity: `Strict` :no_entry:

The following rule must be true:

$$
k^{P90} > 0
$$

### RE6006 - Permeability: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
k^{P90} \leq k^{P50}
$$

### RE6007 - Permeability: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
k^{P50} \leq k^{P10}
$$

### RE6008 - Net To Gross (NTG): NTG must be within the range 0 to 1

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 < NTG < 1
$$


### RE6009 - Net To Gross (NTG): Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
NTG^{P90} \leq NTG^{P50}
$$

### RE6010 - Net To Gross (NTG): Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
NTG^{P50} \leq NTG^{P10}
$$

### RE6011 - Gross Rock Volume (GRV): Low Value must be greater than zero

Severity: `Strict` :no_entry:

The following rule must be true:

$$
V_{gr} > 0
$$

### RE6012 - Gross Rock Volume (GRV): Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
V_{gr}^{P90} \leq V_{gr}^{P50}
$$

### RE6013 - Gross Rock Volume (GRV): Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
V_{gr}^{P50} \leq V_{gr}^{P10}
$$

### RE6014 - Net Pay: Low Value must be greater than to zero

Severity: `Strict` :no_entry:

The following rule must be true:

$$
h_{net} > 0
$$


### RE6015 - Net Pay: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
h_{net}^{P90} \leq h_{net}^{P50}
$$

### RE6016 - Net Pay: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
h_{net}^{P50} \leq h_{net}^{P10}
$$

### RE6017 - Oil Initial Saturation must be lower than 1 and Oil Initial Saturation must be greater than or equal to zero


Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 \leq S_{oi} < 1
$$

### RE6018 - Oil Initial Saturation: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
S_{oi}^{P90} \leq S_{oi}^{P50}
$$


### RE6019 - Oil Initial Saturation: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
S_{oi}^{P50} \leq S_{oi}^{P10}
$$

### RE6020 - Gas Initial Saturation must be lower than 1 and Gas Initial Saturation must be greater than or equal to zero
Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 \leq S_{gi} < 1
$$

### RE6021 - Gas Initial Saturation: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
S_{gi}^{P90} \leq S_{gi}^{P50}
$$

### RE6022 - Gas Initial Saturation: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
S_{gi}^{P50} \leq S_{gi}^{P10}
$$

### RE6023 - Sum of Initial Oil Saturation and Initial Gas Saturation must be lower than 1

Severity: `Strict` :no_entry:

The following rule must be true:
$$
S_{oi} + S_{gi} <1
$$

### RE6024 - Oil Shrinkage Factor must be lower than one and Oil Shrinkae Factor must be greater than or equal to zero

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0\leq E_{o}<1
$$


### RE6025 - Oil Shrinkage Factor: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
E_{o}^{P90} \leq E_{o}^{P50}
$$

### RE6026 - Oil Shrinkage Factor: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
E_{o}^{P50} \leq E_{o}^{P10}
$$

### RE6027 - Gas Shrinkage Factor must be greater than or equal to One

Severity: `Strict` :no_entry:

The following rule must be true:

$$
1 < E_{o}
$$

### RE6028 - Gas Shrinkage Factor: Low Value must be lower than or equal to Middle Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
E_{g}^{P90} \leq E_{g}^{P50}
$$

### RE6029 - Gas Shrinkage Factor: Middle Value must be lower than or equal to High Value

Severity: `Strict` :no_entry:

The following rule must be true:

$$
E_{g}^{P50} \leq E_{g}^{P10}
$$

### RE6029 - GCF Reservoir must be greater than zero and GCF Reservoir must be lower than or equal to one

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 < P_{g,r} \leq 1
$$

### RE6030 - GCF Trap & Seal must be greater than zero and GCF Trap & Seal must be lower than or equal to one

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 < P_{g,ts} \leq 1
$$

### RE6031 - GCF Source Rock must be greater than zero and GCF Source Rock must be lower than or equal to one

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 < P_{g,s} \leq 1
$$


### RE6032 - GCF Migration must be greater than zero and GCF Migration must be lower than or equal to one

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 < P_{g,m} \leq 1
$$

### RE6033 - Gas Oil Contact (GOC): Depth of Gas Oil Contact must be higher than Oil Water Contact (OWC)

Severity: `Strict` :no_entry:

The following rule must be true:

$$
 OWC < GOC   
$$


### RE6034 - Gas Water Contact: Gas Water Contact must be empty if reservoir fluid consists of oil and water only

Severity: `Strict` :no_entry:

The following rule must be true:

$$
G = 0 \implies GWC = 0
$$

### RE6035 - Oil Water Contact: Oil Water Contact must be empty if reservoir fluid consists of gas and water only

Severity: `Strict` :no_entry:

The following rule must be true:

$$
N = 0 \implies OWC = 0
$$

### RE6036 - Reservoir Pressure: Initial Reservoir Pressure must be greater than abandonment reservoir pressure

Severity: `Strict` :no_entry:

The following rule must be true:

$$
P_{res,ab}<P_{res,i}
$$

### RE6037 - Oil Saturation: Critical Oil Saturation must be greater than residual oil saturation

Severity: `Strict` :no_entry:

The following rule must be true:


$$
S_{wr}<S_{w,cr}
$$

### RE6038 - Pressure Gradient: Water Pressure Gradient must be greater than Oil Pressure Gradient

Severity: `Strict` :no_entry:

The following rule must be true:

$$\left(\frac{dP}{dL}\right)_{o} < \left(\frac{P}{Z}\right)_{w}  $$

### RE6039 - Pressure Gradient: Oil Pressure Gradient must be greater than Gas Pressure Gradient

Severity: `Strict` :no_entry:

The following rule must be true:

$$\left(\frac{dP}{dL}\right)_{g} < \left(\frac{P}{Z}\right)_{o}$$

### RE6040 - Gas to Oil Ratio (Rs): Rs should be filled if the reservoir contains Oil

Severity: `Strict` :no_entry:

The following rule must be true:

$$
N > 0 \implies R_{s} \neq \varnothing    
$$

### RE6041 - Specific Gravity: Oil Specific Gravity must be within the range 0 to 1

Severity: `Strict` :no_entry:

The following rule must be true:

$$
0 < \gamma_{o} < 1   
$$

### RE6042 - Specific Gravity: Oil specific gravity must filled if the reservoir contain Oil or Condensate

Severity: `Strict` :no_entry:

The following rule must be true:

$$
N > 0 \implies \gamma_{o} \neq \varnothing    
$$

### RE6043 - Viscocity: Oil Viscocity (at Initial and Bubble Point) must be within the range 0.1 cP to 100 cP

Severity: `Warning` :warning:

According to Tarek Ahmed book (Equations of State and PVT Analysis): The viscosity, in general, is defined as the internal resistance of the fluid to flow. It ranges from 0.1 cp for near critical to over 100 cp for heavy oil

The following rule should be true:

$$
0.01 < \mu_o < 100
$$

### RE6044 - Viscocity: Oil Viscocity (at Initial and Bubble Point) must be empty if the reservoir does not contain Oil or Condensate

Severity: `Strict` :no_entry:

The following rule must be true:

$$
N = 0 \implies (\mu_{oi} \neq \varnothing \text{ and } \mu_{ob} \neq \varnothing)
$$

### RE6045 - Viscocity: Oil Viscocity at Initial must be greater than Oil Viscocity at Bubble Point 

Severity: `Strict` :no_entry:

The following rule must be true:

$$
\mu_{ob} < \mu_{oi}
$$

### RE6046 - Gas Deviation Factor (Z): Gas Deviation Factor (at Initial and Abandonment) must be filled if IGIP is more than zero

Severity: `Strict` :no_entry:

The following rule must be true:

$$
G > 0 \implies (Z_{i} \neq \varnothing \text{ and } Z_{ab} \neq \varnothing)
$$

### RE6047 - P/Z (Pressure over Gas Deviation Factor) at Initial must be greater than P/Z at abandonment

Severity: `Strict` :no_entry:

The following rule must be true:

$$\left(\frac{P}{Z}\right)_{ab} < \left(\frac{P}{Z}\right)_{i}$$

### RE6048 - Composition: Sum of Composition fraction must be one

Severity: `Strict` :no_entry:

$$
X_{CO_{2}}+X_{C_1}+X_{C_2}+X_{C_3}+X_{iC_3}+X_{nC_4}+X_{iC_4}+X_{iC_5}+n_{C_5}+C_{6+} = 1
$$