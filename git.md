## Git Commands

This document outlines essential Git commands for managing your version control.

### Initialization and Status

* **Initialize a new repository:**
`git init`
* **View the current status of your repository:**
`git status`

### Viewing History

* **View the complete commit history:**
`git log`
* **View the commit history with additional details:**
`git log --all --graph --decorate`
* **View the commit history in a single line format:**
`git log --all --graph --decorate --oneline`

### Branching and Merging

* **Move to a specific branch:**
`git checkout <branch_name>`
* **Create a new branch:**
`git checkout -b <branch_name>`
* **Set up a branch to track a remote branch:**
`git branch --set-upstream-to=<remote_branch> <local_branch>`
* **Pull changes from a remote branch:**
`git pull <remote> <local_branch>`
* **View differences between files:**
`git diff <file1> <file2>`

### Undoing and Reverting

* **Revert the last commit (including created files):**
`git revert HEAD~1`
* **Update the current branch:**
`git pull`

### Remote Management

* **Show remote branches:**
`git remote show`
* **Push changes to a remote branch (with tracking):**
`git push -u origin main`

### Undoing Changes

* **Revert the last commit (soft reset):**
`git reset --soft HEAD~1`
* **Add files to the staging area:**
`git add <filenames>`
* **Commit changes:**
`git commit -m "Your commit message"`
* **Force undo and delete unstaged files:**
`git stash save --keep-index --include-untracked`
`git stash drop`

* **Alternative way to undo changes (with amend):**
`git commit --amend -m "Your new commit message"`

### Cloning and Committing

* **Clone a specific branch from a remote repository:**
`git clone -b <branch_name> <remote_repo_url>`
* **Add all files and commit with a message:**
`git commit -a -m "Your commit message"`

### Rebasing

* **Rebase the current branch onto another branch:**
`git rebase <forwarded_branch>`
* **Interactive rebasing:**
`git rebase -i main`

### Deleting Commits

* **Delete the last commit:**
`git reset --hard HEAD~1`

----
* **create a add-commit command alias in git**
`git config --global alias.add-commit '!git add -A && git commit'`

### Other tips and tricks
- Suppose you have a branch pointing to a previous commit. In order to make the branch to point to the most recent commit, use the these commands:
  ```git
  git checkout <the branch>
  git reset --hard  <your most recent commit hash>
  ```
`git clone --recursive <YOUR_GIT> <FOLDER_NAME_YOU_WANT_TO_EXTRACT_INTO>`


```cmake
project(application)

cmake_minimum_required(VERSION 2.8.0)

find_package(VTK REQUIRED)
include(${VTK_USE_FILE})

find_package(Qt4 REQUIRED)
include(${QT_USE_FILE})

# Support for out-of-source build
INCLUDE_DIRECTORIES(
 ${CMAKE_CURRENT_BINARY_DIR}
 ${CMAKE_CURRENT_SOURCE_DIR}
)

set(SRC
   optionsDialog.h
   optionsDialog.cpp
   main.cpp
   mainwindow.h
   mainwindow.cpp
   application.qrc
)

set(MOC optionsDialog.h mainwindow.h)
set(UI optionsDialog.ui mainwindow.ui)
set(RCC application.qrc)

qt4_wrap_cpp(MOC_GENERATED ${MOC})
qt4_wrap_ui(UI_GENERATED ${UI})
qt4_add_resources(RCC_GENERATED ${RCC})

source_group("Form Files" FILES ${UI})
source_group("Resource Files" FILES ${RCC})
source_group("Generated Files" FILES ${MOC_GENERATED} ${UI_GENERATED} ${RCC_GENERATED})

add_executable(application
   ${SRC}
   ${MOC_GENERATED}
   ${UI_GENERATED}
   ${RCC_GENERATED}
)

target_link_libraries(application ${QT_LIBRARIES} QVTK) # QVTK is for VTK 5.x. For VTK 6, use ${VTK_LIBRARIES} instead
```

C:/Users/Asus/Projects/FirstVTK/qml;C:/Users/Asus/Projects/FirstVTK/build/Desktop_Qt_6_7_2_MSVC2019_64bit-Debug/imports;C:\Program Files (x86)\VTK\lib\qml\VTK.9.3