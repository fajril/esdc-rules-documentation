5# RE5 - Maturity Level

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

The following example should pass:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1200
    current sales con cumulative production = 600
    current sales ga cumulative production = 2000
    current sales gn cumulative production = 8000

    project level is E0. On Production

then 
    validation result is True
```

The following example should fail:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1200
    current sales con cumulative production = 600
    current sales ga cumulative production = 2000
    current sales gn cumulative production = 8000

    project level is E1. Production on Hold

then 
    validation result is False
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

The following example should pass:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    project level is E4. Production Pending

then 
    validation result is True
```

The following example should fail:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    project level is E0. On Production

then 
    validation result is False
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

The following example should pass:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    previous project level is E1. Production on Hold
    groovy status is False

    project level is E4. Production Pending

then
    validation result is True
```

The following example should fail:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    previous project level is E1. Production on Hold
    groovy status is False

    project level is E1. Production on Hold

then
    validation result is False
```

### RE5004 - Project Level: If in the previous report the project level is E1. Production on Hold for the last three years and also no production in the current report, then the project level must be E4. Production Pending

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1} = M_{t_R - 2} = M_{t_R - 3} = E_1\right)  \implies M_{t_R} = E_4
$$

```python
import esdc
```

The following example should pass:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    last three previous project level is 
        E1. Production on Hold, E1. Production on Hold, E1. Production on Hold

    project level is E4. Production Pending

then
    validation result is True
```

The following example should fail:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    last three previous project level is 
        E1. Production on Hold, E1. Production on Hold, E1. Production on Hold

    project level is E1. Production on Hold

then
    validation result is False
```

### RE5005 - Project Level: If in the previous report the project level is E4. Production Pending for the last three years and does not have GROOVY report and also no production in the current report, then the project level must be in E7. Production not Viable

Severity: `strict` :no_entry:

The following rule must be true:

$$
\left( q_{o, t_R} = q_{c, t_R}= q_{a, t_R} = q_{n, t_R} = 0 \right) \land \left(M_{t_R-1} = M_{t_R-2} = M_{t_R-3} = E_4\right) \land \left(G_r \equiv \bot \right) \implies M_{t_R} = E_7
$$

```python
import esdc
```

The following example should pass:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    last three previous project level is 
        E4. Production Pending, E4. Production Pending, E4. Production Pending

    groovy status is False

    project level is E7. Production not Viable

then
    validation result is True
```

The following example should fail:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    last three previous project level is 
        E4. Production Pending, E4. Production Pending, E4. Production Pending

    groovy status is False

    project level is E4. Production Pending

then
    validation result is False
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

The following example should pass:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    last three previous project level is 
        E4. Production Pending, E4. Production Pending, E4. Production Pending

    groovy status is True

    project level is E4. Production Pending

then
    validation result is True
```

The following example should fail:

``` al
if
    previous sales oil cumulative production = 1000
    previous sales con cumulative production = 500
    previous sales ga cumulative production = 1500
    previous sales gn cumulative production = 6000

    current sales oil cumulative production = 1000
    current sales con cumulative production = 500
    current sales ga cumulative production = 1500
    current sales gn cumulative production = 6000

    last three previous project level is 
        E4. Production Pending, E4. Production Pending, E4. Production Pending

    groovy status is False

    project level is E4. Production Pending

then
    validation result is False
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

The following example should pass:

``` al
if

    current sales oil cumulative production = 0
    current sales con cumulative production = 0
    current sales ga cumulative production = 0
    current sales gn cumulative production = 0

    last three previous project level is 
        E2. Under Development, E2. Under Development, E2. Under Development

    groovy status is False

    project level is E5. Development Unclarified

then
    validation result is True
```

The following example should fail:

``` al
if

    current sales oil cumulative production = 0
    current sales con cumulative production = 0
    current sales ga cumulative production = 0
    current sales gn cumulative production = 0

    last three previous project level is 
        E2. Under Development, E2. Under Development, E2. Under Development

    groovy status is False

    project level is E2. Under Development

then
    validation result is False
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

The following example should pass:

``` al
if

    current sales oil cumulative production = 0
    current sales con cumulative production = 0
    current sales ga cumulative production = 0
    current sales gn cumulative production = 0

    last three previous project level is 
        E3. Justified for Development, E3. Justified for Development, E3. Justified for Development

    groovy status is False

    project level is E5. Development Unclarified

then
    validation result is True
```

The following example should fail:

