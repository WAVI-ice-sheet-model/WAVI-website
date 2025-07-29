WAVI.jl is a software package to simulate the flow of ice sheets. At its heart, it is a piece of software that solves equations that describe the flow of ice on continental lengthscales.

_Here at WAVI.jl, we're trying to make our code as accessible and friendly as possible._

### Installation

You will need to [install Julia](https://julialang.org/downloads/) to run WAVI.jl.

You can install the latest version of WAVI using Julia's in-build package manager:

```julia title="Installation"
using Pkg
Pkg.add("WAVI"))
```

### Usage
As an example, we can run the [MISMIP+ experiment](http://www.climate-cryosphere.org/activities/targeted/153-misomip/1412-mismip-plus),
the latest ice sheet model intercomparison.

First, we set up the grid along with other model parameters. We'll use a grid with 80x10 grid points
and 8km resolution in both dimensions, and 4 vertical levels:

```julia title="Grid Setup"
using WAVI

grid = Grid(
    nx = 80,
    ny = 10,
    nσ = 4,
    dx = 8000.,
    dy = 8000.,
    u_iszero = ["north"],
    v_iszero = ["east", "west"]
)

bed = WAVI.mismip_plus_bed 
params = Params(accumulation_rate = 0.3)
solver_params =  SolverParams(maxiter_picard = 1)
```
Then we define the model, and we define timestepping parameters for out forwards simulations.

We'll want to run the simulation to steady state for 10000 years with a timestep of 0.5 years.

Finally we define our simulation using our model and timestepping parameters:

```julia title="Model & Simulation definition"
model = Model(
    grid = grid,
    bed_elevation = bed,
    params = params
)

timestepping_params = TimesteppingParams(
    dt = 0.5,
    end_time = 10000.
)

simulation = Simulation(
    model = model,
    timestepping_params = timestepping_params
)
```

With simulation defined, it's ready to go, let's run!

```julia title="Running the model"
run_simulation!(simulation)
```
It's as easy as that: entry into the state of the art ice sheet model intercomparison 😎.

## Repository & Documentation

Discover more use cases in WAVI.jl's extensive documentation:

[WAVI.jl Repository](https://github.com/RJArthern/WAVI.jl){ .md-button .md-button--primary }
[WAVI.jl Documentation](https://rjarthern.github.io/WAVI.jl/){ .md-button }

## Extending WAVI

There are several other tools which help make WAVI easier to use at scale.

[:octicons-arrow-right-24: Read more about other WAVI tools](extend_wavi.md)
