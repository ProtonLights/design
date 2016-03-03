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
their branch locally. When connected, the user branches will rebase onto master, then push to onto master. 

CLI should be able to

- Get list of editable files for a given user
- Identify user by ssh key (public key in repo)
- Init empty project
- Init a sequence
- (Re-)Section a sequence
  - On init, section as section1.
    - Number each section, and don't delete.
    - Use patch to copy changes.
  - Use git --find-renames=100%?
- Add user from public key
- Give permission to user to
  - edit sequence/section
  - update metadata
  - edit permissions
  - edit show




