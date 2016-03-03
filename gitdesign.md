# Operations

- Update sequence global data
  - Layout
  - Boundaries of sections
  - Music file
  - Sequence length
  - (Re)Sectioning a sequence
- Merge changes to sequence metadata
- Update section
- Merge changes to the same section (optional?)
- Merge changes to a different section
- Add new sequence
- Delete sequence (optional?)
- Update permissions
  - Layout
  - Sequence metadata
  - Sequence section
- Merge changes to permissions

# Model

The canonical copy is stored on the master branch on the server. Each user will
have their own branch on the server. When working, each save will commit to
their branch locally. When connected