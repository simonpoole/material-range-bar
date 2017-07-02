MaterialRangeBar
================

This is a fork of MaterialRangeBar v1.3 https://github.com/oli107/material-range-bar that in turn is a fork of https://github.com/edmodo/range-bar that adds some basic material styling, as well as start and end values, values as floats and some other things. It is aiming to mimic this:

http://www.google.com/design/spec/components/sliders.html

It is similar to an enhanced SeekBar widget, though it doesn't make use of the SeekBar. It provides for the selection of a range of values as well as for a single value. The selectable range values are discrete values designated by tick marks; the pin (handle) will snap to the nearest tick mark. This is my first library project, apologies for poor coding, etc etc.

Supported on API Level 12 and above for animations.

![Img](https://github.com/oli107/material-range-bar/blob/master/Screenshots/pin%20expand.gif)

Developers can customize the following attributes (both via XML and programatically):

### Change Log
```

```

### Tick Properties
```
tickStart | float
tickEnd | float
tickInterval | float
tickHeight | dimension
tickColor | color
```

###  Bar Properties
```
rangeBar | boolean
barWeight | dimension
rangeBarColor | reference or color
barPaddingBottom | dimension
connectingLineWeight | dimension
connectingLineColor | reference or color
```

### Pin Properties
```
pinPadding | dimension
pinRadius | dimension
pinMinFont | dimension
pinMaxFont | dimension
pinColor | reference or color
textColor | reference or color
temporaryPins | boolean
```

### Selector Properties
```
selectorColor | reference or color
selectorSize | dimension
```

### Via runtime only (no XML option)
```
pin indices (the location of the thumbs on the RangeBar)
```

![ScreenShot](https://github.com/oli107/material-range-bar/blob/master/Screenshots/screenshot.png)


Examples
=======

## Layout XML

This is a rangebar with both a lower and upper value
```xml
<com.appyvet.rangebar.RangeBar
        xmlns:custom="http://schemas.android.com/apk/res-auto"
        android:id="@+id/rangebar"
        android:layout_width="match_parent"
        android:layout_height="72dp"
        custom:tickStart="5"
        custom:tickInterval="1"
        custom:tickEnd="10"
        android:layout_marginLeft="16dp"
        android:layout_marginRight="16dp"/>
```

This is a seekbar with only a single value (note rangeBar=false)
```xml
<com.appyvet.rangebar.RangeBar
        xmlns:custom="http://schemas.android.com/apk/res-auto"
        android:id="@+id/rangebar"
        android:layout_width="match_parent"
        android:layout_height="72dp"
        custom:rangeBar="false"
        android:layout_marginLeft="16dp"
        android:layout_marginRight="16dp"/>
```

## Adding a listener
//TODO add a full example here
- Add a listener - rangeBar.setOnRangeBarChangeListener which returns left and right index as well as value.
```java
rangebar.setOnRangeBarChangeListener(new RangeBar.OnRangeBarChangeListener() {
            @Override
            public void onRangeChangeListener(RangeBar rangeBar, int leftPinIndex,
                    int rightPinIndex,
                    String leftPinValue, String rightPinValue) {
            }
        });
```
## Adding a formatter
Formats the text inside the pin.
- Add a formater - IRangeBarFormatter which will return the value of the current text inside of the pin
- Transform string s into any string you want and return the newly formated string. 
```java
rangebar.setFormatter(new IRangeBarFormatter() {
            @Override
			public String format(String s) {
				// Transform the String s here then return s
                return null;
            }
        });
```
TODO
=======
- Better instructions.
- Properly implement Map of strings to each value

Demo
=======
... not provided for this fork ....


Installation
=======

**build.gradle**

```groovy
dependencies {
    compile "ch.poole:rangebar:0.1.1"
}
```

License
=======
Copyright 2016, 2017 Simon Poole
Copyright 2015, AppyVet, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License.
You may obtain a copy of the License in the LICENSE file, or at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