``` al
if

    current sales oil cumulative production = 0
    current sales con cumulative production = 0
    current sales ga cumulative production = 0
    current sales gn cumulative production = 0

    last three previous project level is 
        E3. Justified for Development, E3. Justified for Development, E3. Justified for Development

    groovy status is True

    project level is E5. Development Unclarified

then
    validation result is False
```

### RE5009 - Project Level: If in the previous report the project level is E2. Under Development then in the current report the project level should be either E0. On Production, E2. Under Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace E_0, E_2, E_5\rbrace\\
M_{t_R - 1} = E_2 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is E2. Under Development
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is E2. Under Development
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is E2. Under Development
    project level is E5. Development Unclarified

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is E2. Under Development
    project level is E4. Production Pending

then 
    validation result is False
```

### RE5010 - Project Level: If in the previous report the project level is E3. Justified for Development then in the current report the project level should be either E0. On Production, E2. Under Development, E3. Justified for Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace E_0, E_2, E_3, E_5\rbrace\\
M_{t_R - 1} = E_3 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is E3. Justified for Development
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is E3. Justified for Development
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is E3. Justified for Development
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is E3. Justified for Development
    project level is E5. Development Unclarified

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is E3. Justified for Development
    project level is E4. Production Pending

then 
    validation result is False
```

### RE5011 - Project Level: If in the previous report the project level is E5. Development Unclarified then in the current report the project level should be either E0. On Production, E2. Under Development, or E5. Development Unclarified

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace E_0, E_2, E_5\rbrace\\
M_{t_R - 1} = E_5 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is E5. Development Unclarified
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is E5. Development Unclarified
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is E5. Development Unclarified
    project level is E3. Justified for Development

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is E5. Development Unclarified
    project level is E3. Justified for Development

then 
    validation result is False
```

### RE5012 - Project Level: If in the previous report the project level is E6. Further Development then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or E8. Further Development not Viable

Severity: `strict` :no_entry:

$$
M_s = \lbrace E_0, E_2, E_3, E_8 \rbrace \\
M_{t_R - 1} = E_6 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is E6. Further Development
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is E6. Further Development
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is E6. Further Development
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is E6. Further Development
    project level is E8. Further Development not Viable

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is E6. Further Development
    project level is X1. Production on Hold

then 
    validation result is False
```

### RE5013 - Project Level: If in the previous report the project level is E7. Production not Viable and the project does have GROOVY report, then the project level must be in E4. Production Pending

Severity: `strict` :no_entry:

$$
\left(M_{t_R - 1} = E_7 \right) \land \left(G_r \equiv \top \right) \implies M_{t_R} = E_4
$$

```python
import esdc
```

The following example should pass:

``` al
if
    previous project level is E7. Production not Viable
    groovy status is True
    project level is E4. Production Pending

then
    validation result is True
    
```

The following example should fail:

``` al
if
    previous project level is E7. Production not Viable
    groovy status is True
    project level is E7. Production not Viable

then
    validation result is False
    
```

### RE5014 - Project Level: If in the previous report the project level is E7. Production not Viable, then in the current report the project level must be either E0. On Production, E4. Production Pending, or E7 Production not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace E_0, E_4, E_7 \rbrace \\
M_{t_R - 1} = E_7 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is E7. Production not Viable
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is E7. Production not Viable
    project level is E4. Production Pending

then 
    validation result is True
```

``` al
if 
    previous project level is E7. Production not Viable
    project level is E7. Production not Viable

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is E7. Production not Viable
    project level is E1. Production on Hold

then 
    validation result is False
```

### RE5015 - Project Level: If in the previous report the project level is E8. Further Development not Viable, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or E8 Further Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\lbrace E_0, E_2, E_3,E_8\right\rbrace \\
M_{t_R - 1} = E_8 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is E8. Further Development not Viable
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is E8. Further Development not Viable
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is E8. Further Development not Viable
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is E8. Further Development not Viable
    project level is E8. Further Development not Viable

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is E8. Further Development not Viable
    project level is E6. Further Development

then 
    validation result is False
```

### RE5016 - Project Level: If in the previous report the project level is X0. Development Pending, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, X2. Development Undetermined, or X3. Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\lbrace E_0, E_2, E_3, X_0, X_2, X_3\right\rbrace \\
M_{t_R - 1} = X_0 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X0. Development Pending
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is X0. Development Pending
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is X0. Development Pending
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is X0. Development Pending
    project level is X0. Development Pending

then 
    validation result is True
```

``` al
if 
    previous project level is X0. Development Pending
    project level is X2. Development Undetermined

then 
    validation result is True
```

``` al
if 
    previous project level is X0. Development Pending
    project level is X3. Development not Viable
then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X0. Development Pending
    project level is E6. Further Development

