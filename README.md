# khalid-
import {registerRoute} from 'workbox-routing'; import {CacheFirst} from 'workbox-strategies'; import {ExpirationPlugin} from 'workbox-expiration';  registerRoute(   ({request}) => request.destination === 'image',   new CacheFirst({     cacheName: 'image-cache',     plugins: [       new ExpirationPlugin({         maxEntries: 20,       }),     ],   }) );
