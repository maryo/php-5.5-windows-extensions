1) Extract ImageMagick-6.8.6-8-Q16.7z to C:\ImageMagick-6.8.6-8-Q16
2) Add C:\ImageMagick-6.8.6-8-Q16 to Path environment variable
3) Set new environment variable MAGICK_HOME to C:\ImageMagick-6.8.6-8-Q16
4) Enable imagick extension by editing your php.ini by appending extension=php_imagick.dll
5) Restart
6) Profit

Of course it is possible to install GraphicsMagick to a directory of your choice, just update the environment variables accordingly and restart.