then 
    validation result is False
```

### RE5017 - Project Level: If in the previous report the project level is X1. Discovery under Evaluation, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, X1. Discovery under Evaluation, or X2. Development Undetermined

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\lbrace E_0, E_2, E_3, X_0, X_1, X_2\right\rbrace \\
M_{t_R - 1} = X_1 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is X0. Development Pending

then 
    validation result is True
```

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is X1. Discovery under Evaluation

then 
    validation result is True
```

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is X2. Development Undetermined

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X1. Discovery under Evaluation
    project level is X4. Inconclusive Flow

then 
    validation result is False
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

The following example should pass:

``` al
if 
    previous project level for two years is
        X1. Discovery under Evaluation, X1. Discovery under Evaluation
    project level is X0. Development Pending

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level for two years is
        X1. Discovery under Evaluation, X1. Discovery under Evaluation
    project level is X1. Discovery under Evaluation

then 
    validation result is False
```

### RE5019 - Project Level: if in the previous report the project level is X2. Development Undetermined, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, X0. Development Pending, or X2. Development Undetermined

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\lbrace E_0, E_2, E_3, X_0, X_2\right\rbrace \\
M_{t_R - 1} = X_2 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X2. Development Undetermined
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is X2. Development Undetermined
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is X2. Development Undetermined
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is X2. Development Undetermined
    project level is X0. Development Pending

then 
    validation result is True
```

``` al
if 
    previous project level is X2. Development Undetermined
    project level is X2. Development Undetermined

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X2. Development Undetermined
    project level is X4. Inconclusive Flow

then 
    validation result is False
```

### RE5020 - Project Level: if in the previous report the project level is X3. Development not Viable, then in the current report the project level must be either E0. On Production, E2. Under Development, E3. Justified for Development, or X3. Development not Viable

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \left\lbrace E_0, E_2, E_3, X_3\right\rbrace \\
M_{t_R - 1} = X_3 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X3. Development not Viable
    project level is E0. On Production

then 
    validation result is True
```

``` al
if 
    previous project level is X3. Development not Viable
    project level is E2. Under Development

then 
    validation result is True
```

``` al
if 
    previous project level is X3. Development not Viable
    project level is E3. Justified for Development

then 
    validation result is True
```

``` al
if 
    previous project level is X3. Development not Viable
    project level is X3. Development not Viable

then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X3. Development not Viable
    project level is X4. Inconclusive Flow

then 
    validation result is False
```

### RE5021 - Project Level: if in the previous report the project level is X4. Inconclusive Flow, then in the current report the project level must be either E3. Justified for Development, X0. Development Pending, X1. Discovery Under Evaluation, or X4. Inconclusive Flow

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace E_3, X_0, X_1, X_4 \rbrace \\
M_{t_R - 1} = X_4 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X4. Inconclusive Flow
    project level is E3. Justified for Development
then 
    validation result is True
```

``` al
if 
    previous project level is X4. Inconclusive Flow
    project level is X0. Development Pending
then 
    validation result is True
```

``` al
if 
    previous project level is X4. Inconclusive Flow
    project level is X1. Discovery under Evaluation
    validation result is True
```

``` al
if 
    previous project level is X4. Inconclusive Flow
    project level is X4. Inconclusive Flow
then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X4. Inconclusive Flow
    project level is X5. Prospect
then 
    validation result is False
```

### RE5022 - Project Level: if in the previous report the project level is X5. Prospect, then in the current report the project level must be either X0. Development Pending, X1. Discovery Under Evaluation, X4. Inconclusive Flow, or X5. Prospect

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace X_0, X_1, X_4, X_5\rbrace \\
M_{t_R - 1} = X_5 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X5. Prospect
    project level is X0. Development Pending
then 
    validation result is True
```

``` al
if 
    previous project level is X5. Prospect
    project level is X1. Discovery under Evaluation
then 
    validation result is True
```

``` al
if 
    previous project level is X5. Prospect
    project level is X4. Inconclusive Flow
then 
    validation result is True
```

``` al
if 
    previous project level is X5. Prospect
    project level is X5. Prospect
then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X5. Prospect
    project level is X6. Lead
then 
    validation result is False
```

### RE5023 - Project Level: if in the previous report the project level is X6. Lead, then in the current report the project level must be either X1. Discovery Under Evaluation X4. Inconclusive Flow, X5. Prospect, or X6. Lead

Severity: `warning` :warning:

The severity of the rule will be changed into `strict` next year.
The following rule must be true:

$$
M_s = \lbrace X_1, X_4, X_5, X_6\rbrace \\
M_{t_R - 1} = X_6 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous project level is X6. Lead
    project level is X1. Discovery under Evaluation
then 
    validation result is True
```

