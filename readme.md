# Readme

## The files and their connections

The connection between the files is something like this:

- when a page is loaded `content_script.js` is injected
- script checks if the API exists for the current site
- the result is sent to `background.js`, who sets the status of the icon
- and the `popup.html` does the fetching of the posts and so on

## Links and stuff

- [WP JSON REST API reference](https://developer.wordpress.org/rest-api/reference/)

## Build Setup

The extension must unfortunately be built, because:

> Some environments, such as Google Chrome Apps, enforce Content Security Policy (CSP), which prohibits the use of new Function() for evaluating expressions. The standalone build depends on this feature to compile templates, so is unusable in these environments.

The build process compiles the VUE template so it can work in the Chrome extension environment.

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
