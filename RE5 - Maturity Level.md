# RE5 - Maturity Level

## List of Rules

### RE5001 - Project Level: If in the current report the sales production is more than zero, then the project level must be in E0. On Production

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} > 0 \right) \lor \left( q_{c, t_R} > 0 \right) \lor \left( q_{a, t_R} > 0 \right) \lor \left( q_{n, t_R} > 0 \right) \implies M_{t_R} = E_0
$$

```python
import esdc
```

### RE5002 - Project Level: If in the current report the sales production is zero, then the project level cannot be in E0. On Production

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \implies M_{t_R} \neq E_0
$$

```python
import esdc
```

### RE5003 - Project Level: If in the previous report project level is E1. Production on Hold and in the current report the project does not have GROOVY Report and also no production, then the project level must be E4. Production Pending

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1} = E_1\right) \land \left(G_r \equiv \bot \right) \implies M_{t_R} =E_4
$$

```python
import esdc
```

### RE5004 - Project Level: If in the previous report the project level is E1. Production on Hold for the last three years and also no production in the current report, then the project level must be E4. Production Pending

Severity: `strict` :no_entry:

The following rule should be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1} = M_{t_R - 2} = M_{t_R - 3} = E_1\right)  \implies M_{t_R} = E_4
$$

```python
import esdc
```

### RE5005 - Project Level: If in the previous report the project level is E4. Production Pending and does not have GROOVY report and also no production in the current report, then the project level must be in E7. Production not Viable

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1} = E_4\right) \land \left(G_r \equiv \bot \right) \implies M_{t_R} = E_7
$$

```python
import esdc
```

### RE5006 - Project Level: If in the previous report the project level is E4. Production Pending, and in the current report the project does have GROOVY report and no production, then the project level must be in E4. Production Pending

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1} = E_4\right) \land \left(G_r \equiv \top \right) \implies M_{t_R} = E_4
$$

```python
import esdc
```

### RE5007 - Project Level: If the project level is E2. Under Development for the last three years and does not have GROOVY Report, then the project level should be in E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1}=M_{t_R - 2} = M_{t_R - 3} = E_2\right) \land \left(G_r \equiv \bot \right) \implies M_{t_R} = E_5
$$

```python
import esdc
```

### RE5008 - Project Level: If the project level is E3. Justified for Development for the last three years and does not have GROOVY Report, then the project level should be in E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1}=M_{t_R - 2} = M_{t_R - 3} = E_3\right) \land \left(G_r \equiv \bot \right) \implies M_{t_R} = E_5
$$

```python
import esdc
```

### RE5009 - Project Level: If in the previous report the project level is E2. Under Development then in the current report the project level should be either E0. On Production, E2. Under Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_5\right\} \\
M_{t_R - 1} = E_2 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5010 - Project Level: If in the previous report the project level is E3. Justified for Development then in the current report the project level should be either E0. On Production, E2. Under Development, E3. Justified for Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, E_5\right\} \\
M_{t_R - 1} = E_3 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5011 - Project Level: If in the previous report the project level is E5. Development Unclarified then in the current report the project level should be either E0. On Production, E2. Under Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_5\right\} \\
M_{t_R - 1} = E_5 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5012 - Project Level: If in the previous report the project level is E6. Further Development then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or E8. Further Development not Viable

Severity: `strict` :no_entry:

$$
M_s = \left\{E_0, E_2, E_3, E_8\right\} \\
M_{t_R - 1} = E_6 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5013 - Project Level: If in the previous report the project level is E7. Production not Viable and the project does have GROOVY report, then the project level should be in E4. Production Pending

Severity: `strict` :no_entry:

$$
\left(M_{t_R - 1} = E_7 \right) \land \left(G_r \equiv \top \right) \implies M_{t_R} = E_4
$$

```python
import esdc
```

### RE5014 - Project Level: If in the previous report the project level is E7. Production not Viable, then in the current report the project level must be either E0. On Production, E4. Development Pending, or E7 Production not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_4, E_7\right\} \\
M_{t_R - 1} = E_7 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5015 - Project Level: If in the previous report the project level is E8. Further Development not Viable, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or E8 Further Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3,E_8\right\} \\
M_{t_R - 1} = E_8 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5016 - Project Level: If in the previous report the project level is X0. Development Pending, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, X2. Development Undetermined, or X3. Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_0, X_2, X_3\right\} \\
M_{t_R - 1} = X_0 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5017 - Project Level: If in the previous report the project level is X1. Discovery under Evaluation, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, X1. Discovery under Evaluation, or X2. Development Undetermined

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_0, X_1, X_2\right\} \\
M_{t_R - 1} = X_1 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5018 - Project Level: If the project level is X1. Discovery under Evaluation for the last two  years, then in the current report project level cannot be in X1. Discovery under Evaluation anymore

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_{t_R - 1} = M_{t - 2} = X_1 \implies M_{t_R} \neq X_1
$$

```python
import esdc
```