``` al
if 
    previous project level is X6. Lead
    project level is X4. Inconclusive Flow
then 
    validation result is True
```

``` al
if 
    previous project level is X6. Lead
    project level is X5. Prospect
then 
    validation result is True
```

``` al
if 
    previous project level is X6. Lead
    project level is X6. Lead
then 
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X6. Lead
    project level is E0. On Production
then 
    validation result is False
```

### RE5024 - Project Level: If 0 < GCF Total < 1, then the project level is either X6. Lead or X5. Prospect

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_s = \lbrace X_5, X_6\rbrace \\
0 < P_g < 1 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Source Rock = 0.8
    GCF Reservoir = 0.7
    GCF Trap and Seal = 0.4
    GCF Dynamic = 0.9

    project level is X5. Prospect
then 
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Source Rock = 0.8
    GCF Reservoir = 0.7
    GCF Trap and Seal = 0.4
    GCF Dynamic = 0.9

    project level is X4. Inconclusive Flow
then 
    validation result is False
```

### RE5025 - Project Level: If GCF Total = 1, then the project level should be X4 or higher

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_E = \lbrace E_0, \dots, E_8 \rbrace\\
M_s = \lbrace M_E, X_0, \dots X_4 \rbrace\\
P_g = 1 \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Source Rock = 1
    GCF Reservoir = 1
    GCF Trap and Seal = 1
    GCF Dynamic = 1

    project level is X4. Inconclusive Flow
then 
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Source Rock = 1
    GCF Reservoir = 1
    GCF Trap and Seal = 1
    GCF Dynamic = 1

    project level is X5. Prospect
then 
    validation result is False
```

### RE5026 - Project Level: If GCF Total = 0, then project should be dry or dissolved

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
P_g = 0 \implies M_{t_R} \in M_A
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Source Rock = 0
    GCF Reservoir = 0
    GCF Trap and Seal = 0
    GCF Dynamic = 0

    project level is A1. Dry
then 
    validation result is True
```

``` al
if 
    GCF Source Rock = 0
    GCF Reservoir = 0
    GCF Trap and Seal = 0
    GCF Dynamic = 0

    project level is A2. Dissolved
then 
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Source Rock = 0
    GCF Reservoir = 0
    GCF Trap and Seal = 0
    GCF Dynamic = 0

    project level is X5. Prospect
then 
    validation result is False
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

The following example should pass:

``` al
if 
    previous GCF Source Rock = 0.6
    GCF Source Rock = 0.4

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Source Rock = 0.6
    GCF Source Rock = 0.5

then
    validation result is False
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

The following example should pass:

``` al
if 
    previous GCF Reservoir = 0.6
    GCF Reservoir = 0.4

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Reservoir = 0.6
    GCF Reservoir = 0.5

then
    validation result is False
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

The following example should pass:

``` al
if 
    previous GCF Trap and Seal = 0.6
    GCF Trap and Seal = 0.4

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Trap and Seal = 0.6
    GCF Trap and Seal = 0.5

then
    validation result is False
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

The following example should pass:

``` al
if 
    previous GCF Dynamic = 0.6
    GCF Dynamic = 0.4

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Dynamic = 0.6
    GCF Dynamic = 0.5

then
    validation result is False
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

The following example should pass:

``` al
if 
    previous project level is X6. Lead
    previous GCF Total = 0.0625

    project level is X5. Prospect
    GCF Total = 0.1

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous project level is X6. Lead
    previous GCF Total = 0.0625

    project level is X5. Prospect
    GCF Total = 0.01

then
    validation result is False
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

The following example should pass:

``` al
if 
    GCF Source Rock = 0.5
    project level is X6. Lead

then
    validation result is True
```

``` al
if 
    GCF Reservoir = 0.5
    project level is X6. Lead

then
    validation result is True
```

``` al
if 
    GCF Trap and Seal = 0.5
    project level is X6. Lead

then
    validation result is True
```

``` al
if 
    GCF Dynamic = 0.5
    project level is X6. Lead

then
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Source Rock = 0.5
    project level is X5. Prospect

then
    validation result is False
```

``` al
if 
    GCF Reservoir = 0.5
    project level is X5. Prospect

then
    validation result is False  
```

``` al
if 
    GCF Trap and Seal = 0.5
    project level is X5. Prospect

then
    validation result is False
```

``` al
if 
    GCF Dynamic = 0.5
    project level is X5. Prospect

then
    validation result is False
