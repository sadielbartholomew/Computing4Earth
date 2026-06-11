# Metadata

TODO

```{contents}
:local:
```

## Metadata (in general)

Metadata is data that describes other data. In general, it provides contextual information that
summarises given data to make it easier to identify it, to search for it, and to manage and use it.
For example, in a data archive or catalog, metadata provies an overview of what data is available
to form an inventory, to organise the data, and to enable users to filter and search through it.

```{tip}
A good way to understand metadata and its importance is to think of a library of books. The
metadata includes such core informatxion as the book title, author(s), and classification by
subject matter or theme (guiding what section or shelf it gets placed on). Imagine trying to
locate a given book or organise them without carefully labelled metadata - we would have to
consult the pages of text individually each time.

And for array-based data, comparing without metadata would be even more of a challenge
because it would require consulting raw numbers (often in binary form so 0s and 1s only!) and
trying to interpret these without any context.
```

## Metadata in Earth Science

In earth science, metadata is especially important because there are myriad sources and forms of
data: for example, datasets can originate from observations or from computer models, and we must
be careful to detail the details of e.g. remote sensing algorithms etc. in the former case or of the
simulation and initial conditions etc. for the latter case.

***

### Types of metadata

Metadata can be classified in different ways. A classification that is particularly useful for Earth science applications is the **NDG metadata taxonomy** described by Lawrence et al. (2008) (https://doi.org/10.1098/rsta.2008.0237). The taxonomy centres on five categories:

| Category                       | Description                                                                                                             |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| **A — Archive**                | Metadata that describes the syntax and semantics (e.g. parameter descriptions) of the data objects themselves.          |
| **B — Browse**                 | Metadata that supports understanding the context of data and choosing between similar datasets.                         |
| **C — Character and Citation** | Metadata that includes citations of the data itself, and post-fact assertions regarding the quality of the data.        |
| **D — Discovery**              | A subset of the browse and archive metadata selected to aid finding data for evaluation, visualisation, and other uses. |
| **E — Extra**                  | Core discipline-specific or instrument-specific metadata.                                                               |

As illustrated by the following:

```{figure} media/ndg-metadata-taxonomy.jpeg
---
width: 80%
name: ndg-metadata-taxonomy
alt: NDG metadata taxonomy from Lawrence et al. (2008)
---
The NDG metadata taxonomy. Source: Lawrence et al. (2008).
```


### FAIR Principles

TODO

***

## Metadata standards

TODO

### COARDS Conventions

TODO

### CF Conventions

TODO

#### CMOR

TODO

### Technicalities

TODO

#### Data Model

TODO

#### Core terminology and concepts

TODO

#### Standard Names

TODO

***
