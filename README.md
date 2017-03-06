# [resprite-css](http://uptoweb.info/resprite-css)

A simple instruction for calculation CSS properties for responsive background images (RBI) from sprites.

## Content of Resprite-CSS

* The basics of calculating RBI
* Example of responsive images with different sizes
* Example of responsive images with equal sizes (grids, columns, etc)
* Example of cross-browser pseudo compatibility

## The basics of calculating RBI

HTML:
```html
<!--Any parent container element-->
<div class="container">
    <!--Responsive background image element-->
    <div class="img1"></div>
</div>
```

![sprite](https://github.com/uptoweb/resprite-css/blob/master/img/spr.png?raw=true)

##### Initial data:
1. spr-url
2. spr-width = 382px
3. spr-height = 556px
4. img1-width = 322px
5. img1-height = 238px
6. x1 = 40px
7. y1 = 42px

Let's begin to calculate CSS properties of RBI:

CSS:
```css
.img1 {
    /* background-image: url("img/spr.png");*/

    /* background-position: xPos1 yPos1;
    xPos1 = x1 / (spr-width - img1-width) = 40px / (382px - 322px) = 66.66666666666667%
    yPos1 = y1 / (spr-height - img1-height) = 42px / (556px - 238px) = 13.20754716981132% */
    /* background-position: 66.67% 13.21%;*/
    background: url("img/spr.png") 66.67% 13.21%; /*shorthand*/

    /* background-size: w h;
    w = spr-width / img1-width =  382px / 322px = 118.6335403726708%
    h = spr-height / img1-height = 556px / 238px = 233.6134453781513% */
    background-size: 118.63% 233.61%;

    /* padding-top = img1-height / img1-width = 238px/322px = 73.91304347826087% */
    padding-top: 73.91%;

    /* Our element fills all inner container space */
    width: 100%;
}
```
The result you can see [here](http://uptoweb.info/code/resprite-css/basics.html) or in case with pseudo-element, [here](http://uptoweb.info/code/resprite-css/basics-pseudo-element.html)

More information with other examples [here](http://uptoweb.info/resprite-css)
