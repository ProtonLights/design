# Overview

## Definitions

- Sequence = 1 music file, 1 layout, some dmx data
- Layout = Collection of elements, background info
- Element = Represents 1 fixture in a show. Holds position, color, and output
  shape data.
- Output = Represents one logical DMX channel for an element.
- Channel = Actual DMX channel number. 0 <= Channel < 512.
- DMX data = Linked to an element within a sequence. Indicates value between 0.0
  and 1.0 for a given output at a given time.
- Mapping = Linked to a layout. Maps each output in layout to channels.


## Top-level requirements

- Create and edit sequences.
    - Needs to sustain updates to layout without damage
- Merge sequences automatically
    - Sequences must have same music and layout
    - Disable certain elements