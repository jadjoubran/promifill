# Promyfill

Promyfill saves you from shipping polyfill code to all browsers.
Your own polyfill URL will be loaded only if needed.

✅ Promyfill is < 500 Bytes.

# Usage


## Fetch example

```javascript
const fetchPolyfill = 'https://unpkg.com/unfetch@2.1.2/dist/unfetch.umd.js';

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

# Feedback

This is a PWA experiment (medium article coming soon).
For feedback or questions, please open a new issue.
