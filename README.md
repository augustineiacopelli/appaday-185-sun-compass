# Sun Compass

**AppADay Day 185 · Category I (Interactive) · No Claude API**

Live: https://augustineiacopelli.github.io/appaday-185-sun-compass/

Sun Compass shows where the sun is right now on a flat compass dial, with live azimuth and altitude, sunrise, solar noon, sunset, day length change, and a plain English why for each reading. Calibrate your phone compass against the sun, test your sense of direction in Predict, and scrub to any solstice or equinox.

## How it works

The dial is a map of the sky seen from above. North is up, the rim is the horizon, and the center is straight overhead. The amber arc traces the sun's path for the day, sampled every 10 minutes, with orange sunrise, cream solar noon and red sunset markers. When the compass is live the dial turns so it lines up with the real sky; without a sensor, drag the dial or use the heading slider.

Solar position comes from the NOAA solar calculator equations, including the equation of time and atmospheric refraction. Sunrise and sunset use the standard 90.833 degree zenith, and polar day and polar night are handled. A self check runs on load against three Wichita cases (June solstice noon altitude 75.8, December solstice noon altitude 28.9, equinox sunrise azimuth near 90) and reports in the footer and the console.

## Modes

**Live** shows the sun, the day arc, six readout cards (azimuth, altitude, sunrise, solar noon, sunset, day length) each with a short explanation, and a why line about the sun's declination and your noon peak.

**Calibrate** works only when the real sun is above 5 degrees. Lay the phone flat, stand a pen upright on the screen, and turn until its shadow runs straight down to the bottom edge, so the top of the phone points at the sun. Lock computes a signed offset, Apply saves it, and Reset clears it. An optional magnetic declination field covers compasses that read magnetic north. Never look at the sun.

**Sky View** opens the rear camera full screen and draws the day's sun path over the real sky: a dashed horizon with compass bearings, the amber arc with hour labels, a red golden hour band near each end, sunrise and sunset markers, the noon peak, and the sun itself. When the sun is out of frame an edge arrow points to it. The date chips inside Sky View show where the sun will rise and set on a solstice or equinox from the spot you're standing. A zoom match slider (25 to 80 degrees across the screen, default 40) tunes the overlay to your camera. Sky View uses full device orientation (alpha, beta and gamma through a W3C rotation matrix), applies the Calibrate offset and declination, and needs the phone held upright. Without motion sensors or a camera, drag to look around a plain sky.

**Predict** hides the sun. Tap the dial for its direction, or use Aim with phone to point the top edge of the phone where you think the sun is and lock it, so the phone's tilt sets the height. Otherwise set the height with the slider, and reveal. Score is 100 minus the azimuth error minus 1.5 times the altitude error, clamped to 0 through 100. The best score is saved.

## Date, time and location

The day of year and time of day sliders scrub to any moment, the four chips jump to the March equinox, June solstice, September equinox and December solstice, and Today returns to live time. Location defaults to Wichita, KS, can use the device location, or accepts a manual latitude and longitude. Times display in the device's time zone.

## Notes

Single self contained index.html with no dependencies. The compass needs a tap to request permission on iPhone (iOS 13 and later) and uses deviceorientationabsolute on Android. Settings, calibration and best score are stored in localStorage under appaday185.