### RE5019 - Project Level: if in the previous report the project level is X2. Development Undetermined, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, or X2. Development Undetermined

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_0, X_2\right\} \\
M_{t_R - 1} = X_2 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5020 - Project Level: if in the previous report the project level is X3. Development not Viable, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or X3. Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_3\right\} \\
M_{t_R - 1} = X_3 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5021 - Project Level: if in the previous report the project level is X4. Inconclusive Flow, then in the current report the project level must be either E3. Justified for Development, X0. Development Pending, X1. Discovery Under Evaluation, or X4. Inconclusive Flow

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{ E_3, X_0, X_1, X_4\right\} \\
M_{t_R - 1} = X_4 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5022 - Project Level: if in the previous report the project level is X5. Prospect, then in the current report the project level must be either X0. Development Pending, X1. Discovery Under Evaluation, X4. Inconclusive Flow, or X5. Prospect

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{ X_0, X_1, X_4, X_5\right\} \\
M_{t_R - 1} = X_5 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5023 - Project Level: if in the previous report the project level is X6. Lead, then in the current report the project level must be either X1. Discovery Under Evaluation X4. Inconclusive Flow, X5. Prospect, or X6. Lead

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{ X_1, X_4, X_5, X_6\right\} \\
M_{t_R - 1} = X_6 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5024 - Project Level: If 0 < GCF Total < 1, then the project level is either X6. Lead or X5. Prospect

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_s = \left\{X_5, X_6\right\} \\
0 < P_g < 1 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5025 - Project Level: If GCF Total = 1, then the project level should be X4 or higher

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_E = \left\{E_0, \dots, E_8 \right\} \\
M_s = \left\{M_E, X_0, \dots X_4 \right\} \\
P_g = 1 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

### RE5026 - Project Level: If GCF Total = 0, then project should be dry or dissolved

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_A = \left\{A_1, A_2 \right\} \\
P_g = 0 \implies M_{t_R} \in M_A
$$

```python
import esdc
```

### RE5027 - GCF Source Rock: If in the previous report the GCF Source Rock is not 50% - Neutral, then GCF Source Rock should not be 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, s, t_R - 1} \neq 0.5 \implies P_{g, s, t_R} \neq 0.5
$$

```python
import esdc
```

### RE5028 - GCF Reservoir: If in the previous report the GCF Reservoir is not 50% - Neutral, then GCF Reservoir should not be 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, r, t_R - 1} \neq 0.5 \implies P_{g, r, t_R} \neq 0.5
$$

```python
import esdc
```

### RE5029 - GCF Trap and Seal: If in the previous report the GCF Trap and Seal is not 50% - Neutral, then GCF Trap and Seal should not be 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, ts, t_R - 1} \neq 0.5 \implies P_{g, ts, t_R} \neq 0.5
$$

```python
import esdc
```

### RE5030 - GCF Dynamic: If in the previous report the GCF Dynamic is not 50% - Neutral, then GCF Dynamic should not be 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, m, t_R - 1} \neq 0.5 \implies P_{g, m, t_R} \neq 0.5
$$

```python
import esdc
```

### RE5031 - GCF Total: If in the previous report the project level is X6. Lead and in the current report the project level is X5. Prospect, then current GCF total should be higher than last year

Severity: `warning` :warning:

The following rule should be true:

$$
\left(M_{t_R - 1} = X_6\right) \land \left(M_{t_R} = X_5\right) \implies P_{g, t_R - 1} \leq P_{g, t_R}
$$

```python
import esdc
```

### RE5032 - Project Level: If one of GCF element is 50% - Neutral, then the project level should be X6. Lead

Severity: `warning` :warning:

The following rule should be true:

$$
\left( P_{g, s, t_R} = 0.5\right) \lor \left( P_{g, r, t_R} = 0.5 \right) \lor \left( P_{g, ts, t_R} = 0.5 \right) \lor \left( P_{g, m, t_R} = 0.5 \right) \implies M_{t_R} = X_6
$$

```python
import esdc
```

### RE5033 - GCF Source Rock: If project is abandoned, then the GCF source rock should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \left\{A_1, A_2 \right\} \\
M_{t_R} \in M_A \implies \left( P_{g, s, t_R} = 1\right) \lor \left( P_{g, s, t_R} = 0\right)
$$

```python
import esdc
```

### RE5034 - GCF Reservoir: If project is abandoned, then the GCF reservoir should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \left\{A_1, A_2 \right\} \\
M_{t_R} \in M_A \implies \left( P_{g, r, t_R} = 1\right) \lor \left( P_{g, r, t_R} = 0\right)
$$

```python
import esdc
```

### RE5035 - GCF Trap and Seal: If project is abandoned, then the GCF Trap and Seal should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \left\{A_1, A_2 \right\} \\
M_{t_R} \in M_A \implies \left( P_{g, ts, t_R} = 1\right) \lor \left( P_{g, ts, t_R} = 0\right)
$$

```python
import esdc
```

### RE5036 - GCF Dynamic: If project is abandoned, then the GCF Dynamic should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \left\{A_1, A_2 \right\} \\
M_{t_R} \in M_A \implies \left( P_{g, m, t_R} = 1\right) \lor \left( P_{g, m, t_R} = 0\right)
$$

```python
import esdc
```

### RE5037 - GCF Source Rock: If previous GCF Source Rock is higher than 0.5, then the GCF source rock should be higher than or equal to previous GCF Source Rock

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, s, t_R - 1} > 0.5 \implies P_{g, s, t_R} \geq P_{g, s, t_R - 1}
$$

```python
import esdc
```

### RE5038 - GCF Reservoir: If previous GCF Reservoir is higher than 0.5, then the GCF Reservoir should be higher than or equal to previous GCF Reservoir

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, r, t_R - 1} > 0.5 \implies P_{g, r, t_R} \geq P_{g, r, t_R - 1}
$$

```python
import esdc
```

### RE5039 - GCF Trap and Seal: If previous GCF Trap and Seal is higher than 0.5, then the GCF Trap and Seal should be higher than or equal to previous GCF Trap and Seal

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, ts, t_R - 1} > 0.5 \implies P_{g, ts, t_R} \geq P_{g, ts, t_R - 1}
$$

```python
import esdc
```

### RE5040 - GCF Dynamic: If previous GCF Dynamic is higher than 0.5, then the GCF Dynamic should be higher than or equal to previous GCF Dynamic

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, m, t_R - 1} > 0.5 \implies P_{g, m, t_R} \geq P_{g, m, t_R - 1}
$$

```python
import esdc
```
