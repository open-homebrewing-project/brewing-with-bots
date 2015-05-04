# Brewing with Bots

Making beer with the help of <br> our robot overlords

![Drunk Bender](https://brocastnews.files.wordpress.com/2013/12/giphy.gif)

!

## Don't Fear the Robots

![Drone Attack](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/drone.gif)

!

## About Me

- VividCortex
- 7 years of Ops
- [Drone racer in training](http://signup.fpvracingva.com)
- DevOpsCV May 26!!!
- @AgentO3

!

## Beer, Robots, Why?

- Homebrewing is fun!
- Waiting sucks, Robots awesome!!!
- Control == Quality & Consistency
- Desire to hack on physical things
- Homebrewing system are $$$

!

PicoBrew Zymatic - $1600

![PicoBrew](http://www.dudeiwantthat.com/gear/food-drink/picobrew-zymatic-automatic-9674.jpg)

!

BrewBot - $2800

![BrewBot](http://venturebeat.com/wp-content/uploads/2014/09/brewbot.jpg)

!

## 0 to Homebrewer

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-02-23%2012.26.12.jpg)

!

## <strike>Robot</strike> Beer Laws

1. Majority of fermentables must come from grains
1. Must have hops
1. Anything else goes

!

![](http://a57.foxnews.com/global.fncstatic.com/static/managed/img/876/493/rerwerr4534534.jpg?ve=1&tl=1)

!

![](http://beerpulse.com/wp-content/uploads/2013/03/wynkoop-rocky-mountain-oyster-stout-can.jpg)

!

## Processes

- Mashing
- Boil
- Fermentation

!

## Mashing

- Bring water to strike temperature ( 168 F )
- Add grain bill & mix ( 10 to 15lbs )
- Mash for time ( 60 to 90 mins )
- Separate grain from wort
- Sparg grain with water ( 168 F )
- Combine to get boil volume

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-02-23%2013.57.48.jpg)

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-02-23%2014.02.30.jpg)

!

## Boil

- Bring wort to a rolling boil
- Boil for time ( 60 to 90 mins )
- Add hops and other additions at schedule
- Cool wort down ( 75 F )

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-02-23%2015.11.44.jpg)

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-02-23%2016.17.52.jpg)

!

## Fermentation

- Transfer to fermentor
- Pitch yeast
- Store for 2 weeks or more @55 to 85 F
- Bottle or Keg

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-06-11%2018.57.47.jpg)

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2014-02-25%2019.41.58.jpg)

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/2013-09-19%2018.50.51.jpg)

!

# Homebrewing Ops

!

## Most Important Parameters

- Time
- Temperature

!

## Other Parameters

- Liquid volume
- Specific gravity

!

## Common Tasks

- Sanitization
- Heating water ( electric or gas )
- Moving wort ( gravity or pumps )
- Mixing grains
- Sparging
- Adding boil additions
- Chilling wort ( immersion, reverse flow )

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/brewops-loop.png)

!

## Say Hello to BrewTronV1

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/assemble.gif)

!

## BrewTron Bots

- MashTron
- BoilTron
- FermenTron

!

## What is a BrewTron?

- RaspberryPI
- DS18b20 Temperature Prob
- USB Wifi

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/ds18b20-waterproof.jpg)

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/IMG_2038.JPG)

!

## Software

- Node.js
- Cylon.js

!

## Graphing

- StatsD
- Librato

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/IMG_2197.PNG)

!

## Notifications

@BrewTronV1

!

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/Screen%20Shot%202015-04-29%20at%201.42.38%20PM.png)

!

## Why JavaScript?

Accessible

!

# Setting up a BrewTron

!

## Installing Node.js

<div class="code">
wget http://node-arm.herokuapp.com/node_latest_armhf.deb
sudo dpkg -i node_latest_armhf.deb
</div>

!

## Wiring up temperature sensor

