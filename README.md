# Vehicle Dynamics

A Python-based simulation of a horizontally configured automotive piston–crank mechanism. The program provides visual tools for understanding the physics of an internal combustion engine, including piston position, velocity, acceleration, pressure, force, and torque.

This project is intended for automotive enthusiasts, engineering students, and engineers interested in engine and vehicle dynamics.

## Demo

### Basic Execution

Run the main Python file from the terminal:

```bash
python vehicle_dynamics.py
```

### Programmatic Example

```python
from vehicle_dynamics import Car

# Create a Car object using custom parameters
car = Car(Lb=0.155, Lc=0.046)

# If no arguments are provided, the following default values are used:
"""
Lb = 0.155
Lc = 0.046
r_c = 11.5
cylinders = 8
engine_vol = 6.2
c_distance = 0.05
cyl_displacement = 0.092
mp = 0.482
mb = 0.680
nd = 3.73
Ib = 2.58e-3
m_perno = 0.132
v_car = 220
diam_wheel = 0.679
wc = 520
CG = 0.35
pa = 1
pb = 10
pc = 46
pd = 3
"""

# Run one or more available methods
car.volume()
car.pist_pressure()
car.gas_force()
car.mass_torque()
car.torque_comparison()

# A graph is generated for each method called
```

## Installation

Install the required dependencies with:

```bash
pip install -r requirements.txt
```

## 🛠️ Quick Start

```python
from Vehicle dynamics import Car

# 1. Create a Car object using the default parameters
car = Car()

# 2. Run one or more available methods
car.volume()
car.gas_force()

# 3. View the generated graphs
```

## Classes

### `Car`

The `Car` class can be initialized using the following parameters:

```python
Car(
    Lb: int | float = 0.155,
    Lc: int | float = 0.046,
    r_c: int | float = 11.5,
    cylinders: int = 8,
    engine_vol: int | float = 6.2,
    c_distance: int | float = 0.05,
    cyl_displacement: int | float = 0.092,
    mp: int | float = 0.482,
    mb: int | float = 0.680,
    nd: int | float = 3.73,
    Ib: int | float = 2.58e-3,
    m_perno: int | float = 0.132,
    v_car: int | float = 220,
    diam_wheel: int | float = 0.679,
    wc: int | float = 520,
    CG: int | float = 0.35,
    pa: int | float = 1,
    pb: int | float = 10,
    pc: int | float = 46,
    pd: int | float = 3
)
```

#### Parameters

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `r_c` (`int`, `float`): Engine compression ratio.
* `cylinders` (`int`): Number of engine cylinders.
* `engine_vol` (`int`, `float`): Total engine displacement in liters `[L]`.
* `c_distance` (`int`, `float`): Distance between the piston pin and the piston crown in meters `[m]`.
* `cyl_displacement` (`int`, `float`): Displacement of one cylinder.
* `mp` (`int`, `float`): Piston mass in kilograms `[kg]`.
* `mb` (`int`, `float`): Connecting-rod mass in kilograms `[kg]`.
* `nd` (`int`, `float`): Combined differential and wheel transmission ratio.
* `Ib` (`int`, `float`): Connecting-rod mass moment of inertia in `[kg·m²]`.
* `m_perno` (`int`, `float`): Piston-pin mass in kilograms `[kg]`.
* `v_car` (`int`, `float`): Target vehicle velocity used by the model.
* `diam_wheel` (`int`, `float`): Wheel diameter in meters `[m]`.
* `wc` (`int`, `float`): Crankshaft angular velocity in radians per second `[rad/s]`.
* `CG` (`int`, `float`): Dimensionless factor that defines the location of the connecting-rod center of mass.
* `pa` (`int`, `float`): Cylinder pressure during the intake stage `[Pa]`.
* `pb` (`int`, `float`): Cylinder pressure at the end of the compression stage `[Pa]`.
* `pc` (`int`, `float`): Cylinder pressure during the power stage `[Pa]`.
* `pd` (`int`, `float`): Cylinder pressure during the exhaust stage `[Pa]`.

The class creates a `Car` object using either the values provided by the user or the predefined default values.

Negative values are not accepted for any of the object attributes. If a negative value is provided, the class raises a `ValueError`.

## Methods

### `angles()`

Graphs the connecting-rod angle as a function of the crankshaft angle. Both angles are represented using standard angular positions in degrees `[°]`.

**Uses:**

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.

**Returns:**

A graph of the connecting-rod angle with respect to the crankshaft angle.

---

### `piston()`

Graphs the piston position as a function of the crankshaft angle.

**Uses:**

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `c_distance` (`int`, `float`): Distance between the piston pin and the piston crown in meters `[m]`.

**Returns:**

A graph of the piston position in meters `[m]` with respect to the crankshaft angle.

---

### `volume()`