```

### RE5033 - GCF Source Rock: If project is abandoned, then the GCF source rock should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
M_{t_R} \in M_A \implies \left( P_{g, s, t_R} = 1\right) \lor \left( P_{g, s, t_R} = 0\right)
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Source Rock = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Source Rock = 1
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Source Rock = 0
    project level is A2. Dissolved

then
    validation result is True
```

``` al
if 
    GCF Source Rock = 1
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Source Rock = 0.5
    project level is A1. Dry

then
    validation result is False
```

``` al
if 
    GCF Source Rock = 0.5
    project level is A2. Dissolved

then
    validation result is False
```

### RE5034 - GCF Reservoir: If project is abandoned, then the GCF reservoir should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
M_{t_R} \in M_A \implies \left( P_{g, r, t_R} = 1\right) \lor \left( P_{g, r, t_R} = 0\right)
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Reservoir = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Reservoir = 1
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Reservoir = 0
    project level is A2. Dissolved

then
    validation result is True
```

``` al
if 
    GCF Reservoir = 1
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Reservoir = 0.5
    project level is A1. Dry

then
    validation result is False
```

``` al
if 
    GCF Reservoir = 0.5
    project level is A2. Dissolved

then
    validation result is False
```

### RE5035 - GCF Trap and Seal: If project is abandoned, then the GCF Trap and Seal should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
M_{t_R} \in M_A \implies \left( P_{g, ts, t_R} = 1\right) \lor \left( P_{g, ts, t_R} = 0\right)
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Trap and Seal = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Trap and Seal = 1
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Trap and Seal = 0
    project level is A2. Dissolved

then
    validation result is True
```

``` al
if 
    GCF Trap and Seal = 1
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Trap and Seal = 0.5
    project level is A1. Dry

then
    validation result is False
```

``` al
if 
    GCF Trap and Seal = 0.5
    project level is A2. Dissolved

then
    validation result is False
```

### RE5036 - GCF Dynamic: If project is abandoned, then the GCF Dynamic should be either 0% or 100%

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
M_{t_R} \in M_A \implies \left( P_{g, m, t_R} = 1\right) \lor \left( P_{g, m, t_R} = 0\right)
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    GCF Dynamic = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Dynamic = 1
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    GCF Dynamic = 0
    project level is A2. Dissolved

then
    validation result is True
```

``` al
if 
    GCF Dynamic = 1
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    GCF Dynamic = 0.5
    project level is A1. Dry

then
    validation result is False
```

``` al
if 
    GCF Dynamic = 0.5
    project level is A2. Dissolved

then
    validation result is False
```

### RE5037 - GCF Source Rock: If previous GCF Source Rock is higher than 0.5 and the Project Level is not A1. Dry or A2. Dissolved, then the GCF source rock should be higher than or equal to previous GCF Source Rock

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
\left( P_{g, s, t_R - 1} > 0.5 \right) \land M_{t_R} \not \in M_A \implies P_{g, s, t_R} \geq P_{g, s, t_R - 1}
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous GCF Source Rock = 0.6
    GCF Source Rock = 0.6
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Source Rock = 0.6
    GCF Source Rock = 0.7
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Source Rock = 0.6
    GCF Source Rock = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    previous GCF Source Rock = 0.6
    GCF Source Rock = 0
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Source Rock = 0.7
    GCF Source Rock = 0.6
    project level is X5. Prospect

then
    validation result is False
```

### RE5038 - GCF Reservoir: If previous GCF Reservoir is higher than 0.5 and the Project Level is not A1. Dry or A2. Dissolved, then the GCF Reservoir should be higher than or equal to previous GCF Reservoir

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
\left( P_{g, r, t_R - 1} > 0.5 \right) \land M_{t_R} \not \in M_A \implies P_{g, r, t_R} \geq P_{g, r, t_R - 1}
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous GCF Reservoir = 0.6
    GCF Reservoir = 0.6
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Reservoir = 0.6
    GCF Reservoir = 0.7
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Reservoir = 0.6
    GCF Reservoir = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    previous GCF Reservoir = 0.6
    GCF Reservoir = 0
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Reservoir = 0.7
    GCF Reservoir = 0.6
    project level is X5. Prospect

then
    validation result is False
