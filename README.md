# Bizzell Library AR Scavenger Hunt 2020

A simple web-based AR experience to encourage students to explore the Bizzell Library building.

## Contents

* [Introduction](#Introduction)
* [Requirements](#Requirements)
* [Installation](#Installation)
* [Miscellaneous](#Miscellaneous)
* [Modification](#Modification)

## <a name="Introduction"></a> Introduction

This is a web-based AR experience intended to encourage new students to explore the Bizzell Library at the University of Oklahoma. The initiative is designed to help maintain social distancing by alleviating the need for a traditional "lead a group of students on a tour" approach.

The webpage is intended to be visited using a mobile device with a camera. The introductory page offers basic information and guidance, and includes links into a more detailed help page and the main scavenger hunt display.

The main display shows a series of icons down the left hand side of the screen. These icons indicate locations to find, and clicking on an icon produces a clue for the user. Whether the clue is easy or hard to relate to the location depends on the options the user chose on the introductory screen.

There is a unique AR marker placed in each physical location. when the user points their mobile device's camera at the marker, the marker is recognized and the appropriate icon is highlighted to indicate the location has been found.

When all locations are found, a message is displayed encouraging the user to visit the circulation desk for their free prize - 3D printed ear protectors.

## <a name="Requirements"></a> Requirements

* Web server that supports HTTPS (required for camera access in iOS and Android)
* Reasonably modern mobile device (iOS or Android) and web browser (Safari and Chrome both work)
* The [three.js](https://threejs.org/) JavaScript 3D library ([GitHub](https://github.com/mrdoob/three.js/))
* The [ARToolKit.js](http://www.artoolkitx.org/jsartoolkit5/) JavaScript port of ARToolKit ([GitHub](https://github.com/artoolkitx/jsartoolkit5))
* The [THREEx](http://www.threejsgames.com/extensions/) extensions for `three.js` ([GitHub](https://github.com/jeromeetienne/threex))

## <a name="Installation"></a> Installing the software

Copy the contents of this repository into a suitable directory on your web host, and install the other dependencies as described in the [Requirements](#Requirements) section.

Note: you may need to change paths to the JavaScript files in `hunt.html` file.

## <a name="Miscellaneous"></a> Miscellaneous

The `hunt.html` page can be accessed using two parameters: `mode` and `debug`.

The `mode` parameters controls whether the clues provided to the user are straightforward (`mode=easy`) or more cryptic (`mode=hard`).

The `debug` parameter controls whether the user is shown a button to clear the internal cookie that remembers which locations were found previously, and attempts to superpose colored boxes over identified AR markers (`debug=true`).

For example, `hunt.html?mode=hard` access the hunt in hard mode, whereas `hunt.html?mode=easy&debug=true` would access the `hunt.html` page in easy mode with the `debug` additions enabled.

## <a name="Modification"></a> Modification

This project should be fairly trivial to modify; new content simply requires new icons and markers to be generated, with the `system` object in `hunt.html` updated to reflect the changes.
