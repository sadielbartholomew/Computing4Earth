# Grids, Coordinates and Projections


```{contents}
```

## Grids and coordinate systems

Ignoring local surface variations such as hills and mountains (see
{ref}`orography-section`), the
Earth is [still not a perfect sphere](https://oceanservice.noaa.gov/facts/earth-round.html).
Technically it is an oblate spheroid (an ellipsoid with two equal semi-diameters), a little wider in
the centre due to its rotation and subsequent centrifugal forces on it. However, for
the purposes of earth system modelling, it is generally treated as a sphere.

:::{figure} https://upload.wikimedia.org/wikipedia/commons/e/e6/Spheroids.svg
:label: fig-oblate-spheroid
:width: 80%

Schematic showing an 'oblate' (left) and a 'prolate' spheroid shape. Earth is an oblate spheroid
like on the left view except with the seminajor and semiminor axes being very close in size such
that it is much closer to a sphere than the more 'squashed' oblate spheroid in the schematic where
the two radii differ more.
:::

In order to pinpoint absolute and relative spatial locations on this sphere to which
Earth is approximated as in shape, a horizontal coordinate system is needed. Vertical levels can
then be created (if relevant), often by considering the space projected
upwards from some defined lowest vertical level of the coordinate system, often the Earth's
surface.

### Coordinate systems

A Geographic Coordinate System (GCS), or informally a coordinate system, defines the reference
surface (e.g. sphere or ellipsoid) and enables specification of locations on it by defining the
origin and orientation of coordinates on the reference surface.

In Earth Science, the GCS usually assumes Earth is a sphere and the coordinates are often
expressed as latitude and longitude.

```{note}
Alternative schemes do exist to describe the effective latitude and longitude coordinate, such
as geocodes, which are identifier schemes for locations - well-known examples are
[`Geohash`](https://en.wikipedia.org/wiki/Geohash) and
[`what3words`](https://what3words.com/about). However in Earth Science we usually use
latitude and longitude in degrees as a basis for specifying coordinates and location.
```

### Latitude and Longitude

Most coordinate systems utilise the concept of latitude and longitude,
imaginary lines that cross the Earth in north-south and east-west direction
relative to set zero points.

Both are measured in degrees, though for data we prefer to refer to the more specific units of
degrees east for longitude and degrees north for latitude:

* Longitude in degrees east measures position east (or west) of the Prime Meridian, an
imaginary north-south line (meridian means line of longitude) that passes from the
North to South Pole through Greenwich, London, UK. It is analagous
to (and encoded as) the x coordinate for the Earth system.
* Latitude in degrees north measures position north (or south) of the Equator, an imaginary
line (a parallel, i.e. line of latitude) halfway between the North and South Poles. It is analagous
to (and encoded as) the y coordinate for the Earth system.

Usually latitude is written as the first coordinate and longitude the second, to describe the
north-south position first and then the east-west position: `(latitude, longitude)` i.e.
`(y, x)` coordinates.

 {numref}`fig-latlon` illustrates varying degrees of latitude on the left and of longitude on the right:

:::{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Latitude_and_Longitude_of_the_Earth.svg/960px-Latitude_and_Longitude_of_the_Earth.svg.png
:label: fig-latlon
:width: 80%

Schematic illustrating latitude and longitude.
:::

```{tip}
Latitude lines are parallel circles which slice the Earth into wedges, like orange slices; whereas longitude lines are lines which converge at the poles, like those which form orange segments.

One way to help remember which is which between latitude and longitude is that **long**itude
lines (meridians) are all **equally long** i.e. the same length (unlike latitude lines i.e. parallels) because they all go from pole to pole.
```

```{note}
An interesting fact is that latitude is determined by nature, while longitude is determined
by convention. The the poles and the Equator exist because of the Earth's rotation, but the
location of zero degrees (east) longitude is arbitrary and was chosen by humans. It was
[chosen as the line passing through the Royal Observatory in Greenwich in 1884](https://en.wikipedia.org/wiki/Prime_meridian_(Greenwich))
because Greenwich was already widely used as a reference for navigation and maps.
```



### Grids

A grid system partitions the Earth or relevant area on it into discrete cells for numerical
computation.

```{tip}
The difference is somewhat subtle: while coordinate systems are frameworks for describing
locations, grids are frameworks for dividing space.
```

Some grids are based on a GCS, but others aren't. A notable basic example of a grid system which
is based on a GCS is the regular lat-lon grid, which uses latitude and longitude as the basis of
the grid.

```{figure} media/gcm_grid_globe_bom.png
---
name: gcm_grid_globe_bom
width: 80%
---
The Earth paritioned into discrete cells forming a grid system. Source: The Bureau of Meteorology (2003) https://www.bom.gov.au/info/GreenhouseEffectAndClimateChange.pdf.
```

### Grid cells

The discrete subdivisions of the Earth by the grid system, for example the 2D bounding
boxes formed by the hypothetical lines of latitude and longitude in a regular lat-lon grid, or
bounding 3D boxes formed by those plus set vertical levels, are called grid cells.

By splitting up the full Earth system into grid cells, the Earth can be modelled as a
collection of discrete areas or volumes (depending on whether the vertical dimension is
also considered). This facilitates calculations by providing fundamental computational units.

(grid-reso)=

### Grid resolution

The size of the grid cells  is called the *resolution*. The higher the resolution, the smaller
the grid cells and the more of them that cover the Earth, therefore the more computationally
expensive the model using the grid but the better it can distinguish detailed information
and capture processes that occur on smaller scales that are important to the overall
behaviour (see also {ref}`parameterisations`).





#### Horiztonal resolution

```{figure} https://www.carbonbrief.org/wp-content/uploads/2018/01/fig-1-4-1024x653.jpg
---
name: spatial-resolution
width: 80%
---
Examples of varying horizontal/spatial resolutions of grid, and the finer
{term}`topography` that it is possible
to capture with each, for a selection of climate models from the first four {term}`IPCC`
Assessment Reports, namely, in order of lowest to highest resolution: FAR (from 1990),
SAR (1995), TAR (2001) and AR4 (2007). Source: Figure 1.4 of {cite}`IPCC2007AR4`
(via a condensed version featured in
[a The Carbon Brief article](https://www.carbonbrief.org/qa-how-do-climate-models-work)).
```



#### Vertical resolution

TODO

### Grid categories: regular vs. irregular vs. unstructured (vs. other)

TODO

#### Structured (rectangular/Cartesian) grids

TODO

#### Curvilinear grids

TODO

#### Irregular grids

TODO

#### Unstructured grids and UGRID

TODO

#### Other grids

Some grids don't fit neatly into the classiifcation of (ir)regular or unstructured. Some important
examples in use in the earth sciences are as follows.

#### HEALPix

HEALPix (see {cite}`Gorski_2005`) stands for **H**ierarchical **E**qual **A**rea
iso**L**atitude **Pix**elation of a sphere. The basic idea involves
hierarchically tessellating the sphere into curvilinear quadrilaterals.
HEALPix was originally developed for
all-sky astronomical observations, particularly analyses
of the cosmic microwave background. However, it has come to be adopted in Earth system science due to various useful properties which guided its design, namely:

- every cell has identical area, simplifying statistical analyses;
- pixels can be recursively subdivided to increase resolution;
- cells lie on iso-latitude rings, enabling fast spherical harmonic transforms and zonal calculations;
- the indexing scheme makes neighbour searches and data access computationally efficient.

```{figure} https://irsa.ipac.caltech.edu/healpix/images/gorski_f1.jpg
---
name: healpix-resos
width: 80%
---
Orthographic view of the HEALPix partition of the sphere with octahedral symmetry. The shading illustrates how one cell becomes four as one descends the hierarchy of resolutions. Source: Figure 3 of {cite}`Gorski_2005`.
```

As alluded to in the second advantage point above, HEALPix grids are restricted to resolutions
that nest hierarchically, i.e. one cell at a given resolution always contains exactly four
whole cells at next higher resolution.  This means you can easily move between resolutions via
unweighted averaging/summing/broadcasting, rather than computationally expensive and
(to some extent) inaccurate regridding techniques.

HEALPix has a further advantage that the cells are completely defined by mathematical formula
(amount, shape, and location), so you don’t need to to store coordinates and bounds on
datasets since they can be deduced.

##### Defining HEALPix grids

Each defined hierarchical resolution is called a **refinement level $R$** and this
relates to the number of **pixels** i.e. partitions of the sphere. The
number of global pixels $N$ can be found from $R$ as follows:

$$
  N = 12 \times 4^{R}
$$

where the minimum R i.e. lowest resolution is 'level 0' i.e. $R=0$ with $N=12$
pixels. Interestingly, the practical maximum is level 29' i.e.  $R=29$ since for
$R \le 29$ all indexing schemes (see below) can be represented by
64-bit integers but at $R=30$ we have $N=12 \times 4^{30}$
which is $\approx 13.84$  quintillion ($\times 10^{18}$) which exceeds
$\approx 9.223$ quintillion, the largest integer representable with 64 bits.

```{note}
There is also another numbering scheme used to distinguish HEALPix grids
called the $N_{side}$ paramter which maps directly to  $R$ via:

$$
N_{side} = 2^{R}
$$

It represents the number of subdivisions along each edge of a base HEALPix pixel,
where the base pixel, one of the 12 quadrilateral regions into which the sphere
is initially divided before any refinement (to higher resolution) takes place.

However, $N_{side}$ is uniquely determined by the $R$ value so it is derived and
in these notes we refer to $R$ instead, because it is $R$ which must be specified in
CF-compliant metadata to encode a HEALPix grid, hence more appropriate
in the context of data and computing.
```

To define a particular HEALPix grid you also need to specify one of the four available
**indexing schemes** for labelling the pixels, which are, where 'consecutive pixels'
means consecutive in the data array:

- **ring**: sorts pixels along isolatitude rings from north to south, resulting in consecutive pixels
  that share a latitude;
- **nested**: sorts pixels along the Z-order curve within each of the 12 base level, resulting in geographic proximity for consecutive pixels;
- **nuqiq**: effectively concatenates nested indices from lower to the higher refinement levels, resulting in geographic proximity for consecutive pixels within a refinement level but not across different refinement levels;
- **zuniq**: sorts pixels of all  refinement levels along the Z-order curve resulting in geographic proximity for consecutive pixels, regardless of their refinement level.

```{figure} https://healpix.sourceforge.io/html/introf2.png
---
name: healpix-indexing-nested-ring
width: 80%
---
Illustration of the nested and ring indexing schemes, two of the four possible for
HEALPix grids, in a cylindrical projection for the level one grid i.e. $R=1$
(first and third panel) and the level two grid i.e. $R=2$ (second and fourth) with
the top two panels showing indexing by the ring scheme and the bottom two
panels the nested scheme. Source: https://healpix.sourceforge.io/, based off
a very similar figure from the paper {cite}`Gorski_2005`.
```

The latter two, **z/nuniq**, are designed so that you can store this field as a single 1D  array
with indices and each index uniquely defines the exact size and location of its cell, regardless
of the cell resolution. They differ in expected access pattern, where nuniq is 'breadth first' and
zuniq is 'depth first'.


##### Multi-resolution HEALPix grids

While a standard HEALPix grid uses a single refinement level across the
entire sphere, multi-resolution HEALPix grids (see {cite}`multi-res-healpix`)allow
different regions to be
represented at different resolutions. Areas requiring greater spatial detail
can therefore be refined independently, while more homogeneous regions
remain at a coarser resolution. This hierarchical representation can
substantially reduce storage requirements and computational cost without
sacrificing accuracy where it is most needed.

```{figure} https://ars.els-cdn.com/content/image/1-s2.0-S2405844017304966-gr8.jpg
---
name: multi-reso-healpix
width: 60%
---
An example multi-Resolution HEALPix grid showing six levels of cell resolution i.e.
refinement level for different locations, depicted in different colours. Source:
{cite}`multi-res-healpix`
```

Multi-resolution HEALPix can't be implemented with the same indexing
schemes as satndard HEALPix because they have effectively
effectively varying refinement level across the pixels. Therefore for
each pixel you need to know not only the index but the refinement level.
Instead, pixels are labelling according to **hierarchical indexing schemes**
 such as UNIQ which encode both the
refinement level and pixel index into a single integer, enabling pixels from
different resolutions to coexist within a single dataset.

Multi-resolution grids are particularly well suited to cloud-native geospatial
datasets, where adaptive spatial resolution can improve storage efficiency
and accelerate spatial queries.

% TODO add diagram of phenomena depicted on MRH grid as per presentation

#### Grid choice advantages and disadvantages summary

There are various types of grid system defined and used for studying or modelling
the Earth, because each has advantages (and motivations) and disadvantages. The typical use
cases along with pros and cons for some key grid systems are summarised below:


| Grid type | Example model/project | Diagram | Typical use | Main advantages | Main disadvantages |
|------------|------------|------------|------------|----------------|-------------------|
| Regular latitude–longitude | HadGEM3-GC (Met Office Hadley Centre) | *(Insert regular lat–lon grid figure)* | • Global atmosphere and climate models<br>• Reanalysis and observational products | • Conceptually simple<br>• Easy analysis and visualisation<br>• Structured indexing<br>• Mature numerical methods | • Polar singularities<br>• Non-uniform cell areas<br>• Restrictive polar time steps |
| Rotated latitude–longitude | Regional UM (Met Office) configurations, CORDEX (Coordinated Regional Climate Downscaling Experiment, World Climate Research Programme) domains | *(Insert rotated lat–lon grid figure)* | • Regional atmosphere models<br>• Regional climate models | • Mostly same benefits as regular lat–lon<br>• Pole moved outside domain so singularities less detrimental<br>• Efficient regional focus | • Same distortions as regular lat–lon<br>• Not globally uniform<br>• Less intuitive coordinates |
| Tripolar | NEMO (Nucleus for European Modelling of the Ocean, European consortium) | *(Insert tripolar grid figure)* | • Ocean models<br>• Sea-ice models | • No Arctic singularity<br>• Widely used in ocean modelling | • Distortion near artificial poles<br>• More complex geometry than regular lat–lon grid<br>• Limited atmospheric use |
| Cubed sphere | LFRic (Met Office) | *(Insert cubed-sphere grid figure)* | • Modern atmosphere models<br>• Coupled Earth system models | • No pole singularities<br>• Nearly uniform cell sizes<br>• Excellent scalability | • Face-edge treatment required<br>• More complex numerics and software infrastructure |
| Icosahedral | ICON (ICOsahedral Non-hydrostatic, DWD and MPI-M) | *(Insert icosahedral grid figure)* | • Modern atmosphere models | • Nearly uniform cell sizes<br>• Nearly isotropic mesh (resolution is similar in all directions)<br>• Excellent scalability | • Unstructured mesh complexity<br>• More complex diagnostics and post-processing |
| HEALPix (Hierarchical Equal Area isoLatitude Pixelisation) | Planck mission sky maps (astrophysics origin); increasingly used in Earth observation and geospatial analysis | ![](https://irsa.ipac.caltech.edu/healpix/images/gorski_f1.jpg) | • Astronomy<br>• Global geospatial datasets<br>• Remote sensing<br>• Spherical data analysis | • Equal-area cells<br>• Hierarchical refinement<br>• Efficient spatial indexing<br>• Well suited to global statistical analyses | • Cell shapes vary across the globe<br>• Less common in Earth system models<br>• Numerical methods less mature than for traditional model grids |
| Reduced Gaussian | ECMWF IFS (Integrated Forecasting System) | *(Insert Gaussian grid figure)* | • Global numerical weather prediction<br>• Spectral atmospheric models | • More uniform cells than regular lat–lon<br>• Efficient spectral transforms<br>• Structured indexing<br>• Operationally proven | • Still based on latitude circles<br>• Less uniform than cubed-sphere or icosahedral grids<br>• Scalability limited by latitude-based decomposition |

###  Vertical coodinates

TODO

#### Parametric and hybrid

TODO

#### Height vs. pressure

TODO

### Regridding

TODO

#### Interpolation methods

TODO

***

## Projections

TODO

### Map projections and why they are needed

TODO

### Distortions

TODO

### Types of projections

TODO

#### Projections commonly used in various applications

TODO

### Projection choice and application

TODO

#### For numerical modelling

TODO

#### Visulisation

TODO

#### Regional domain

TODO
