# bingdaily

This bash script downloads the daily Bing wallpaper and saves it to a given directory.

Refer to the bash script [`backslide`](https://github.com/mboljen/backslide) to change the current desktop wallpaper after having downloaded the daily Bing wallpaper.

## Installation

Use the following command to install this software:

```bash
$ make
$ make install
```

The default `PREFIX` is set to `/usr/local`.  In order to succesfully complete the installation, you need to have write permissions for the installation location.

## Usage

The following command will download the current wallpaper offered by [Bing](https://www.bing.com/):

```bash
$ bingdaily [-p directory] [-m market] [-d day] [-r resolution] [-s size] [-y] [-h]
```

### Options

+ `-p directory`

  Changes the download folder.  The default download location is set to the current working directory.

+ `-m market`

  Selects the Bing market.

   - `en-US`
   - `zh-CN`
   - `ja-JP`
   - `en-AU`
   - `en-UK`
   - `de-DE` (default)
   - `en-NZ`
   - `en-CA`

+ `-d day`

  Selects the day of the Bing wallpaper.

  - `0` = today (default)
  - `1` = yesterday
  - `2` = etc.

+ `-r resolution`

  Selects the desired image resolution in pixels.

  - `UHD` (default)
  - `1920x1280`
  - `1920x1080`
  - `1366x768`
  - `1280x720`
  - `1024x768`
  - `800x600`

+ `-s size`

  Set font size of wallpaper title added as annotation to the bottom of the wallpaper. The default is `0` to not include any description.  [ImageMagick](https://www.imagemagick.org/) is required.  The value `size` can be set to one of the following:

  + Positive values larger than `1` are interpreted as absolute values in pixels.
  + Positive values smaller than `1` are applied as scaling factors to the detected image height.
  + Positive values with trailing percentage sign are applied to the image height.

+ `-y`

  Overwrites existing image files.

+ `-h`

  Shows this help message.

### Exit codes

+ `0` All operations successful
+ `1` Invalid configuration
+ `2` Failed to fetch meta information of Bing wallpaper
+ `3` Failed to replace existing Bing wallpaper
+ `4` Failed to download Bing wallpaper

### Autostart

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

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
