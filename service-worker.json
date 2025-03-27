self.addEventListener('install', function (e) {
  e.waitUntil(
    caches.open('pastillas-v1').then(function (cache) {
      return cache.addAll([
        'pastillas.html',
        'manifest.json',
        'icon-192.png',
        'icon-512.png',
        'service-worker.js'
      ]);
    })
  );
});

self.addEventListener('fetch', function (e) {
  e.respondWith(
    caches.match(e.request).then(function (response) {
      return response || fetch(e.request);
    })
  );
});
