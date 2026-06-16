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

Most coordinate systems  utilise the concept of latitude and longitude,
imaginary lines that cross the Earth in north-south and east-west direction
relative to set zero points.

Both are measured in degrees, though in ESM we use more specific units of
degrees east for longitude and degrees west for latitude.

Latitude measures position north or south of the Equator, an imaginary line (a parallel,
i.e. line of latitude) halfway between the North and South Poles.

Longitude measures position east or west of the Prime Meridian, an
imaginary north-south line (meridian means line of longitude) that passes from the
North to South Pole through Greenwich, London, UK.

<insert diagram(s) showing lat and lon>

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
| Regular latitude–longitude | HadGEM3-GC (Met Office Hadley Centre) | *(Insert lat–lon grid figure)* | • Global atmosphere and climate models<br>•  Analysis products | • Conceptually simple<br>• Easy analysis and visualisation<br>• Structured indexing<br>• Mature numerical methods | • Polar singularities<br>• Non-uniform cell areas<br>• Restrictive polar time steps |
| Rotated latitude–longitude | Regional UM (Met Office) configurations, CORDEX (Coordinated Regional Climate Downscaling Experiment, World Climate Research Programme) domains | *(Insert rotated lat–lon figure)* | Regional atmosphere and climate models | *(Insert dis/advantages)*  | *(Insert dis/advantages)* |
| Tripolar | NEMO (Nucleus for European Modelling of the Ocean, European consortium) | *(Insert tripolar grid figure)* | Ocean and sea-ice models | • No Arctic singularity<br>• Widely used in ocean modelling | • (Distortion near) artificial poles<br>• More complex geometry than regular lat-lon grid<br>• Limited atmospheric use |
| Cubed sphere | LFRic (Met Office) | *(Insert cubed-sphere figure)* | Modern atmosphere and coupled models | *(Insert dis/advantages)*  | *(Insert dis/advantages)* |
| Icosahedral | ICON (ICOsahedral Non-hydrostatic, DWD and MPI-M) | *(Insert icosahedral grid figure)* | Modern atmosphere models | *(Insert dis/advantages)*  | *(Insert dis/advantages)* |

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
