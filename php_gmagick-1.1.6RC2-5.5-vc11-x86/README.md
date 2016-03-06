- Extract `GraphicsMagick-1.4.02-Q16.7z` to `C:\GraphicsMagick-1.4.02-Q16`
- Add `C:\GraphicsMagick-1.4.02-Q16` to `Path` environment variable
- Set new environment variable `MAGICK_HOME` to `C:\GraphicsMagick-1.4.02-Q16`
- Enable gmagick extension by editing your php.ini by appending `extension=php_gmagick.dll`
- Restart
- Profit

Of course it is possible to install GraphicsMagick to a directory of your choice, just update the environment variables accordingly and restart.
