# _design_files

This repository stores the design files for all custom-made mechanical and electronic parts used in the lab.  
It is mirrored to the shared folder at:  
`/mnt/ceph/_design_files`

## Quick Start

- **Looking for a specific design?**
  - See the summary table below to find which folder contains the files you need.
  - Each major folder contains a README or index to help you navigate subfolders and file types.
- **Cloning the repository?**
  - Use `git clone --recurse-submodules` to get all submodules (see below for details).
- **Need to open a file?**
  - See folder READMEs for recommended software for each file type (e.g., Autodesk Inventor for `.ipt`, Eagle for `.sch`/`.brd`).

## Repository Structure Summary

| Folder                | Description                              | Main File Types      | Questions? Ask:          |
|-----------------------|------------------------------------------|----------------------|--------------------------|
| rat_behav_rig         | Rat behavioral rig CAD & docs            | .ipt, .stl, .pdf     | Viktor, Dammy, Lillianne |
| mouse-box             | Mouse behavioral box designs             | .ipt, .stl, .pdf     | Dammy, Quentin           |
| Repix_CAD_files       | Neuropixels implant design files         | .step, .stl          | Viktor, Elena            |
| np_calibration_files  | Neuropixels probe calibration data       | .csv                 | Viktor                   |
| Edmunds_designs       | Submodule: Edmund Chong's designs        | .ipt, .stl           | Edmund                   |

## Folder Structure

```
.
├── Edmunds_designs      # Submodule: Edmund Chong's mechanical designs
├── Repix_CAD_files      # Design files for Neuropixels implants     
├── mouse-box            # Design files for the mouse behavioral box
├── np_calibration_files # Neuropixels configuration files
├── rat_behav_rig        # Design files for the rat behavioral rig   
└── README.md
```

## External Design Repositories (Git Submodules)

Some folders in this repository are **Git submodules**—they link to external repositories maintained by individual lab members or collaborators.  
This structure allows each contributor to manage their own designs independently while keeping everything accessible in one place.

### Example: `Edmunds_designs`

- Maintained by: **Edmund Chong**
- Source repo: [edmundchong/Inventor](https://github.com/edmundchong/Inventor)
- Contains: Inventor files for various lab components

## About `.gitmodules`

The `.gitmodules` file tracks all submodules in this repository. It records the path and URL for each submodule, ensuring that everyone who clones the repository can initialize and update submodules easily.  
**Keep this file as long as you use submodules.** If you remove all submodules, you can safely delete `.gitmodules`.

## Cloning This Repository (with Submodules)

### Enabling Auto-Sync for Submodules (Git Hook)

To keep submodules like `Edmunds_designs` automatically in sync after pulling updates, this repository includes a Git hook stored in `.githooks/`.

After cloning, run:

```bash
./setup_hooks.sh
```

This configures Git to use the tracked hook, which:

- Automatically fetches and updates submodules after each `git pull`
- Commits and pushes the updated submodule pointer (if needed)

You only need to run this once per machine.

**Advanced:** You can customize or add your own hooks in the `.githooks/` directory if you want to automate other Git actions.

### Cloning with Submodules

To ensure you clone all linked submodules:

```bash
git clone --recurse-submodules https://github.com/akramilab/_design_files.git
```

If you've already cloned the repo without submodules:

```bash
git submodule update --init --recursive
```

### Keeping Submodules Up to Date Manually

To manually update a submodule (e.g., Edmund's):

```bash
cd Edmunds_designs
git pull origin main  # or the appropriate branch
cd ..
git add Edmunds_designs
git commit -m "Update Edmunds_designs submodule"
git push
```

Repeat for other submodules as needed.

### Notes

- Only maintainers of a submodule's source repo should make edits inside those folders.
- To contribute to a submodule, fork it or contact its maintainer.
- To **add a new submodule**, please contact the main repository maintainer.
