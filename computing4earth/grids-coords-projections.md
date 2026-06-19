# Grids, Coordinates and Projections


```{contents}
:local:
```

## Grids and coordinate systems

Ignoring local surface variations such as hills and mountains (see orography), the
Earth is still not a perfect sphere. Technically it is an oblate spheroid, a little wider in
the centre due to its rotation and subsequent centrifugal forces on it. However, for
the purposes of earth system modelling, it is generally treated as a sphere.

<insert diagram of Earth shape>

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

```{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Latitude_and_Longitude_of_the_Earth.svg/960px-Latitude_and_Longitude_of_the_Earth.svg.png?_=20250207114002
---
name: fig-latlon
width: 80%
---
Schematic illustrating latitude and longitude. Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Latitude_and_Longitude_of_the_Earth.svg#filelinks).
```

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

A grid system partitions the Earth or relevant area on it into cells for numerical computation.

```{tip}
The difference is somewhat subtle: while coordinate systems are frameworks for describing
locations, grids are frameworks for dividing space.
```

Some grids are based on a GCS, but others aren't. A notable basic example of a grid system which
is based on a GCS is the regular lat-lon grid, which uses latitude and longitude as the basis of
the grid.

### Grid cells

The discrete subdivisions of the Earth by the grid system, for example the 2D bounding
boxes formed by the hypothetical lines of latitude and longitude in a regular lat-lon grid, or
bounding 3D boxes formed by those plus set vertical levels, are called grid cells.

By splitting up the full Earth system into grid cells, the Earth can be modelled as a
collection of discrete areas or volumes (depending on whether the vertical dimension is
also considered). This facilitates calculations by providing fundamental computational units.

### Grid resolution

TODO

#### Horiztonal resolution

TODO

#### Vertical resolution

TODO

### Regular vs. irregular vs.unstructured

TODO

#### Structured (rectangular/Cartesian) grids

TODO

#### Curvilinear grids

TODO

#### Irregular grids

TODO

#### Unstructured grids and UGRID

TODO

#### Grid choice advantages and disadvantages

There are various types of grid system defined and used for studying or modelling
the Earth, because each has advantages (and motivations) and disadvantages. The typical use
cases along with pros and cons for some key grid systems are summarised below:


| Grid type | Example model/project | Diagram | Typical use | Main advantages | Main disadvantages |
|------------|------------|------------|------------|----------------|-------------------|
| Regular latitude–longitude | HadGEM3-GC (Met Office Hadley Centre) | *(Insert regular lat–lon grid figure)* | • Global atmosphere and climate models<br>•  Analysis products | • Conceptually simple<br>• Easy analysis and visualisation<br>• Structured indexing<br>• Mature numerical methods | • Polar singularities<br>• Non-uniform cell areas<br>• Restrictive polar time steps |
| Rotated latitude–longitude | Regional UM (Met Office) configurations, CORDEX (Coordinated Regional Climate Downscaling Experiment, World Climate Research Programme) domains | *(Insert rotated lat–lon grid figure)* | Regional atmosphere and climate models | • Mostly same benefits as regular lat–lon <br>• Pole moved outside domain so singularities less detrimental<br> • Efficient regional focus | • Same distortions as regular lat–lon <br>• Not globally uniform<br>• Less intuitive coordinates |
| Tripolar | NEMO (Nucleus for European Modelling of the Ocean, European consortium) | *(Insert tripolar grid figure)* | Ocean and sea-ice models | • No Arctic singularity<br>• Widely used in ocean modelling | • (Distortion near) artificial poles<br>• More complex geometry than regular lat-lon grid<br>• Limited atmospheric use |
| Cubed sphere | LFRic (Met Office) |*(Insert cubed-sphere grid figure)*| Modern atmosphere and coupled models | • No pole singularities<br>• Nearly uniform cell sizes<br>• Excellent scalability  | Face-edge treatment required<br>• More complex numerics and software infrastructure |
| Icosahedral | ICON (ICOsahedral Non-hydrostatic, DWD and MPI-M) | *(Insert icosahedral grid figure)* | Modern atmosphere models | • Nearly uniform cell sizes<br>• Isotropic mesh: resolution is similar in all directions<br>• Excellent scalability  | • Unstructured mesh complexity<br>• More complex diagnostics and post-processing |
| HEALPix (Hierarchical Equal Area isoLatitude Pixelisation) | Planck mission sky maps (astrophysics origin); increasingly used in Earth observation and geospatial analysis| *(Insert HEALPix grid figure)* | Astronomy; global geospatial datasets; remote sensing; spherical data analysis | • Equal-area cells<br>• Hierarchical refinement<br>• Efficient spatial indexing<br>• Well suited to global statistical analyses | • Cell shapes vary across the globe<br>• Less common in Earth system models<br>• Numerical methods less mature than for traditional model grids |
| Reduced Gaussian | ECMWF IFS (Integrated Forecasting System) | *(Insert Gaussian grid figure)* | Global numerical weather prediction; spectral atmospheric models | • More uniform cells than regular lat–lon<br>• Efficient spectral transforms<br>• Structured indexing<br>• Operationally proven | • Still based on latitude circles<br>• Less uniform than cubed-sphere or icosahedral grids<br>• Scalability limited by latitude-based decomposition |


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
