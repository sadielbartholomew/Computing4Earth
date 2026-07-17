# Data

```{note}
We treat *meta*data as a separate topic (see [Metadata](metadata.md)) given its importance,
though really it is a topic under data so belongs under this section.
```

```{contents}
```

## Categorising data

### Provenance-based categories

Earth system datasets can be grouped into four broad categories based on how they
are generated (their **provenance**):

- observations (including satellite data, though sometimes this is treated separately);
- model simulations;
- reanalysis;
- derived.

```{note}
The terms 'dataset' (or 'data set') and '(data) product' are generally used interchangably, and can
be defined as:

> a set of data files that can contain multiple parameters and that compose a logically meaningful group of related data

% (from: https://www.earthdata.nasa.gov/engage/data-producer-resources/data-product-development-guide-producers-v2#apx_b Appendix B. Glossary) Version 2.0 of the Data Product Development Guide (DPDG) for Data Producers was released on July 10, 2024, by the NASA Earth Science Data Systems DPDG Working Group. Citation: Ramapriyan H.K., P.J.T. Leonard, E.M. Armstrong, S.J.S. Khalsa, D.K. Smith, L.F. Iredell, D.M. Wright, G.J. Huffman, and T.R. Walker. “Data Product Development Guide (DPDG) for Data Producers version 2.0. NASA Earth Science Data and Information System Standards Office, July 2024. https://doi.org/10.5067/DOC/ESCO/RFC-041VERSION2

or more loosely a 'collection of data' but it is more common to see 'product' used in published data which results from an operational or processing chain - so usually you will see 'derived products' rather than 'derived data(sets)' used in practice.
```

% CCCS ref: see specifically 'Types of data' subsection from that link

For example, this classification is [used by](https://climate.copernicus.eu/esotc/2025/about-data) the
[Copernicus Climate Change Service](https://climate.copernicus.eu/)
for climate assessment datasets (see for example the ''Types of data and using multiple sources of information' section of {cite}`C3S_WMO_2026_ESOTC2025`).

Other groups, such as the [World Meteorological Organization (WMO)](https://wmo.int/),
describe Earth system datasets more on a **lifecycle (or information chain)** basis,
progressing from observations through analyses and predictions (including
numerical prediction and reanalysis) to derived products. But the categories remain
similar in each case.

### Data availability for past, present and future

The availability of Earth system datasets depends on the **time period of interest**:

- observations are inherently retrospective: we can only make observations of the present and past because they require measurements;
- reanalysis extends observations so they are also contrained to the present and past;
- however, model simulations are unique because they can simulate historical
  behaviour as well as future climate under different forcing scenarios
  (see {ref}`forcings`): only they can provide future information.

This is summarised by this diagram which compares the time domain datasets in each category may by applicable to:

```{figure} https://nordicesmhub.github.io/climate-data-tutorial/fig/climate_data_types.png
---
name: datacategories-time-domain
width: 100%
---
Possible datasets by provenance category available for the past, present and future. Source: https://nordicesmhub.github.io/climate-data-tutorial/01-introduction/index.html
```

We briefly cover dataset levels and then go over each of these categories in turn and then look at how they relate to, and can interface with, each other.

###  Data Processing Levels

% See: https://www.earthdata.nasa.gov/learn/earth-observation-data-basics/data-processing-levels

TODO.

###  Observational data

TODO

#### Remote sensing e.g. satellites

TODO

#### Ground-based tools and networks

TODO

#### Weather stations/observatories

TODO

###  Model simulation data

TODO

###  Reanalysis data

% See: https://climate.copernicus.eu/courses/09-c3s-uls-data-resources-reanalysis/


TODO

###  Derived products data

TODO

### Interfacing between different dataset types

TODO

#### Interfacing between models and observations


***

## Data formats

TODO

***

## Data standards

TODO

***

## Data Analysis for Earth System Science

TODO

### Common statistics

TODO

### Reanalysis

TODO

### Climate metrics

TODO

### Detection and attribution

TODO

***

## Uncertainty in data

TODO

***

## Post-processing of data

TODO

***

## Accessing data

TODO

### Data portals

TODO

### Data catalogues

TODO

***

## References

```{bibliography}
```

