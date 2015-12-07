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
  - Contains data on position, color, and outputs.
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


## Sequence Editor requirements

- Create and edit layouts.
  - Graphical editor for making and arranging new elements.
- Create and edit sequences.
  - Needs to sustain updates to layout or music file without affecting
    existing DMX data.
  - Need to visualize what sequence looks like digitally.
- Merge sequences automatically
  - Sequences must have same music and layout
  - Distribute sequences to others
    - Create child sequences with sections of layout or time disabled.
- Create and edit mappings.
  - Graphical editor for mappings.
- All editors
  - Must run cross platform (Windows, Mac, Linux, optionally other Unixes).
  - Prevent the user from making simple errors, including but not limited to
    - Multiple outputs to one channel.
    - Splitting sequences that overlap.
    - Deleting DMX data unintentionally.


## DMX Execution requirements

- Send DMX data over Enttec USB DMX Pro protocol.
- Output DMX data and play music simultaneously.
  - Music and DMX must always be within 50 ms of each other.
  - Adjustable delay of either music or DMX to keep in time.
- Play, pause, and seek into a sequence.
- Queue multiple sequences into an ordered playlist.
  - Play sequences in order with appropriate timing and fades in/out.
  - Play arbitrary sequences in a playlist.
- Execute simple commands
  - All on/off.
  - Turn on 1 channel
    - Turn on block of channels.
  - Turn on 1 output
    - Turn on block of outputs.
  - Turn on 1 element.
    - Turn on multiple elements.
  - Turn on arbitrary set of channels, outputs, and elements.
- Stability
  - Ensure only one sequence executes at a time.
  - Tolerate loss of output port.
- Use a simple and easily understood storage format.