Graphs the combustion-chamber volume as a function of the crankshaft angle.

**Uses:**

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `c_distance` (`int`, `float`): Distance between the piston pin and the piston crown in meters `[m]`.
* `r_c` (`int`, `float`): Engine compression ratio.

**Returns:**

A graph of the combustion-chamber volume in cubic meters `[m³]` with respect to the crankshaft angle.

---

### `angular()`

Graphs the angular velocity and angular acceleration of the connecting rod as functions of the crankshaft angle.

**Uses:**

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `wc` (`int`, `float`): Constant crankshaft angular velocity in radians per second `[rad/s]`.

**Returns:**

Graphs of the connecting-rod angular velocity `[rad/s]` and angular acceleration `[rad/s²]` with respect to the crankshaft angle.

---

### `linear_vel()`

Graphs the linear velocity and acceleration of the piston–crank mechanism as functions of the crankshaft angle.

**Uses:**

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `wc` (`int`, `float`): Constant crankshaft angular velocity in radians per second `[rad/s]`.

**Returns:**

Graphs of the linear velocity `[m/s]` and linear acceleration `[m/s²]` with respect to the crankshaft angle.

---

### `center_mass()`

Graphs the linear velocity and acceleration of the connecting rod at its center of mass as functions of the crankshaft angle.

**Uses:**

* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `wc` (`int`, `float`): Constant crankshaft angular velocity in radians per second `[rad/s]`.
* `CG` (`int`, `float`): Dimensionless factor used to determine the location of the connecting-rod center of mass.

For example, when:

```python
CG = 0.35
```

the center of mass is located at:

```python
0.35 * Lb
```

The distance is measured from the connection between the crankshaft and the connecting rod.

**Returns:**

Graphs of the center-of-mass linear velocity `[m/s]` and acceleration `[m/s²]` with respect to the crankshaft angle.

---

### `otto()`

Graphs a simplified Otto cycle for the engine.

**Uses:**

* `pa` (`int`, `float`): Cylinder pressure during the intake stage at bottom dead center, BDC.
* `pb` (`int`, `float`): Cylinder pressure at the end of the compression stage at top dead center, TDC.
* `pc` (`int`, `float`): Cylinder pressure after fuel ignition during the power stage.
* `pd` (`int`, `float`): Cylinder pressure during the exhaust stage.

**Returns:**

A graph representing the simplified Otto cycle.

---

### `pist_pressure()`

Graphs the pressure acting on the piston as a function of the crankshaft angle.

**Uses:**

* `pressure_list` (`list`): Pressure values generated by the `otto()` method.
* `volume_list` (`list`): Cylinder-volume values generated by the `volume()` method.

**Returns:**

A graph of the piston pressure with respect to the crankshaft angle.

---

### `gas_force()`

Graphs the force produced by the combustion pressure as a function of the crankshaft angle.

**Uses:**

* `pist_pressure` (`list`): Piston-pressure values generated by the `pist_pressure()` method.
* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.
* `f_list` (`list`): Force values calculated from the pressure acting on the piston.

**Returns:**

A graph of the gas force produced by combustion with respect to the crankshaft angle.

---

### `mass_torque()`

Graphs the inertial torque produced by the masses of the piston, piston pin, connecting rod, and crankshaft as a function of the crankshaft angle.

**Uses:**

* `alpha_list` (`list`): Angular-acceleration values generated by the `angular()` method.
* `Lb` (`int`, `float`): Connecting-rod length in meters `[m]`.
* `Lc` (`int`, `float`): Crankshaft radius in meters `[m]`.

**Returns:**

A graph of the inertial torque generated by the component masses with respect to the crankshaft angle.

---

### `total_torque()`

Graphs the sum of the gas torque and inertial torque as a function of the crankshaft angle.

**Uses:**

* `torque_gas_list` (`list`): Gas-torque values generated by the `gas_force()` method.
* `torque_mass_list` (`list`): Inertial-torque values generated by the `mass_torque()` method.

**Returns:**

A graph of the total torque produced by one cylinder with respect to the crankshaft angle.

---

### `torque_comparison()`

Generates three graphs comparing the gas torque, inertial torque, and total torque of an engine with a specified number of cylinders.

The method also calculates the average torque and the combined torque contribution of all cylinders at each crankshaft angle.

**Uses:**

* `total_torque_list` (`list`): Total-torque values generated by the `total_torque()` method.
* `torque_gas_list` (`list`): Gas-torque values generated by the `gas_force()` method.
* `torque_mass_list` (`list`): Inertial-torque values generated by the `mass_torque()` method.
* `cylinders` (`int`): Number of cylinders in the engine.

**Returns:**

Three graphs showing:

1. Gas torque.
2. Inertial torque.
3. Total torque.

The method also outputs the average torque and the sum of the torque contributions from all cylinders at each crankshaft angle.
