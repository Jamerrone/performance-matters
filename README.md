# Performance matters

## Project setup

This project serves an adapted version of the [Bootstrap documentation website](http://getbootstrap.com/). It is based on the [github pages branche of Bootstrap](https://github.com/twbs/bootstrap/tree/gh-pages). 

Differences from actual Bootstrap documentation:

- Added custom webfont
- Removed third party scripts
- The src directory is served with [Express](https://expressjs.com/).
- Templating is done with [Nunjucks](https://mozilla.github.io/nunjucks/)

## Project progress

#### Run 1: Init
![](./images/1-init-run.png)

#### Run 2: Minify CSS
![](./images/2-minify-css.png)

#### Run 3: Optimize Images
![](./images/3-optimize-images.png)

#### Run 4: Minify JavaScript
![](./images/4-minify-js.png)

#### Run 5: Minify HTML
![](./images/5-minify-html.png)

#### Run 6: Unused CSS & Font Display: swap
![](./images/6-unused-css-and-font-swap.png)

#### Run 7: Critical CSS & Async CSS
![](./images/7-criticalcss-and-asynccss.png)

## Getting started

- Install dependencies: `npm install`
- Serve: `npm start`
- Expose localhost: `npm run expose`