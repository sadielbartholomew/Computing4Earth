# Earth System Modelling

```{contents}
```

## Modelling and simulation

TODO

## Model types

TODO

### GCM vs. ESM

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
scientific heritage and/or development team. Over time, successive versions of the family
incorporate new physical parameterisations, numerical methods, resolutions and
component models.

An example is the
[HadGEM (Hadley Centre Global Environment Model)](https://www.metoffice.gov.uk/research/approach/modelling-systems/unified-model/climate-models/hadgem3)
family developed mainly the UK's Met Office Hadley Centre.

The HadGEM family illustrates how climate models evolve over time. Successive generations
generally incorporate improvements in spatial resolution alongside advances in the
representation of physical, chemical and biological processes. Beginning with
HadGEM2 (see {cite}`hadgem2-family-gmd`), and continuing in the latest generation HadGEM3,
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
**configuration**. The table below provides examples.

| Term                    | Meaning                                                                                                                                                     | Example                              |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| **Model family**        | A lineage of related models sharing a common codebase, scientific heritage and development team.                                                            | **HadGEM**, CESM, ICON, ACCESS, EC-Earth |
| **Model generation**    | A major version within a family, typically representing substantial scientific or software developments.                                                    | HadGEM**1**, HadGEM**2**, HadGEM**3**            |
| **Model configuration** | A specific implementation of a model generation, defined by its component models, parameterisations, coupling, spatial resolution and intended application. (See below.) | HadGEM3**-GC3.1-LL**, HadGEM3**-GC3.1-MM**   |

```

### Configurations of models

***

## Model spin-up

TODO

***

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