```

### RE5039 - GCF Trap and Seal: If previous GCF Trap and Seal is higher than 0.5 and the Project Level is not A1. Dry or A2. Dissolved, then the GCF Trap and Seal should be higher than or equal to previous GCF Trap and Seal

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
\left( P_{g, ts, t_R - 1} > 0.5 \right) \land M_{t_R} \not \in M_A \implies P_{g, ts, t_R} \geq P_{g, ts, t_R - 1}
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous GCF Trap and Seal = 0.6
    GCF Trap and Seal = 0.6
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Trap and Seal = 0.6
    GCF Trap and Seal = 0.7
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Trap and Seal = 0.6
    GCF Trap and Seal = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    previous GCF Trap and Seal = 0.6
    GCF Trap and Seal = 0
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Trap and Seal = 0.7
    GCF Trap and Seal = 0.6
    project level is X5. Prospect

then
    validation result is False
```

### RE5040 - GCF Dynamic: If previous GCF Dynamic is higher than 0.5 and the Project Level is not A1. Dry or A2. Dissolved, then the GCF Dynamic should be higher than or equal to previous GCF Dynamic

Severity: `warning` :warning:

The following rule should be true:

$$
M_A = \lbrace A_1, A_2 \rbrace\\
\left( P_{g, m, t_R - 1} > 0.5 \right) \land M_{t_R} \not \in M_A \implies P_{g, m, t_R} \geq P_{g, m, t_R - 1}
$$

```python
import esdc
```

The following example should pass:

``` al
if 
    previous GCF Dynamic = 0.6
    GCF Dynamic = 0.6
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Dynamic = 0.6
    GCF Dynamic = 0.7
    project level is X5. Prospect

then
    validation result is True
```

``` al
if 
    previous GCF Dynamic = 0.6
    GCF Dynamic = 0
    project level is A1. Dry

then
    validation result is True
```

``` al
if 
    previous GCF Dynamic = 0.6
    GCF Dynamic = 0
    project level is A2. Dissolved

then
    validation result is True
```

The following example should fail:

``` al
if 
    previous GCF Dynamic = 0.7
    GCF Dynamic = 0.6
    project level is X5. Prospect

then
    validation result is False
```

### RE5041 - Project Level: If sales cumulative production is more than zero, then the project level must be either E0, E1, E4, or E7

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_s = \lbrace E_0, E_1, E_4, E_7 \rbrace\\
\left( N_{ps, t_R} > 0 \right) \lor \left( N_{ps, t_R}^c > 0 \right) \lor \left( G_{ps, t_R}^a > 0 \right) \lor \left( G_{ps, t_R} > 0 \right) \implies M_{t_R} \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if
    current sales oil cumulative production = 1200

    project level is E0. On Production

then 
    validation result is True
```

The following example should fail:

``` al
if
    current sales oil cumulative production = 0
    current sales con cumulative production = 0
    current sales ga cumulative production = 0
    current sales gn cumulative production = 0

    project level is E7. Production not Viable

then 
    validation result is False
```

### RE5042 - Project Level: Project level must be filled

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_{t_R} \not \in \emptyset
$$

```python
import esdc
```

The following example should pass:

``` al
if
    project level is E0. On Production

then 
    validation result is True
```

The following example should fail:

``` al
if
    project level is null

then 
    validation result is False
```

### RE5043 - Project Level: If the project have hydrocarbon volume, project level can not be in A1. Dry nor A2. Dissolved

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_s = \lbrace A_1, A_2 \rbrace\\
\left( \Delta N_{pn}^{\text{ P10}} > 0 \right) \lor \left(\Delta N_{pn}^{c \text{ P10}} > 0 \right) \lor \left(\Delta G_{pn}^{a \text{ P10}} > 0 \right) \lor \left(\Delta G_{pn}^{\text{P10}} > 0 \right) \implies M_{t_R} \not \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if
    project level is E0. On Production
    Oil GRR/CR/PR High Value = 1000

then 
    validation result is True
```

The following example should fail:

``` al
if
    project level is A1. Dry
    Oil GRR/CR/PR High Value = 1000

then 
    validation result is False
```

### RE5044 - GCF Source Rock: GCF Source Rock must be filled

Severity: `strict` :no_entry:

The following rule must be true:

$$
P_{g, s, t_R} \not \in \emptyset
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Source Rock = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Source Rock is null

then 
    validation result is False
```

### RE5045 - GCF Reservoir: GCF Reservoir must be filled

Severity: `strict` :no_entry:

The following rule must be true:

$$
P_{g, r, t_R} \not \in \emptyset
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Reservoir = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Reservoir is null

then 
    validation result is False
```

### RE5046 - GCF Trap and Seal: GCF Trap and Seal must be filled

Severity: `strict` :no_entry:

The following rule must be true:

$$
P_{g, ts, t_R} \not \in \emptyset
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Trap and Seal = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Trap and Seal is null

then 
    validation result is False
