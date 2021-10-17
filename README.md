# NAME

bingdaily - Download the daily Bing wallpaper and save it to a given directory.


# SYNOPSIS

**bingdaily** [ **-p** _directory_ ] [ **-m** _market_ ] [ **-d** _day_ ] [ **-r** _resolution_ ] [ **-s** _size_ ] [ **-y** ] [ **-h** ]


# DESCRIPTION

**bingdaily** downloads the current daily wallpaper offered by [Bing](https://www.bing.com/).


# OPTIONS

**-p** _path_
: change the download folder.  The default download folder is set to the current working directory.

**-m** _market_
: select the Bing market.

  - `en-US`
  - `zh-CN`
  - `ja-JP`
  - `en-AU`
  - `en-UK`
  - `de-DE` (default)
  - `en-NZ`
  - `en-CA`

**-d** _day_
: select the day of the Bing wallpaper.

  - `0` = today (default)
  - `1` = yesterday
  - `2` = etc.

**-r** _resolution_
: select the desired image resolution in pixels.

  - `UHD` (default)
  - `1920x1280`
  - `1920x1080`
  - `1366x768`
  - `1280x720`
  - `1024x768`
  - `800x600`

**-s** _size_
: set the font size of the wallpaper title added as annotation to the bottom of the wallpaper.  The default is `0` to not include any description.  This feature requires  [ImageMagick](https://www.imagemagick.org/) version 6.3.2 or later.  The value `size` can be set to one of the following:

  - Positive values larger than `1` are interpreted as absolute integers in pixels.
  - Positive values smaller than `1` are applied as scaling factor to the image height of the Bing wallpaper.
  - Positive values with a trailing percentage sign are applied to the image height of the Bing wallpaper.

**-y**
: overwrite existing image files.

**-h**
: show this help message.


# INSTALLATION

Clone the remote repository and change into the local repository:

```bash
$ git clone https://github.com/mboljen/bingdaily
$ cd bingdaily
```

Use the following command to install this software:

```bash
$ make
$ make install
```

The default `PREFIX` is set to `/usr/local`.  In order to successfully complete the installation, you need to have write permissions for the installation location.


# EXIT CODES

+ `0` All operations successful
+ `1` Invalid configuration
+ `2` Failed to fetch meta information of Bing wallpaper
+ `3` Failed to replace existing Bing wallpaper
+ `4` Failed to download Bing wallpaper


# ENVIRONMENT

In order to invoke the script after user login, create the file `~/.config/autostart/bingdaily.desktop` with the following contents.

```
[Desktop Entry]
Type=Application
Name=Daily Bing Wallpaper
Exec=sh -c "bingdaily -y"
Icon=wallpaper
Comment=Download Bing daily wallpaper
X-GNOME-Autostart-enabled=true
```

Make sure that `bingdaily` can be found using the `PATH` variable.

Refer to the bash script [`backslide`](https://github.com/mboljen/backslide) to change the current desktop wallpaper after having downloaded the daily Bing wallpaper.


# CONTRIBUTION

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Submit bug reports online at: <https://github.com/mboljen/bingdaily/issues>

Please make sure to update tests as appropriate.


# SEE ALSO

Full documentation and sources at: <https://github.com/mboljen/bingdaily>


# LICENSE

[MIT](https://choosealicense.com/licenses/mit/)






