 Browsers
==========

There are a couple of wonderful things about this system.
First of all, each piece integrates with the pieces below it, but there's very little (if any at all) interaction from a lower level to a higher one.
This means that, since they are planned to be shared libraries or other public APIs, you can swap out many pieces as you'd like.
Second, this incredible separation allows us to manage some pretty cool functionality, (e.g., a more automated version of the `RMS browsing method <http://lwn.net/Articles/262570/>`_).

- [ ] Fetcher

  - libcurl layer to grab a page and read it into memory

- [ ] Cacher

  - database table that stores the URL, the time cached and some serialized data

- [ ] Crawler and Mounter

  - library to crawl a webpage to create a relatively simple sitemap (which is likely part of the serialized data to be cached)
  - layer over a FUSE filesystem to opaquely represent the webpage's structure

- [ ] Pager / Renderer

  - Correctly handle basic ``<div>`` layouting
  - CSS (colors, animations?, basic layouting)
  - JS (enough to allow basic logins)
  - basic security features (DNT, noscript, &c.)
  - sixel?

- [ ] Daemon and CLI client

  - Daemon will be sitting waiting to fetch pages on-request from a client
  - Client will offer control over each piece of the structure
