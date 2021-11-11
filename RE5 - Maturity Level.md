# RE5 - Maturity Level

## List of Rule

### RE5001 - Project Level: If last year hydrocarbon production is more than zero, then the project level must be in E0. On Production

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t-1} > 0 \right) \land \left( q_{c, t-1} > 0 \right) \land \left( q_{a, t-1} > 0 \right) \land \left( q_{n, t-1} > 0 \right) \implies M_t = E_0
$$

```python
import esdc
```

### RE5002 - Project Level: If last year hydrocarbon sales production is zero, then Project Level cannot be in E0. On Production

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \implies M_t \neq E_0
$$

```python
import esdc
```

### RE5003 - Project Level: If last year project level is E1. Production on Hold and the project does not have GROOVY Report and also no production in previous year, then Project Level must be E4. Production Pending

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \land \left(M_{t-1} = E_1\right) \land \left(G_r \equiv \bot \right) \implies M_t =E_4
$$

```python
import esdc
```

### RE5004 - Project Level: If project level is E1. Production on Hold for the last three years and also no production in previous year, then Project Level must be E4. Production Pending

Severity: `strict` :no_entry:

The following rule should be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \land \left(M_{t-1}=M_{t-2} = M_{t - 3} = E_1\right)  \implies M_t = E_4
$$

```python
import esdc
```

### RE5005 - Project Level: If last year project level is E4. Production Pending and does not have GROOVY report and also no production in previous year, then Project Level must be in E7. Production not Viable

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \land \left(M_{t-1} = E_4\right) \land \left(G_r \equiv \bot \right) \implies M_t = E_7
$$

```python
import esdc
```

### RE5006 - Project Level: If last year project level is E4. Production Pending and does have GROOVY report and also no production in previous year, then Project Level must be in E4. Production Pending

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \land \left(M_{t-1} = E_4\right) \land \left(G_r \equiv \top \right) \implies M_t = E_7
$$

```python
import esdc
```

### RE5007 - Project Level: If project level is E2. Under Development for the last three years and does not have GROOVY Report, then the Project Level should be in E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \land \left(M_{t-1}=M_{t-2} = M_{t - 3} = E_2\right) \land \left(G_r \equiv \bot \right) \implies M_t = E_5
$$

```python
import esdc
```

### RE5008 - Project Level: If project level is E3. Justified for Development for the last three years and does not have GROOVY Report, then the Project Level should be in E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
\left( q_{o, t-1} = q_{c, t-1}= q_{a, t-1} = q_{n, t-1} = 0 \right) \land \left(M_{t-1}=M_{t-2} = M_{t - 3} = E_3\right) \land \left(G_r \equiv \bot \right) \implies M_t = E_5
$$

```python
import esdc
```

### RE5009 - Project Level: If last year project level is E2. Under Development then the project level should be either E0. On Production, E2. Under Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_5\right\} \\
M_{t - 1} = E_2 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5010 - Project Level: If last year project level is E3. Justified for Development then the project level should be either E0. On Production, E2. Under Development, E3. Justified for Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, E_5\right\} \\
M_{t - 1} = E_3 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5011 - Project Level: If last year project level is E5. Development Unclarified then the project level should be either E0. On Production, E2. Under Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2 E_5\right\} \\
M_{t - 1} = E_5 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5012 - Project Level: If last year project level is E6. Further Development then the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or E8. Further Development not Viable

Severity: `strict` :no_entry:

$$
M_s = \left\{E_0, E_2, E_3, E_8\right\} \\
M_{t - 1} = E_6 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5013 - Project Level: If last year project level is E7. Production not Viable and GROOVY report is available, then the project level should be in E4. Production Pending

Severity: `strict` :no_entry:

$$
\left(M_{t - 1} = E_7 \right) \land \left(G_r \equiv \top \right) \implies M_t = E_4
$$

```python
import esdc
```

### RE5014 - Project Level: If last year project level is E7. Production not Viable, then the project level must be either E0. On Production, E4. Development Pending, or E7 Production not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_4, E_7\right\} \\
M_{t - 1} = E_7 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5015 - Project Level: If last year project level is E8. Further Development not Viable, then the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or E8 Further Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3,E_8\right\} \\
M_{t - 1} = E_8 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5016 - Project Level: If last year project level is X0. Development Pending, then the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, X2. Development Undetermined, or X3. Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_0, X_2, X_3\right\} \\
M_{t - 1} = X_0 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5017 - Project Level: If last year project level is X1. Discovery under Evaluation, then the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, X1. Discovery under Evaluation, or X2. Development Undetermined

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_0, X_1, X_2\right\} \\
M_{t - 1} = X_1 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5018 - Project Level: If project level is X1. Discovery under Evaluation for the last two  years, then project level cannot be in X1. Discovery under Evaluation anymore

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_{t - 1} = M_{t - 2} = X_1 \implies M_t \neq X_1
$$

