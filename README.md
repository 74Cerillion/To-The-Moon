# To-The-Moon
Simulating the free-return path of the Apollo 8 CSM during its trip to the moon, using Turtle and Vec to solve the 3-body-problem

# Apollo 8 Free-Return Trajectory Simulation

A Python gravity simulation modeling an Apollo 8-style free-return trajectory around the Moon using Python's built-in `turtle` graphics module.

The project simulates the gravitational interaction between the Earth, Moon, and Apollo Command/Service Module (CSM), updating each body's acceleration, velocity, and position over time to visualize the spacecraft's trajectory.

## Project Overview

This project explores basic orbital mechanics and object-oriented programming by representing celestial bodies and spacecraft as interacting objects within a gravitational system.

The simulation contains three primary bodies:

- **Earth** — Primary gravitational body
- **Moon** — Orbits within the simulated Earth-Moon system
- **Apollo CSM** — Spacecraft following a free-return trajectory through the system

Each body's movement is calculated iteratively based on the gravitational influence of every other body in the simulation.

## Features

- Object-oriented gravitational simulation
- Multi-body gravitational interactions
- Vector-based acceleration and velocity calculations
- Numerical time-step simulation
- Earth and Moon sprite visualization
- Custom-drawn Apollo Command/Service Module
- Spacecraft orientation changes during flight
- Configurable initial spacecraft position and velocity
- Turtle-based real-time visualization

## How It Works

The simulation is organized around two primary classes.

### `GravSys`

Maintains the gravitational system and tracks:

- Bodies participating in the simulation
- Simulation time
- Time-step interval
- Main simulation loop

During each iteration, every registered body advances one simulation step.

### `Body`

Extends Python's `Turtle` class to represent an object affected by gravity.

Each body stores:

- Mass
- Position
- Velocity
- Reference to the gravitational system
- Visual representation

The `acc()` method calculates the combined gravitational acceleration produced by all other bodies:

```python
a += (G * body.mass / abs(r)**3) * r