```

### RE5047 - GCF Dynamic: GCF Dynamic must be filled

Severity: `strict` :no_entry:

The following rule must be true:

$$
P_{g, m, t_R} \not \in \emptyset
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Dynamic = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Dynamic is null

then 
    validation result is False
```

### RE5048 - GCF Source Rock: GCF Source Rock must be within the range 0 to 1

Notes: _New Rules_

Severity: `strict` :no_entry:

The following rule must be true:

$$
0 \leq P_{g, s, t_R} \leq 1
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Source Rock = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Source Rock = 50

then 
    validation result is False
```

### RE5049 - GCF Reservoir: GCF Reservoir must be within the range 0 to 1

Notes: _New Rules_

Severity: `strict` :no_entry:

The following rule must be true:

$$
0 \leq P_{g, r, t_R} \leq 1
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Reservoir = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Reservoir = 50

then 
    validation result is False
```

### RE5050 - GCF Trap and Seal: GCF Trap an Seal must be within the range 0 to 1

Notes: _New Rules_

Severity: `strict` :no_entry:

The following rule must be true:

$$
0 \leq P_{g, ts, t_R} \leq 1
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Trap and Seal = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Trap and Seal = 50

then 
    validation result is False
```

### RE5051 - GCF Dynamic: GCF Dynamic an Seal must be within the range 0 to 1

Notes: _New Rules_

Severity: `strict` :no_entry:

The following rule must be true:

$$
0 \leq P_{g, d, t_R} \leq 1
$$

```python
import esdc
```

The following example should pass:

``` al
if
    GCF Trap and Seal = 0.5

then 
    validation result is True
```

The following example should fail:

``` al
if
    GCF Trap and Seal = 50

then 
    validation result is False
```

### RE5052 - Project Level: if project level is E0, E1, E4, E7, then the sales cumulative production must be greater than 0

Notes: _New Rules_

Severity: `strict` :no_entry:

Related to RE5041. The following rule must be true:

$$
    M_s = \lbrace E_0, E_1, E_4, E_7 \rbrace\\
    N_{ps} = N_{ps}^c = G_{ps}^a = G_{ps} = 0 \implies M_{t_R} \not \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if
    oil sales cumulative production = 100
    project level is E0. On Production

then
    validation result is True
```

``` al
if
    oil sales cumulative production = 0
    project level is E1. Production on Hold

then
    validation result is False
```

### RE5053 - Project Level: If project does not have hydrocarbon volume then the project level must be either E7, E8, A1, or A2

Severity:  `strict` :no_entry:

Notes: _Moved from RE0, previously RE0043_

The following equation must be true:

$$
M_s = \lbrace E_7, E_8, A_1, A_2 \rbrace\\
\Delta N_{pn}^{\text{ P10}} = \Delta N_{pn}^{c \text{ P10}} = \Delta G_{pn}^{a \text{ P10}} = \Delta G_{pn}^{\text{P10}} = 0 \implies M_{t_R} \in M_s
$$

```python

import esdc
```

The following example should pass:

``` al
if
    Oil GRR/CR/PR High Value = 1000
    project level is E0. On Production

then
    Validation result is True

```

The following example should fail:

``` al
if
    Oil GRR/CR/PR High Value = 0
    con GRR/CR/PR High Value = 0
    ga GRR/CR/PR High Value = 0
    gn GRR/CR/PR High Value = 0
    project level is E0. On Production

then
    Validation result is False

```

### RE5054 - Project Level: Project must have reserves 1P for project maturity level E0, E1, E2, E3

Severity:  `strict` :no_entry:

Notes: _Moved from RE0, previously RE0044_

The following equation must be true:

$$
M_s = \lbrace E_0, E_1, E_2, E_3 \rbrace\\
\left( \Delta N_{ps}^{\text{ 1P}} > 0 \right) \lor \left(\Delta N_{ps}^{c \text{ 1P}} > 0 \right) \lor \left(\Delta G_{ps}^{a \text{ 1P}} > 0 \right) \lor \left(\Delta G_{ps}^{\text{1P}} > 0 \right) \implies M_{t_R} \in M_s
$$

```python

import esdc
```

The following example should pass:

``` al
if
    Oil Reserves 1P = 1000
    project level is E0. On Production

then
    Validation result is True

```

The following example should fail:

``` al
if
    Oil reserves 1P = 0
    con reserves 1P = 0
    ga reserves 1P = 0
    gn reserves 1P = 0

    project level is E0. On Production

then
    Validation result is False
```

### RE5055 - Project Level: Project must not have reserves 1P for project maturity level E4 to X6

Severity:  `strict` :no_entry:

