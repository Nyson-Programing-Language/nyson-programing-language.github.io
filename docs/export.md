## How to export normally
do `nyson "examples/Loading Bar.nys" -compile` you will get a file called `nysonProgram` in your current directory and you can use that

## Export to AppImage
### Dependency
- [AppImage Tools](https://appimage.github.io/appimagetool/)

### Steps

1. make a directory called something like `{name}.AppDir`
2. run `cd {name}.AppDir`
3. make a file called `AppRun` with the code 
```
#!/bin/sh

cd "$(dirname "$0")"
exec ./nysonProgram
```
4. make a file called `{name}.desktop` with the code
```
[Desktop Entry]
Name={name}
Exec=nysonProgram
Icon=Logo
Type=Application
Categories={categories example "Utility"}
```
5. make a image called `Logo.png` with the width and height of 256 (can also take any image and run `convert {image path} -resize 256x256 Logo.png`)
6. compile your program like from [here](https://nyson-programing-language.github.io/#/export?id=how-to-export-normally) and copy the nysonProgram to this directory
7. run `chmod +x AppRun *.desktop nysonProgram`
8. run `cd ..`
9. then run `{AppImage Tools appimage location} {name}.AppDir`
