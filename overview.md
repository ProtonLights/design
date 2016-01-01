# Overview

## Definitions

TODO: Fixtures

- Channel
  - Actual DMX channel number and universe.
  - Integer u, 0 <= u
  - Integer c, 0 <= c < 512. But some things can go over 512.
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
- Command
  - Represents an arbitrary set of DMX outputs, unattached to music.
  - Is an enumeration:
    - All channels to a value.
    - All channels periodically fade on/off.
    - 1 channel to a value.
    - Continuously run a set of commands.
- Playlist
  - An ordered list of sequences.
- Show
  - 1 layout, 1 mapping, 1 playlist.
  - Information on what to do between songs and before/after the show.
    - How to fade in and out.
    - Whether to wait, run commands, or continue.


## Sequence Editor requirements

swap channels
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
  - Use simple and easily understood storage format for files.
- Most work can be done offline.


## Show Execution requirements

- Send DMX data over Enttec USB DMX Pro protocol.
- Output DMX data and play music simultaneously.
  - Music and DMX must always be within 50 ms of each other.
  - Adjustable delay of either music or DMX to keep in time.
- Play, pause, and seek into a sequence.
- Play sequences in order with appropriate timing and fades in/out.
  - Play arbitrary sequences in a playlist.
- Execute commands.
- Stability
  - Ensure only one sequence or command executes at a time.
  - Tolerate loss of output port.
- Use a simple and easily understood storage format for binary data storage.
