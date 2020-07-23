# Hyperion-Camera
How to setup Hyperion.ng to use a PI camera

WARNING: This does not work with the 5/27 build of Hyperion.NG! You will need to build the latest to get it to work. 

## Parts List:
 * Pi Camera: https://www.amazon.com/gp/product/B07RXKZ1KN/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1Long 
 * Ribbon cable: https://www.amazon.com/gp/product/B07D58GDDV/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1Wide 
 * Lens kit: https://www.amazon.com/gp/product/B01E18OYVW/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1

3d printed this as the camera holder, which the arm is command strip held on under the top of the entertainment center: https://www.thingiverse.com/thing:2019291


## Steps:
 1. Install Hyperion.ng
    - Follow DrZzs guide - https://www.youtube.com/watch?v=urOEHzbV48A
    - You will NOT need the HDMI capture card. The PI Camera is what you will use.
    - Have you pi camera hooked up
 1. Activate the camera in rasp-config
    - Enable both the camera and SPI(?)
 1. Run these commands to make the camera work with USB/Hyperion
    - sudo modprobe bcm2835-v4l2
    - Configure Camera
      - Mine is upside down
      - /usr/bin/v4l2-ctl --set-ctrl=rotate=180 --set-fmt-video=width=1280,height=720,pixelformat=UYVY -d /dev/video0 -p 30
    - Will need to run this command on every reboot (will add services at some time)
 1. Go to hyperion 
 1. Under Configuration Enable USB Capture
 1. Change Size Decimation to 1
    - We set a lower resolution above
 1. Under Led Hardware configure you layout
 1. Go to advanced setting to change Trapezoid to fit your TV
    - The 4 corners of your TV
    - Refresh page and click on the TV icon in the top right corner, click live view
    - Won't be perfect get it close