![](https://dl.dropboxusercontent.com/u/69816878/brewing-with-bots/learn_raspberry_pi_breadboard-probe.png)

!

## Preparing the PI

<div class="code">
sudo modprobe w1_gpio && sudo modprobe w1_therm
</div>

!

## Preparing the PI

<div class="code">
echo "w1_gpio" >> /etc/modules
echo "w1_therm" >> /etc/modules
</div>

!

## Reading Sensor Data

<div class="code">
/sys/bus/w1/devices/28-0000066fc63a/w1_slave
</div>

!

## Reading Sensor Data

<div class="code">
56 01 4b 46 7f ff 0a 10 d1 : crc=d1 YES
56 01 4b 46 7f ff 0a 10 d1 t=21375
</div>

!

## Reading Sensor Data

<div class="code">
56 01 4b 46 7f ff 0a 10 d1 : crc=d1 YES
56 01 4b 46 7f ff 0a 10 d1 <span class="highlight">t=21375</span>
</div>

!

## Reading Sensor Data

21375 / 1000 = <span class="highlight">21.375 C<span>

21.375 * 9/5 + 32 = 70.475 F

!

## Reading Sensor Data

21375 / 1000 = 21.375 C

21.375 * 9/5 + 32 = <span class="highlight">70.475 F</span>

!

# Cylon.js Intro

- Robot
- Connections
- Devices
- Utilities

!

## Robot

<div class="code">
<span class="highlight">var Cylon = require('cylon')</span>
...
Cylon.robot({
  work: function(my) {
    # Do Stuff
...
}).start();
</div>


!

## Robot

<div class="code">
var Cylon = require('cylon')
...
<span class="highlight">Cylon.robot({
  work: function(my) {
    # Do Stuff</span>
...
}).start();
</div>


!

## Robot

<div class="code">
var Cylon = require('cylon')
...
Cylon.robot({
  work: function(my) {
    # Do Stuff
...
<span class="highlight">}).start();</span>
</div>

!

## Connections

<div class="code">
...
Cylon.robot({
  <span class="highlight">connections: {
    robot: { adaptor: "loopback" }
    },</span>
  work: function(my) {
    my.robot.emit("some-event");
...
</div>

!

## Connections

<div class="code">
...
Cylon.robot({
  connections: {
    robot: { adaptor: "loopback" }
    },
  work: function(my) {
    <span class="highlight">my.robot.emit("some-event");</span>
...
</div>

!

## Devices

<div class="code">
...
Cylon.robot({
  ...
  <span class="highlight">devices: {
    lcd: { driver: 'lcd' }
  },</span>
  ...
  work: function(my) {
    my.lcd.print("Hello!");
...
</div>


!

## Devices

<div class="code">
...
Cylon.robot({
  ...
  devices: {
    lcd: { driver: 'lcd' }
  },
  ...
  work: function(my) {
    <span class="highlight">my.lcd.print("Hello!");</span>
...
</div>

!

## Utilities

<div class="code">
...
  work: function(my) {
    <span class="highlight">every((10).seconds(), function(){
      my.sampleTemp(my);</span>

      my.when(my.currentTemp >= my.waterTemp, function(){
        my.robot.emit("heat-water");
    });
...
    my.robot.once("heat-water", function(){
    # Only do this once
...
</div>

!


## Utilities

<div class="code">
...
  work: function(my) {
    every((10).seconds(), function(){
      my.sampleTemp(my);

      <span class="highlight">my.when(my.currentTemp >= my.waterTemp, function(){
        my.robot.emit("heat-water");</span>
    });
...
    my.robot.once("heat-water", function(){
    # Only do this once
...
</div>

!

## Utilities

<div class="code">
...
  work: function(my) {
    every((10).seconds(), function(){
      my.sampleTemp(my);

      my.when(my.currentTemp >= my.waterTemp, function(){
        my.robot.emit("heat-water");
    });
...
    <span class="highlight">my.robot.once("heat-water", function(){
    # Only do this once</span>
...
</div>

!

## BrewTron Code

[MashTron](https://raw.githubusercontent.com/open-homebrewing-project/mashtron/master/robot.js)

[BoilTron](https://raw.githubusercontent.com/open-homebrewing-project/boiltron/master/robot.js)

[FermenTron](https://raw.githubusercontent.com/open-homebrewing-project/fermentron/master/robot.js)

!

# Open Homebrewing Project

An effort to design hardware specs and software for an automated homebrewing system.

!

## Inspired by

- [Open Compute Project](http://www.opencompute.org/)
- [Windowfarms](http://our.windowfarms.org/)
- [Farm Hack](http://farmhack.org/)

!

## Project Goals

- Spur innovation
- Keep costs low
- Build DIY a community

!

## Ideas / Projects

- Vibration mixer
- Automate sparging process
- Water level sensors
- Digital Specific Gravity sensor
- BrewCloud Dashboard

!

## It's a Marathon

3 to 5 years

!

## Leverage RaspberryPI Ecosystem

!

![](http://ecx.images-amazon.com/images/I/41alJqHI0uL._SY355_.jpg)

!

![](http://www.modmypi.com/image/data/rpi-products/hacking-and-prototyping/sensors/hc-sr04.JPG)

!

## References

[DS18B20 Wiring and Setup for RaspberryPI](https://learn.adafruit.com/adafruits-raspberry-pi-lesson-11-ds18b20-temperature-sensing/hardware)

[More info on DS18B20](http://www.tweaking4all.com/hardware/arduino/arduino-ds18b20-temperature-sensor/)

[What Modules you will need](http://www.reuk.co.uk/DS18B20-Temperature-Sensor-with-Raspberry-Pi.htm)

[Installing Node.js on RaspberryPI](http://weworkweplay.com/play/raspberry-pi-nodejs/)

[Prevent Wifi Sleep](http://electronut.in/preventing-raspberry-pi-wifi-from-going-into-sleep-mode/)

[Cylon.js Docs](http://cylonjs.com/documentation/guides/working-with-robots/)

## Code

[Open Homebrewing Project](https://github.com/open-homebrewing-project)

[MashTron](https://github.com/open-homebrewing-project/mashtron)

[BoilTron](https://github.com/open-homebrewing-project/boiltron)

[FermenTron](https://github.com/open-homebrewing-project/fermentron)
