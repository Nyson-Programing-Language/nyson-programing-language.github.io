## How to export normaly
do `nyson "examples/Loading Bar.nys" -compile` you will get a file called `nysonProgram` in your current directory and you can use that

## Export to AppImage
### Dependency
- [AppImage Tools](https://appimage.github.io/appimagetool/)

### Steps

1. make a directory called something like `{name}.AppImage`
2. run `cd {name}.AppImage`
3. make a file called `AppRun` with the code 
```
#!/bin/sh

cd "$(dirname "$0")"
exec ./nysonProgram
```
3. make a file called `{name}.desktop` with the code
```
[Desktop Entry]
Name={name}
Exec=nysonProgram
Icon=Logo
Type=Application
Categories={categories example "Utility"}
```
4. make a image called `Logo.png` with the width and height of 256 (can also take any image and run `convert {image path} -resize 256x256 Logo.png`)
5. compile your program like from [here](https://nyson-programing-language.github.io/#/export?id=how-to-export-normaly) and copy the nysonProgram to this directory
6. run `chmod +x AppRun *.desktop nysonProgram`
7. run `cd ..`
8. then run `{AppImage Tools appimage location} {name}.AppDir`
