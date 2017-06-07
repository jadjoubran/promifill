# Promyfill

Promyfill saves you from shipping polyfill code to all browsers.
Your own polyfill URL will be loaded only if needed.

✅ Promyfill is < 500 Bytes.

# Usage

## Fetch example

```javascript
const fetchPolyfill = 'https://rawgit.com/github/fetch/master/fetch.js';

promyfill(window.fetch, fetchPolyfill).then((fetch) => {
    //fetch is available (polyfill is fetched only if needed)
    fetch('users.json');
});
```

## Alternate usage

```javascript
const fetchPolyfill = 'https://rawgit.com/github/fetch/master/fetch.js';

promyfill('fetch' in window, fetchPolyfill).then(() => {
    //fetch is available (polyfill is fetched only if needed)
    fetch('users.json');
});
```

## Intersection observer example

```javascript
const ioPolyfill = 'https://rawgit.com/WICG/IntersectionObserver/gh-pages/polyfill/intersection-observer.js';

promyfill('IntersectionObserver' in window, ioPolyfill).then(() => {
    const io = new IntersectionObserver(() => {});
})
```

# "Promises" support

Promyfill relies on native promises available in most modern browsers, except a [few](http://caniuse.com/#search=promise) such as IE11, Android 4.4].
In order to support these browsers, you can use [promise-min](https://github.com/taylorhakes/promise-polyfill) from taylorhakes

# Feedback

This is a PWA experiment, usage & motivation detailed in this [Medium article](https://medium.com/@JoubranJad/progressive-web-app-experiment-promyfill-900faddda22f)
For feedback or questions, please open a new issue.
