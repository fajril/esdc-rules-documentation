# RE3 - Reservoir Properties

## List of Rules

### RE3001 - IOIP: Low Case value should be lower than or equal to the result of Volumetric Method

severity: `warning` :warning:

The following equation should be true:

$$
V_{gr}^{\text{P90}} = NTG^{\text{P90}} = \phi^{\text{P90}} = S_o^{\text{P90}} = E_o^{\text{P90}} \neq \emptyset \implies N^{\text{P90}} \leq 7758 \cdot V_{gr}^{\text{P90}} \cdot NTG^{\text{P90}} \cdot \phi^{\text{P90}} \cdot S_o^{\text{P90}} \cdot E_o^{\text{P90}}
$$

```python
import esdc
```

### RE3002 - IOIP: Mid Case value should be lower than or equal to the result of Volumetric Method

severity: `warning` :warning:

The following equation should be true:

$$
V_{gr}^{\text{P50}} = NTG^{\text{P50}} = \phi^{\text{P50}} = S_o^{\text{P50}} = E_o^{\text{P50}} \neq \emptyset \implies N^{\text{P50}} \leq 7758 \cdot V_{gr}^{\text{P50}} \cdot NTG^{\text{P50}} \cdot \phi^{\text{P50}} \cdot S_o^{\text{P50}} \cdot E_o^{\text{P50}}
$$

```python
import esdc
```

### RE3003 - IOIP: High Case value should be lower than or equal to the result of Volumetric Method

severity: `warning` :warning:

The following equation should be true:

$$
V_{gr}^{\text{P10}} = NTG^{\text{P10}} = \phi^{\text{P10}} = S_o^{\text{P10}} = E_o^{\text{P10}} \neq \emptyset \implies N^{\text{P10}} \leq 7758 \cdot V_{gr}^{\text{P10}} \cdot NTG^{\text{P10}} \cdot \phi^{\text{P10}} \cdot S_o^{\text{P10}} \cdot E_o^{\text{P10}}
$$

```python
import esdc
```

### RE3004 - IGIP: Low Case value should be lower than or equal to the result of Volumetric Method

severity: `warning` :warning:

The following equation should be true:

$$
V_{gr}^{\text{P90}} = NTG^{\text{P90}} = \phi^{\text{P90}} = S_g^{\text{P90}} = E_g^{\text{P90}} \neq \emptyset \implies G^{\text{P90}} \leq 43560 \cdot V_{gr}^{\text{P90}} \cdot NTG^{\text{P90}} \cdot \phi^{\text{P90}} \cdot S_g^{\text{P90}} \cdot E_g^{\text{P90}}
$$

```python
import esdc
```

### RE3005 - IGIP: Mid Case value should be lower than or equal to the result of Volumetric Method

severity: `warning` :warning:

The following equation should be true:

$$
V_{gr}^{\text{P50}} = NTG^{\text{P50}} = \phi^{\text{P50}} = S_g^{\text{P50}} = E_g^{\text{P50}} \neq \emptyset \implies G^{\text{P50}} \leq  43560 \cdot V_{gr}^{\text{P50}} \cdot NTG^{\text{P50}} \cdot \phi^{\text{P50}} \cdot S_g^{\text{P50}} \cdot E_g^{\text{P50}}
$$

```python
import esdc
```

### RE3006 - IGIP: High Case value should be lower than or equal to the result of Volumetric Method

severity: `warning` :warning:

The following equation should be true:

$$
V_{gr}^{\text{P10}} = NTG^{\text{P10}} = \phi^{\text{P10}} = S_g^{\text{P10}} = E_g^{\text{P10}} \neq \emptyset \implies N^{\text{P10}} \leq 43560 \cdot V_{gr}^{\text{P10}} \cdot NTG^{\text{P10}} \cdot \phi^{\text{P10}} \cdot S_g^{\text{P10}} \cdot E_g^{\text{P10}}
$$

```python
import esdc
```