Notes: _Moved from RE0, previously RE0045_

The following equation must be true:

$$
M_s = \lbrace E_0, E_1, E_2, E_3 \rbrace\\
\left( \Delta N_{ps}^{\text{ 1P}} = \Delta N_{ps}^{c \text{ 1P}} = \Delta G_{ps}^{a \text{ 1P}} = \Delta G_{ps}^{\text{1P}} = 0 \right) \implies M_{t_R} \notin M_s
$$

```python

import esdc
```

The following example should pass:

``` al
if
    Oil reserves 1P = 0
    con reserves 1P = 0
    ga reserves 1P = 0
    gn reserves 1P = 0

    project level is X0. Development Pending

then
    Validation result is True
```

The following example should fail:

``` al
if
    Oil reserves 1P = 0
    con reserves 1P = 0
    ga reserves 1P = 0
    gn reserves 1P = 0

    project level is E3. Justified for Development

then
    Validation result is False
```

### RE5056 - Project Remarks: Project must have remarks if there is a discrepancy in resources low

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
\sum \Delta D_{N, N^{c}, G^{a}, G}^\text{um, ppa, wi, gtr, cio P90} > 0 \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5057 - Project Remarks: Project must have remarks if there is a discrepancy in resources mid

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
\sum \Delta D_{N, N^{c}, G^{a}, G}^\text{um, ppa, wi, gtr, cio P50} > 0 \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5058 - Project Remarks: Project must have remarks if there is a discrepancy in resources high

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
\sum \Delta D_{N, N^{c}, G^{a}, G}^\text{um, ppa, wi, gtr, cio P10} > 0 \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5059 - Project Remarks: Project must have remarks if there is a change in project IOIP low

Notes: _Added for resources report 31.12.2022._

Severity: `strict` :no_entry:

$$
N_{\text{project}, t_R}^{\text{P90}} \neq N_{\text{project}, t_{R - 1}}^{\text{P90}} \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5060 - Project Remarks: Project must have remarks if there is a change in project IOIP mid

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
N_{\text{project}, t_R}^{\text{P50}} \neq N_{\text{project}, t_{R - 1}}^{\text{P50}} \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5061 - Project Remarks: Project must have remarks if there is a change in project IOIP high

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
N_{\text{project}, t_R}^{\text{P10}} \neq N_{\text{project}, t_{R - 1}}^{\text{P10}} \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5062 - Project Remarks: Project must have remarks if there is a change in project IGIP low

Notes: _Added for resources report 31.12.2022._

Severity: `strict` :no_entry:

$$
G_{\text{project}, t_R}^{\text{P90}} \neq G_{\text{project}, t_{R - 1}}^{\text{P90}} \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5063 - Project Remarks: Project must have remarks if there is a change in project IGIP mid

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
G_{\text{project}, t_R}^{\text{P50}} \neq G_{\text{project}, t_{R - 1}}^{\text{P50}} \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5064 - Project Remarks: Project must have remarks if there is a change in project IGIP high

Notes: _Added for resources report 31.12.2022_

Severity: `strict` :no_entry:

$$
G_{\text{project}, t_R}^{\text{P10}} \neq G_{\text{project}, t_{R - 1}}^{\text{P10}} \implies M_{\text{remarks}, t_R} \notin \emptyset
$$

```python

import esdc
```

### RE5065 - Project Level: If the project have hydrocarbon inplace volume, project level can not be in A1. Dry nor A2. Dissolved

Severity: `strict` :no_entry:

The following rule must be true:

$$
M_s = \lbrace A_1, A_2 \rbrace\\
 N_{project}^{\text{ P10}}  +  G_{project}^{\text{ P10}} =0 \implies M_{t_R} \not \in M_s
$$

```python
import esdc
```

The following example should pass:

``` al
if
    project level is E0. On Production
    Project Initial Oil in Place High Value = 1000

then 
    validation result is True
```

The following example should fail:

``` al
if
    project level is A1. Dry
    Project Initial Oil in Place High Value = 1000

then 
    validation result is False
```

### RE5066 - Project Level: Project must have onstream actual for project maturity level E0, E1, E4, E7

Severity:  `strict` :no_entry:

The following equation must be true:

$$
M_s = \lbrace E_0, E_1, E_4, E_7 \rbrace\\
M_{t_R} \notin M_s \implies  t_{act} \notin \empty
$$

```python
import esdc
```

### RE5067 - Project Level: Onstream actual must be lower than reporting year

Severity:  `strict` :no_entry:

The following equation must be true:
$$
t_{act} < t_R 
$$
```python
import esdc
```