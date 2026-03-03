### March.1st
#### 1. Import Grass image into Godot
- Export as Sprite Sheet and DON'T forget to use the Tailset selection.
- Use TailMapLayer->New Tailset to import PNG image.
- Change the tail size before importing.
- Select the TailMapLayer and put tails as you want.

#### 2. Parent node and child node
- WARNING: CharaterBody2D must be the parent node since all of the scripts will be put here.
- Sprite2D is a type of texture.
- Be careful about API references since GoScript is based on C++, where the order of parameters matters most.

#### 3. About Aseprite
- Using rotation to make duplications is effective
- Use shortcut "M" to select the region and manipulate it.

### Congras on running the MVP first!!!!

### March.2nd
#### 1. Terminal and Finder
- Use `open .` in terminal to open Finder.
- Drag the file into terminal will provide its absolute path.

#### 2. Virtual Disk Refelction
- `Ctrl + X` cut the files
- Open `cmd` with the Administrator rights
- Use command 
```bash
  mklink /j "[Origin path]" "[Goal path]"
```
- *Attention: Must cut the whole file instead of everything below*

#### 3. About Setup of Anaconda
- Register Anaconda3 as the system Python 3.13. If unstall Anaconda, remember to clear all PATH contents.

### 4. Command on Conda
- Create the env
```bash
 conda env create -n [env_name] [Python=3.1x]
```
- Exit
```bash
 conda deactivate
```
- Remove env
```bash
 conda env remove -n [env_name]
```
- Activate env
```bash
 conda activate comfyui
```

#### 5. Differences between venv and conda
- venv share the global Python version, while conda can use different ones.
- conda can optimize space usage.
- remove venv? delete the whole file.

#### 6. Shortcuts in terminal
- *Terminal and PowerShell*
- `Ctrl + U` / `ESC` Clear the row
- `[Empty]` / `Ctrl + Home` Clear contents before the cursor
- `Ctrl + K` / `Ctrl + End` Clear contents after the cursor
- `Ctrl + W` / `Ctrl + Backspace` Clear a word before the cursor

#### 7. Freeze requirements.txt
- Export total dependencies
```bash
conda env export --no-builds > environment.yml
```
