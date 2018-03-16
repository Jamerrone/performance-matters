# Performance Matters

## Project Setup

This project serves an adapted version of the [Bootstrap documentation website](http://getbootstrap.com/). It is based on the [github pages branche of Bootstrap](https://github.com/twbs/bootstrap/tree/gh-pages). 

Differences from actual Bootstrap documentation:

- Added custom webfont
- Removed third party scripts
- The src directory is served with [Express](https://expressjs.com/).
- Templating is done with [Nunjucks](https://mozilla.github.io/nunjucks/)

## Project Progress

### Run 1: Init
![](./images/1-init-run.png)
The first run was extremely slow and unoptimized for slow 3G connections. There were multiple critical problems with a total load time of 31 seconds. The first paint was only rendered at the 9th second. This means that the user stared at a blank screen for almost 10 seconds! Other then the slow render speed the total download size was huge, at 1.2mb.

**First meaningful paint:** 09.60s<br>
**Total load time:** 30.73s

### Run 2: Minify CSS
![](./images/2-minify-css.png)<br>
For the minifying process, I used a vs code plugin named Minify. Somehow Google Chrome bugged out and didn't want to render the paint screenshots. However, it was a bit faster but not really significant as you can see in the total load time. Mostly because of the blocking behavior of the CSS and JavaScript files.  

**First meaningful paint:** -<br>
**Total load time:** 30.48s

### Run 3: Optimize Images
![](./images/3-optimize-images.png)
This was a bigger performance boost then I had imagined. The one second gain on the first meaningful paint is, of course, nice but the real boost can be found in the total load time. A 08.38s boost is huge. For the image optimization, I used the [Tinypng](https://tinypng.com/) web interface.

**First meaningful paint:** 08.99s<br>
**Total load time:** 22.10s

### Run 4: Minify JavaScript
![](./images/4-minify-js.png)
For the javascript minifying process I used the same Minify plugin. Somehow the first paint performance went backward but I gained a few more seconds on the total load time. I am quite happy with this, mostly because I know that my first paint will get an enormous boost in the last 2 optimization steps.

**First meaningful paint:** 11.70s<br>
**Total load time:** 19.94s

### Run 5: Minify HTML
![](./images/5-minify-html.png)
Same as the JavaScript files but with 0 gains.

**First meaningful paint:** 11.80s<br>
**Total load time:** 19.96s

### Run 6: Unused CSS & Font Display: swap
![](./images/6-unused-css-and-font-swap.png)
What a boost! By deleting the unused CSS properties and using the new font swap technique my total load time went to 18.77 and my first meaningful paint to 04.69 seconds!

**First meaningful paint:** 04.69s<br>
**Total load time:** 18.77s

### Run 7: Critical CSS & Async CSS
![](./images/7-criticalcss-and-asynccss.png)
Ok, this is unreal. The critical CSS and async CSS combinations is huge! I am not sure why I never heard about this before but I can ensure everyone that this will be my new standard. The total load time got a 1-second performance boost but my first meaningful paint went to 293 milliseconds! For the critical CSS, I used the [Critical Path CSS Generator](https://jonassebastianohlsson.com/criticalpathcssgenerator/) website.

**First meaningful paint:** *293ms !*<br>
**Total load time:** 17.55s

## Getting Started

- Install dependencies: `npm install`
- Serve: `npm start`
- Expose localhost: `npm run expose`