```python
import esdc
```

### RE5019 - Project Level: if last year project level is X2. Development Undetermined, then the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, or X2. Development Undetermined

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_0, X_2\right\} \\
M_{t - 1} = X_2 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5020 - Project Level: if last year project level is X3. Development not Viable, then the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or X3. Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{E_0, E_2, E_3, X_3\right\} \\
M_{t - 1} = X_3 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5021 - Project Level: if last year project level is X4. Inconclusive Flow, then the project level must be either E3. Justified for Development, X0. Development Pending, X1. Discovery Under Evaluation, or X4. Inconclusive Flow

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{ E_3, X_0, X_1, X_4\right\} \\
M_{t - 1} = X_4 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5022 - Project Level: if last year project level is X5. Prospect, then the project level must be either X0. Development Pending, X1. Discovery Under Evaluation, X4. Inconclusive Flow, or X5. Prospect

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{ X_0, X_1, X_4, X_5\right\} \\
M_{t - 1} = X_5 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5023 - Project Level: if last year project level is X6. Lead, then the project level must be either X1. Discovery Under Evaluation X4. Inconclusive Flow, X5. Prospect, or X6. Lead

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\{ X_1, X_4, X_5, X_6\right\} \\
M_{t - 1} = X_6 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5024 - Project Level: If 0 < GCF Total < 1, then project level is either X6. Lead or X5. Prospect

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_s = \left\{X_5, X_6\right\} \\
0 < P_g < 1 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5025 - Project Level: If GCF Total = 1, then project level should be X4 or higher

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_E = \left\{E_0, \dots, E_8 \right\} \\
M_s = \left\{M_E, X_0, \dots X_4 \right\} \\
P_g = 1 \implies M_t \in M_s
$$

```python
import esdc
```

### RE5026 - Project Level: If GCF Total = 0, then project should be dry or dissolved

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_A = \left\{A_0, A_1 \right\} \\
P_g = 0 \implies M_t \in M_A
$$

```python
import esdc
```

### RE5027 - GCF Source Rock: If last year GCF Source Rock is not 50% - Neutral, then GCF Source Rock should not 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, s, t - 1} \neq 0.5 \implies P_{g, s, t} \neq 0.5
$$

```python
import esdc
```

### RE5028 - GCF Reservoir: If last year GCF Reservoir is not 50% - Neutral, then GCF Reservoir should not 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, r, t - 1} \neq 0.5 \implies P_{g, r, t} \neq 0.5
$$

```python
import esdc
```

### RE5029 - GCF Trap and Seal: If last year GCF Trap and Seal is not 50% - Neutral, then GCF Trap and Seal should not 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, ts, t - 1} \neq 0.5 \implies P_{g, ts, t} \neq 0.5
$$

```python
import esdc
```

### RE5030 - GCF Migration: If last year GCF Migration is not 50% - Neutral, then GCF Migration should not 50% - Neutral

Severity: `warning` :warning:

The following rule should be true:

$$
P_{g, m, t - 1} \neq 0.5 \implies P_{g, m, t} \neq 0.5
$$

```python
import esdc
```

### RE5031 - GCF Total: If last year project level is X6. Lead and current project level is X5. Prospect, then current GCF total should be higher than last year

Severity: `warning` :warning:

The following rule should be true:

$$
\left(M_{t - 1} = X_6\right) \land \left(M_t = X_5\right) \implies P_{g, t - 1} \leq P_{g, t}
$$

```python
import esdc
```

### RE5032 - Project Level: If one of GCF element is 50% - Neutral, then Project Level should be X6. Lead

Severity: `warning` :warning:

The following rule should be true:

$$
\left( P_{g, s, t} = 0.5\right) \lor \left( P_{g, r, t} = 0.5 \right) \lor \left( P_{g, ts, t} = 0.5 \right) \lor \left( P_{g, m, t} = 0.5 \right) \implies M_t = X_6
$$

```python
import esdc
```
