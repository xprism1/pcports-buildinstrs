# pokeemerald_pc

Build instructions for the PC port of `pokeemerald`, in WSL (Ubuntu 18.04 LTS).

Notes:
- This is still a WIP and sound support has yet to be added.

## 1. Installing build dependencies

```
sudo apt install mingw-w64 libpng-dev
```

## 2. Building tools

```
git clone https://github.com/Sierraffinity/pokeemerald.git --branch pc-port --single-branch
cd pokeemerald
chmod +x build_tools.sh
./build_tools.sh
```

## 3. Building PC port
```
wget <insert link>
```
Extract `SDL2-devel-2.0.12-mingw.tar/SDL2-2.0.12/i686-w64-mingw32` to `pokeemerald/SDL2-2.0.12`

Open `pokeemerald/Makefile_pc`, replace the path specified in `SDL_DIR :=` to the path to your SDL2-2.0.12 folder (that you extracted in the previous step).

Now run `make -f Makefile_pc`

Built executable should be located in `pokeemerald/pokeemerald.exe`. If it complains about missing SDL2.dll upon launching, copy `pokeemerald/SDL2-2.0.12/bin/SDL2.dll` to `pokeemerald/` (i.e. place `SDL2.dll` next to the .exe)