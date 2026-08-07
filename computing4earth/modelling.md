# Earth System Modelling

```{contents}
```

## Modelling and simulation

TODO

## Model types

% Good sources TODO review and reference:
% - https://www.gfdl.noaa.gov/climate-modeling/
% - https://www.carbonbrief.org/qa-how-do-climate-models-work
% - https://apps.epri.com/climate-data-user-guide/en/review-of-climate-models.html

### GCM vs. ESM

 Both an Earth System Model ({term}`ESM` henceforth) and a General Circulation Model
({term}`GCM` henceforth) are mathematical representations of the entire earth
 system, including the interconnected physical components such as the atomsphere, ocean,
 land and ice/cryosphere, but an {term}`ESM` goes beyond an {term}`GCM` to include
 representation of the chemical and biological processes occuring on Earth which
 feed back to the weather/climate system.
 
 A GCM will use predetermined inputs
 corresponding to the state of  such processes, for example the atmospheric composition and
 greenhouse gas emissions or deforestation by humans, but an ESM will simulate how these
 develop over time and therefore are more complex but in return include important
 feedbacks which can amplify or dampen the state of climate change and are critical
 for studying its long-germ evolution.

Examples of components which an ESM will represent which a GCM won't include:

- biogeochemical cycles, notably the carbon cycle;
- atmospheric chemistry e.g. ozone and aerosols;
- dynamic vegetation and land-based ecosystems;
- marine biogeochemistry and ocean ecosystems.

#### ESMs

TODO

#### General circulation models (GCMs)

TODO

***

### Climate models vs. weather models

TODO

### Scenario-based modelling

TODO

### Resolution and time stepping

#### Resolution

See also {ref}`grid-reso` for more on resolution.

TODO

#### Time stepping

TODO

#### Downscaling

TODO

(parameterisations)=

### Parameterisations

When scientific processes are any of the following:
- too small in scale to be captured (we say *resolved*) by the grid cell size;
- the equations that govern them are too mathematically complex or unpredictable;
- it is too computationally expensive (in time or memory etc.) to calculate per cell;

they are treated via *parameterisation*.

Parameterisations are representations of the given physical or chemical processes
which don't directly calculate to simulate the process but instead simplify by
approximating through use of representative variables or alternative datasets,
for example in terms of the mean values across the grid box.

Common parameterisations used in models are for turbulence, convection, cloud processes,
and radiative transfer.

### Scales

The spatial scales of processes influencing and describing weather and climate vary widely, as indicated
in the diagram:

```{figure} https://static.cambridge.org/binary/version/id/urn:cambridge.org:id:binary:20220412092640702-0514:S2634460222000061:S2634460222000061_fig1.png
---
name: atmospheric-time-space-scales
width: 100%
---
Important processes influencing weather and climate according to the
scales in space and time which they occur. A line at 100 km indicates
the spatial size under which a {term}`GCM` usually needs to parameterise
a processes. For example, eddies, tides and turbulence all lie to the
left of this line and are commonly parameterised by models.
Source: Figure 1 of {cite}`Kitsios_De_Mello_Matear_2022`.
```

% https://courses.ems.psu.edu/learningweather/node/29

There are specific terms used to describe specific spatial scales and these are summarised in the
table below.

| Spatial scale   | Approximate spatial extent (km) | Typical examples                                                             |
| --------------- | -------------------------: | ---------------------------------------------------------------------------- |
| **Microscale**  |                     < 1 | Turbulence, buildings, individual fields, dust devils                        |
| **Local**       |                   ~1–10 | Urban heat islands, local fog, sea breezes                                   |
| **Mesoscale**   |                ~1–1,000 | Thunderstorms, squall lines, sea-breeze fronts, mesoscale convective systems |
| **Synoptic**    |            ~1,000–3,000 | High- and low-pressure systems, fronts, mid-latitude cyclones                |
| **Regional**    |               ~10–1,000 | Regional climate patterns, river basins, mountain ranges                     |
| **Continental** or **Basin** |           ~1,000–10,000 | European climate, North American climate, ENSO, Indian Ocean Dipole, North Atlantic Oscillation |
| **Global**      |                Earth-wide | Global circulation, global mean temperature, planetary climate patterns      |


## Comparison and evaluation of models

TODO

### Bias Correction

TODO

***

## Tuning and Calibration

TODO

***

## Components and example models

TODO

### Atmosphere

TODO

### Ocean

TODO

### Land surface

TODO

### Cryosphere

TODO

I.e. land ice (glaciers, ice sheets) and sea ice

TODO

### Biosphere: terrestrial and marine

TODO

### Biogeochemical cycles

TODO

E.g. carbon cycle,nitrogen, sulfur, phosphorus cycles

TODO

### Anthroposphere (i.e. human systems)

TODO

***

## Coupling components

TODO

###  Coupled models

TODO

***


