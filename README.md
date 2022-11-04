# Nautilus Extension: Nautilus Extra Columns

GNOME Files has Grid View and List views for browsing your files and folders. Whilst GNOME Files minimalism is visually appealing, it can be limiting, especially when compared to something like Windows File Explorer or KDE Plasma Dolphin.
The List View by default is limited to a few category columns. This extension adds extra columns like image EXIF data, audio tags, and .pdf metadata.
This could potentially be expanded further with extra Python libraries, something I might decide to experiment with if I need more columns :)

# Installation

Installation can be narowed down to just the required categories; For example, if you wish to install just the mediainfo category:

 `make install-mediainfo` => this will install just the `src/nec-mediainfo.py` extension, rather than the whole content of `src`

## Requirements & Dependencies
* make
* mediainfo: [pymediainfo](https://github.com/sbraz/pymediainfo/)
* exif: [pyexiv2](https://launchpad.net/py3exiv2)
* pdf: [PyPDF2](https://mstamy2.github.com/PyPDF2)

To install all of the above on a Debian or Redhat based system, use the command below

```
if [ -f "/etc/debian_version" ]; then
 sudo apt install make python3 python3-gi python3-pil gir1.2-nautilus-3.0 gir1.2-gexiv2-0.10 python3-nautilus python3-mutagen python3-pypdf2 python3-plumbum python3-exiv2 mediainfo
fi
if [ "$(grep -Ei 'fedora|redhat' /etc/*release)" ]; then
 sudo dnf install make python3 python3-pillow python3-nautilus python3-mutagen python3-exiv2 python3-PyPDF2 python3-plumbum mediainfo
fi
```


## Install to global destination (system)

To install the extension, clone the GitHub repository through your terminal:

``` bash
git clone https://github.com/Hekel1989/nautilus-extra-columns.git
```

Navigate to the repository’s folder:

``` bash
cd nautlius-nec
```
Use make to install the extension:

``` bash
sudo make install PREFIX=/usr
```

Restart GNOME Files/Nautilus for the changes to take effect:

```
$ nautilus -q
```

If that doesn’t work, then kill the Nautilus process:

```
$ sudo killall nautilus

```

## Install to local destination (home directory)

Follow the exact same procedure as above, but rather than running 

``` bash
sudo make install PREFIX=/usr
```

run this instead


``` bash
make install
```

To use Nautilus Extra Columns:

- On the GNOME Files top bar, click the **list/grid view** button to toggle the list view on a folder.
- Click the **View options** button next to the list/grid view button.
- Click **Visible Columns**.
- Toggle the extra columns added by the extension.

You can also right-click the row of column categories on a folder with list view to find and use the extra columns.

# Uninstalling

To uninstall the extension, navigate to the git folder and run uninstall as below
``` bash
sudo make uninstall PREFIX=/usr
```
