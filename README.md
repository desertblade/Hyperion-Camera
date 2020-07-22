# Hyperion-Camera
How to setup Hyperion.ng to use a PI camera

## Parts List:
 * Pi Camera: https://www.amazon.com/gp/product/B07RXKZ1KN/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1Long 
 * Ribbon cable: https://www.amazon.com/gp/product/B07D58GDDV/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1Wide 
 * Lens kit: https://www.amazon.com/gp/product/B01E18OYVW/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1

3d printed this as the camera holder, which the arm is command strip held on under the top of the entertainment center: https://www.thingiverse.com/thing:2019291


## Steps:
 1. Install the Pi cameraActivate the camera in rasp-config
    - Enable both the camera and SPI
 1. Run these commands to make the camera work with USB/Hyperion
    - sudo modprobe bcm2835-v4l2
    - /usr/bin/v4l2-ctl --set-ctrl=rotate=180 --set-fmt-video=width=1280,height=720,pixelformat=UYVY -d /dev/video0
 1. Go to hyperion 
