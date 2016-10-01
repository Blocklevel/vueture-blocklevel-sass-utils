# vueture-blocklevel-sass-utils
> A Blocklevel Vueture SASS plugin, contains mixins, functions and extends for faster templating.

## DOCS NOT DONE YET ##

## Installation ##
Install the plugin by NPM:
``` bash
$ npm install vueture-blocklevel-sass-utils --save
```

Open ```src/assets/sass/app.scss``` and import ```vueture-blocklevel-sass-utils``` under the vendor chapter.


``` css
import '~vueture-blocklevel-sass-utils';
```

## Functions ##
See sass docs for more information about functions.

### Ease ###
CSS easings based on ceaser. https://matthewlein.com/ceaser/

#### Usage ####
``` scss
.my-ease-element {
  transition: background 200ms ease('easeInOut');
}
```

#### Easings ####
| key  | value |
|---|---|
| ```linear``` | ```0.250, 0.250, 0.750, 0.750``` |
| ```ease``` | ```0.250, 0.100, 0.250, 1.000``` |
| ```easeIn``` | ```0.420, 0.000, 1.000, 1.000``` |
| ```easeOut``` | ```0.000, 0.000, 0.580, 1.000``` |
| ```easeInOut``` | ```0.420, 0.000, 0.580, 1.000``` |
| ```easeInQuad``` | ```0.550, 0.085, 0.680, 0.530``` |
| ```easeOutQuad``` | ```0.250, 0.460, 0.450, 0.940``` |
| ```easeInCubic``` | ```0.550, 0.055, 0.675, 0.190``` |
| ```easeOutCubic``` | ```0.215, 0.610, 0.355, 1.000``` |
| ```easeInQuart``` | ```0.895, 0.030, 0.685, 0.220``` |
| ```easeOutQuart``` | ```0.165, 0.840, 0.440, 1.000``` |
| ```easeInQuint``` | ```0.755, 0.050, 0.855, 0.060``` |
| ```easeOutQuint``` | ```0.230, 1.000, 0.320, 1.000``` |
| ```easeInSine``` | ```0.470, 0.000, 0.745, 0.715``` |
| ```easeOutSine``` | ```0.390, 0.575, 0.565, 1.000``` |
| ```easeInExpo``` | ```0.950, 0.050, 0.795, 0.035``` |
| ```easeOutExpo``` | ```0.190, 1.000, 0.220, 1.000``` |
| ```easeInCirc``` | ```0.600, 0.040, 0.980, 0.335``` |
| ```easeOutCirc``` | ```0.075, 0.820, 0.165, 1.000``` |
| ```easeInBack``` | ```0.600, -0.280, 0.735, 0.045``` |
| ```easeOutBack``` | ```0.175, 0.885, 0.320, 1.275``` |
| ```easeInOutQuad``` | ```0.455, 0.030, 0.515, 0.955``` |
| ```easeInOutCubic``` | ```0.645, 0.045, 0.355, 1.000``` |
| ```easeInOutQuart``` | ```0.770, 0.000, 0.175, 1.000``` |
| ```easeInOutQuint``` | ```0.860, 0.000, 0.070, 1.000``` |
| ```easeInOutSine``` | ```0.445, 0.050, 0.550, 0.950``` |
| ```easeInOutExpo``` | ```1.000, 0.000, 0.000, 1.000``` |
| ```easeInOutCirc``` | ```0.785, 0.135, 0.150, 0.860``` |
| ```easeInOutBack``` | ```0.680, -0.550, 0.265, 1.550 |

### Respond-to ###
Media query helper. Helps you to have consistent breakpoints.

#### Usage ####
``` scss
.my-element {
  width: 500px;

  @include respond-to('x-small') {
    width: 100%;
  }
}
```

#### Mediaqueries: ####
| key  | value |
|---|---|
| ```x-small``` | ```(max-width: 480px)``` |
| ```small``` | ```(max-width: 768px)``` |
| ```medium``` | ```(max-width: 1024px)``` |
| ```large``` | ```(min-width: 1025px)``` |
| ```x-large``` | ```(min-width: 1480px)``` |
| ```xx-large``` | ```(min-width: 1680px)``` |
| ```from-x-small``` | ```(min-width: 481px)``` |
| ```from-small``` | ```(min-width: 769px)``` |
| ```from-medium``` | ```(min-width: 1025px)``` |

### zIndex ###
Better z-index managing. Create a list of element names and get the ```z-index``` based on elements name. Returns a number.

#### Usage: ####
``` scss
@layout: content, popup;

.content {
  z-index: zindex($layout, content); // z-index: 1;
}

.popup {
  z-index: zindex($layout, popup); // z-index: 2;
}
```

#### Parameters: ####

| name | type | description |
|---|---|---|
| ```$list``` | ```(Array)``` | The list to find the current ```z-index``` in |
| ```$element``` | ```(String)``` | The name of the current element, must be in the ```$list``` |
