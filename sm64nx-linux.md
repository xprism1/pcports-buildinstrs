# sm64nx

Build instructions for `sm64nx`, in Arch Linux.

## 1. Installing build dependencies
```
pip3 install pillow zstandard tqdm xxhash
sudo pacman -S audiofile glfw-x11
```

## 2. Building tools
`git clone https://github.com/teamsalta/sm64nx.git`

Copy a SM64 US ROM to `sm64nx/`, then

```
cd sm64nx/tools
make
```

## 3. Building pak file
```
cd ../import
python extract_assets.py
python ../scripts/pak.py --source . --output '../romfs/!!base.pak'
```

Ignore any `could not get hash` messages, just make sure it packed 1163 files.

## 4. Building PC port
```
cd ..
make
```