## Model families and configurations

### Families of models

A **model family** is a collection of related numerical models that share a common codebase,
scientific heritage and/or development team. Over time, successive versions i.e.
**generations** of the family incorporate new physical parameterisations, numerical methods,
resolutions and component models.

An example is the HadGEM (Hadley Centre Global Environment Model)
family developed mainly by the UK's Met Office Hadley Centre.

The HadGEM family illustrates how climate models evolve over time. Successive generations
generally incorporate improvements in spatial resolution alongside advances in the
representation of physical, chemical and biological processes. Beginning with
[HadGEM2](https://www.metoffice.gov.uk/research/approach/modelling-systems/unified-model/climate-models/hadgem2)
(see {cite}`hadgem2-family-gmd`), and continuing in the latest generation
[HadGEM3](https://www.metoffice.gov.uk/research/approach/modelling-systems/unified-model/climate-models/hadgem3),
each generation comprises multiple model
configurations tailored to different scientific applications ranging from operational NWP to
global climate projections.


```{figure} https://www.cs.toronto.edu/~sme/PMU199-climate-computing/pmu199-2012F/HadleyModelsResolution.jpg
---
name: hadley-centre-model-resolution-evolution
width: 100%
---
An illustration of the improving resolution across vertical and horizontal space between a predecessor of the HadGEM family and the first generation, HadGEM1, illustrating improvements in successive models. Source: https://www.cs.toronto.edu/~sme/PMU199-climate-computing/pmu199-2012F/index.html.
```

```{tip}
It is useful to make clear the distinction between **family**, **generation** and
**configuration**. A model family describes the overall lineage of related models, whereas a
model configuration is a specific implementation of a model generation for a particular
scientific purpose. The table below provides examples.

| Term                    | Meaning                                                                                                                                                     | Example                              |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| **Model family**        | A lineage of related models sharing a common codebase, scientific heritage and development team.                                                            | **HadGEM**, CESM, ICON, ACCESS, EC-Earth |
| **Model generation**    | A major version within a family, typically representing substantial scientific or software developments.                                                    | HadGEM**1**, HadGEM**2**, HadGEM**3**            |
| **Model configuration** | A specific implementation of a model generation, defined by its intended application, component models, coupling, parameterisations, and resolution (see below). | HadGEM3-**GC3.1-LL**, HadGEM3-**GC3.1-MM**   |

```

### Configurations of models

Modern climate models are rarely developed as a single, fixed model. Instead, each model
generation typically includes multiple model configurations, which share a common scientific
framework but differ in aspects such as:

- their intended application, such as NWP, seasonal forecasting or long-term climate projection;
- the atmosphere, ocean, land and sea-ice component models and coupling of them;
- which Earth system processes are represented (e.g. chemistry, aerosols or vegetation);
- physical parameterisations;
- horizontal and vertical spatial resolution;
- temporal resolution (e.g. timestep).

HadGEM again provides a useful example. The current HadGEM3 generation includes
numerous configurations designed for different scientific and operational purposes, for
instance:
- [HadGEM3-GC3.1-LL](https://ukesm.ac.uk/cmip-es-documentation/hadgem3-gc31-ll/)
  is a relatively low-resolution coupled configuration used
  extensively for CMIP6 climate simulations; while
- [HadGEM3-GC3.1-MM](https://ukesm.ac.uk/cmip-es-documentation/hadgem3-gc31-mm/)
  uses a higher-resolution atmosphere and ocean for HighResMIP
  experiments.

***

## Model spin-up

TODO

***

## Simple vs. complex climate models

### Simple climate models

TODO

% - Layer model (see e.g. https://serc.carleton.edu/integrate/teaching_materials/earth_modeling/student_materials/unit3_article1.html)
% - Energy balance models (e.g. https://github.com/climateblab/energy-balance)
% See: Energy balance climate models for the above, great review paper.
% - Radiative (equilibrium or convective) model

### From simple to complex models

TODO

```{figure} https://www.researchgate.net/profile/Venni-Arra/publication/337363210/figure/fig2/AS:826968534679564@1574176071595/A-climate-model-pyramid-showing-increasing-complexity-in-GCMs-on-the-vertical-axis-and.png
---
name: gcm-complexity-pyramid
width: 80%
---
A climate model pyramid showing increasing complexity in GCMs on the vertical axis and
the primary processes that interact with each other along the outlines: radiation, dynamics,
resolution, chemistry and surface processes. Source: {cite}`climate-model-crit-review`.
```

***

## Model variables

There are three categories of climate variables:
-  prescribed;
- progrnostic;
- diagnostic.

% See: https://ntrs.nasa.gov/api/citations/20190004951/downloads/20190004951.pdf

## Data Assimilation

TODO

***

## Ensembles

TODO

***

## Global vs. regional climate models

TODO

***

## Model intercomparison (projects)

TODO
