# Grids and Projections


```{contents}
```

## Grids

Ignoring local surface variations (mountains etc. - see orography), the
Earth is still not a perfect sphere. Technically it is an oblate spheroid, a little wider in
the centre due to its rotation and subsequent centrifugal forces on it. However, for
the purposes of earth system modelling, it is generally treated as a sphere.

<insert diagram of Earth shape>

In order to understand absolute and relative spatial locations, a grid system is
needed - it pinpoints locations on and abovethe sphere to which Earth is approximated
as in shape. Vertical levels can then be created by considering the cells projected
upwards from the zero point of the grid (often the Earth's surface) - or in rare
cases may be defined differently.

By splitting up the Earth into small cells formed by the grid
sudivisions, we can TODO

The majority of grid systems utilise the concept of latitude and longitude, imaginary
lines that divide the Earth into sections - together they form there own grid, the
regular latitude-longitude grid, which will be covered below.

Besides the regular latitude-longitude grid,
there are various types of grid system defined and used for studying or modelling
the Earth, because each has advantages (and motivations) and disadvantages.
Some major examples are covered in a dedicated section below.


### Latitude and Longitude

Latitude is TODO . Longitude is TODO

Both are measured in degrees, though in ESM we use more specific units of
degrees east for longitude and degrees west for latitude.

<insert diagram showing lat and lon>



TODO

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

#### Coordinate systems

TODO

#### Grid choice advantages and disadvantages

TODO

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
