#### 1. To update an existing clone
```bash
cd aseprite
git pull
git submodule update --init --recursive
```
#### 2. VS Code Markdown file preview
`cmd + shft + v`

#### 3. Dependencies(macOS)
CMake, Skia(2D Graphic library), Ninja

#### 4. About PATH
It will be overloaded if possible. Decide whichi version to use and be careful about PWD, comparing with the absolute directory.

#### 5. About System dir
`/Applications`: System direction
`~/Applications`:User direction

#### 6. About icons in macOS
The suffix of `.ico` only works well in Windows. Use `.icns` instead in the macOS.
