# bingdaily

This bash script downloads the daily Bing wallpaper and saves it to a given directory.

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
$ bingdaily [-C directory] [-m market] [-d day] [-r resolution] [-y] [-h]
```

### Options

+ `-C directory`

  Changes the download folder.  The default download location is set to `$XDG_PICTURES_DIR/Bing`.

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

  Selects the desired image resolution.

  - `UHD` (default)
  - `1920x1280`
  - `1920x1080`
  - `1366x768`
  - `1280x720`
  - `1024x768`
  - `800x600`

+ `-y`

  Overwrites existing image files.

+ `-h`

  Shows this help message.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
