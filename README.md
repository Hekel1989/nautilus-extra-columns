# Nautilus Extension: Nautilus Extra Columns

Expand Nautilus' columns with extra options like: tags, metadata, exif, quality information.

# Installation

Instalation can be selective, for eg: `make install-mediainfo` => `src/nec-mediainfo.py`

## Requirements & Dependiences
* mediainfo: [pymediainfo](https://github.com/sbraz/pymediainfo/)
* exif: [pyexiv2](https://launchpad.net/py3exiv2)
* pdf: [PyPDF2](https://mstamy2.github.com/PyPDF2)

To install all of the above on a Debian or Redhat based system, use the command below

```
if [ -f "/etc/debian_version" ]; then
 sudo apt install python3 python3-gi python3-pil gir1.2-nautilus-3.0 gir1.2-gexiv2-0.10 python3-nautilus python3-mutagen python3-pypdf2 python3-plumbum python3-exiv2 mediainfo
fi
if [ "$(grep -Ei 'fedora|redhat' /etc/*release)" ]; then
 sudo dnf install python3 python3-pillow python3-nautilus python3-mutagen python3-exiv2 python3-PyPDF2 python3-plumbum mediainfo
fi
```

## Install to local destination (home directory)
`git clone https://github.com/Hekel1989/nautilus-extra-columns.git`
`cd nautlius-nec`

``` bash
make install
```

## Install to global destination (system)

``` bash
make
sudo make install PREFIX=/usr
```

# Uninstalling

`sudo make install PREFIX=/usr`
