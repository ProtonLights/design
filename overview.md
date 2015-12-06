# Overview

## Definitions

- Sequence = 1 music file, 1 layout, some dmx data
- Layout = Some elements
- Element = Represents 1 fixture in a show. Holds position, color, and output shape data
- DMX data = Attached to an element. Indicates value between 0.0 and 1.0 for a given output
- Mapping =

## Top-level requirements

- Create and edit sequences.
    - Needs to sustain updates to layout without damage
- Merge sequences automatically
    - Sequences must have same music and layout
    - Disable certain elements