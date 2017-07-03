jquery.counterup
==========

jquery.counterup is a jQuery plugin that *animates* a number from zero (counting up towards it). It supports counting up:

* integers `12345`
* floats `0.1234`
* formatted numbers `1,234,567.00`
* time `21:45:00`

Features:

* Auto-detect for integers, floats or formatted numbers.
* The plugin will also use the number of decimal places the original number is using.
* Start counter with a different duration and delay by setting `data-counterup-time=""` and `data-counterup-delay=""`.
* Lets you use your own formatter.
* Lightweight: ~1kb
* Minimal setup

*Requires [waypoints.js](http://imakewebthings.com/jquery-waypoints/)*

Demo
====

**[DEMO](http://ciromattia.github.io/jquery.counterup/demo/index.html)**

Install with Bower
```
bower install jquery.counterup
```
=====

**Include**

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/waypoints/4.0.0/jquery.waypoints.min.js"></script>
<script src="jquery.counterup.min.js"></script>
```

**HTML**

With default values from plugin instantiation.
```
<span class="counter">1,234,567.00</span>
<span>$</span><span class="counter">1.99</span>
<span class="counter">12345</span>
```
With values from `data` attribute.
```
<span class="counter" data-counterup-time="1500" data-counterup-delay="30" data-counterup-beginat="100">1,234,567.00</span>
```

**jQuery**

```
$('.counter').counterUp();
```

**or with extra parameters**

```
$('.counter').counterUp({
    delay: 10,
    time: 1000,
    offset: 70,
    beginAt: 100,
    formatter: function (n) {
      return n.replace(/,/g, '.');
    }
});
```

`delay` - The delay in milliseconds per number count up

`time` - The total duration of the count up animation

`offset` - The viewport percentile from which the counter starts (by default it's 100, meaning it's triggered
at the very moment the element enters the viewport)

`beginAt` - The number from which to count up

`formatter` - A callback to format the number with
