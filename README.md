# _design_files

This repository stores the design files for all custom-made mechanical and electronic parts used in the lab.  
It is mirrored to the shared folder at:  
`/mnt/ceph/_design_files`



## 📁 Folder Structure

```
.
├── Edmunds\_designs     # Submodule: Edmund Chong’s mechanical designs
├── mouse-box           # Design files for the mouse behavioral box
├── rat\_behav\_rig       # Design files for the rat behavioral rig
└── README.md
```


## 🔗 External Design Repositories (Git Submodules)

Some folders in this repository are **Git submodules**—they link to external repositories maintained by individual lab members or collaborators.  
This structure allows each contributor to manage their own designs independently while keeping everything accessible in one place.

### 🔹 Example: `Edmunds_designs`
- Maintained by: **Edmund Chong**
- Source repo: [edmundchong/Inventor](https://github.com/edmundchong/Inventor)
- Contains: Inventor files for various lab components


## 🛠 Cloning This Repository (with Submodules)

To ensure you clone all linked submodules:

```bash
git clone --recurse-submodules https://github.com/akramilab/_design_files.git
````

If you already cloned the repo without `--recurse-submodules`, run:

```bash
git submodule update --init --recursive
```


## 🔄 Keeping Submodules Up to Date

To update a submodule (e.g., Edmund’s):

```bash
cd Edmunds_designs
git pull origin main  # or the appropriate branch
cd ..
git add Edmunds_designs
git commit -m "Update Edmunds_designs submodule"
```

Repeat for other submodules as needed.


## 📝 Notes

* Only maintainers of a submodule's source repo should make edits within those folders.
* If you'd like to contribute to a submodule, consider forking it or contacting the maintainer.
* If you want to **add a new design folder as a submodule**, contact the repository maintainer so it can be added properly.
