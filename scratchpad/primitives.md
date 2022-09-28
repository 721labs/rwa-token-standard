This document is my initial thoughts on how to develop standard (ideal: universal adoption) primitives, what they should look like and why.

## Property as a layer cake

- Standards comprise a layer that others can build on top of
  - `[ [ Unique Asset ] [ Digital Representation ] [ Conflict Resolution] ]`
  - `[ [ Physical Records of Stewardship ] [ Digital Records of Stewardship ] [ Reconciliation ] ]`
  - `[ Legal Disputes => Validity Recognition by courts => case law ]` 
  - `[ Application layer adoption => larger market adoption ]`

## Layer 0: Representation

### 0.1: Unique, physical asset

- Unique Characteristics ("What")
  - How the assets non-fungibility is defined

#### Land

- **ToDo: What are all of the legal features of land definition?**
- Boundaries
  - Representation
    - Categorical Names: Geocoding Strategies, Location Encoding Systems
    - Example Implementations: GIS
  - Definition
    - Convex hull of a set of points
      - Edge, [Minimum Bounding Box](https://en.wikipedia.org/wiki/Minimum_bounding_box)
- Points
  - Arbitrarily precise resolutions
    - Different systems differ with respect to precision
  - Coordinate Systems
    - Latitude, Longitude
    - Open Location Code
      - Developed by Google, 2014
      - Derived from Lat, Lng so already exist everywhere
    - [Geohash](https://en.wikipedia.org/wiki/Geohash)
  - Partition Systems
    - aka [Discrete Global Grids](https://en.wikipedia.org/wiki/Discrete_global_grid)
    - Partition space into cells (convex hulls)
    - Implementations
      - Global Area Reference System
      - [Military Grid Reference System](https://en.wikipedia.org/wiki/Military_Grid_Reference_System)
      - [What3Words](https://what3words.com/clip.apples.leap)
        - Resolution: ~3m
        - Word-based encodings

### 0.2: Digital representation

- Given a set of geo-points, [calculate its convex hull](https://en.wikipedia.org/wiki/Convex_hull_algorithms) in a gas-efficient manner
  - On vs. off-chain
  - Continuous (dynamic via getter) vs. periodic
- UUID: university unique identifier of the hull i.e. a unique hash of the _what_.

### 0.3: Conflict Resolution

- Computing overlapping convex hulls

## Layer 1: Veracity

### 1.1: Representation

- Capturing updates to L0.1

### 1.2: Possession

- Multiple valid forms of possession (e.g. private ownership, public ownership, contested ownership)
  - linguistically: don't call it ownership => make as few assumptions here as possible
  - Open: enables creativity for new forms of ownership
- L1.2 exists on top of L0 (each is a discrete layer)
- who possesses of the asset?
  - provenance = chronologically ascending sorted list of stewardship structures

  #### 1.2.1: Physical records

  #### 1.2.2: Digital records

  #### 1.2.3: Reconciliation

  - Finding and resolving conflicts?
  - Finding:
    - Easiest but complex: use common standards
    - Use the already universal standards (e.g. Deeds & NLP)

## Layer 2: Robustness

### 2.1: Legal

### 2.2: Validity via Recognition (Case Test)

- Courts recognize the validity of the system via a legal test
- Establishment legal precedent (case law)

## Layer 3: Composability

- Why use it?
  - L2.2
    - to ensure their titles are legally clear of title disputes
    - "standards & database as the legal authority i.e. the final word as far as the law is concerned"

### 3.1: Protocol Layer

- Principal: develop standards to be "open" by default in order to allow their improvement and wider adoption
  - Openness pushes complexity up into the protocol implementations; conversely, standards should be simple.

### 3.2: Application Layer

- Adoption

### 3.3: Market

- Broad commercial adoption