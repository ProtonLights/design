# Overview

## Definitions

- Channel
  - Actual DMX channel number.
  - Integer c, 0 <= c < 512.
- Output
  - Represents one logical DMX channel for an element.
  - Might be 1 channel in reality, but might also be 0 or 20.
- Element
  - Represents 1 fixture in a show.
  - Holds position, color, and outputs.
- DMX data
  - Linked to an element.
  - Indicates value between 0.0 and 1.0 for a given output at a given time.
- Layout
  - Collection of elements
  - Contains background color/image, some metadata.
- Sequence
  - 1 music file, 1 layout, and dmx data.
- Mapping
  - Linked to a layout.
  - Maps each output in layout to channels.


## High-level requirements

- Create and edit layouts.
  - Graphical editor for making and arranging new elements.
- Create and edit sequences.
  - Needs to sustain updates to layout or music file without affecting
    existing DMX data.
  - Need to visualize what sequence looks like digitally.
- Merge sequences automatically
  - Sequences must have same music and layout
  - Distribute sequences to others
    - Sub-sequences with sections of layout or time disabled.
- Create and edit mappings.
  - Graphical editor for mappings.
- All editors must run cross platform (Windows, Mac, Linux, BSD).
