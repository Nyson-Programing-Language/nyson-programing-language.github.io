## Dependencies

#### Required

- [Rust](https://www.rust-lang.org/tools/install)
- [Git](https://git-scm.com/downloads)
- Curl (most os should have it but if you dont search up how to get it with your os)

#### Optional

- [VLC](https://www.videolan.org/vlc/) (for audio)

## --------------------

## Self compile
```shell
git clone https://github.com/Nyson-Programing-Language/nyson-programming-language.git
cd nyson
cargo build --release
cd target/release
```

it will be called Nyson

## Linux or Mac
```shell
curl "https://raw.githubusercontent.com/Nyson-Programing-Language/nyson-programming-language/main/startup.sh" | sh
```

## Windows
(have to run in cmd)
with git & cargo:
```
cd ~
git clone https://github.com/Nyson-Programing-Language/nyson.git
cd nyson
cargo build --release
```
to compile in rust simply run cargo run in code dir as so:
``cargo run {path of nys file to run}``

to compile anywhere add "C:\Users\%username%\Nyson\target\release" to PATH and run as so:
``nyson {path of nys file to run}``

with cURL:
```shell
curl "https://raw.githubusercontent.com/Nyson-Programing-Language/nyson-programming-language/main/startup.bat" -o startup.bat && .\startup.bat && del .\startup.bat
```

## IF YOU GET A ERROR TALKING ABOUT LINX.EXE READ THIS
so if you get a error looking like this
\
![error](https://i.imgur.com/8f8OQYb.png)
\
you are not alone to fix this you need [Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) once you go to the page it will download visual studio and once you open the installer you need to have
\
![Desktop development with C++](https://i.imgur.com/oRs1bJa.png)
\
selected then click install then once it is done close the installer and redo the install.
