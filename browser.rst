 Browsers
==========

- [ ] Daemon (?)

  - [ ] Fetch pages with ``libcurl``/similar into a cache
  - [ ] Walk a cached page to create a data structure of page resources (?)

This is an interesting idea; it separates the online part of the internet from browsing.
This makes security much simpler to accomplish (this almost feels like a slightly more automated version of the `RMS browsing method <http://lwn.net/Articles/262570/>`_).
It also separates the components of a browser into the page fetcher and the renderer (possibility to support multiple front-ends easily).
However, this could easily mean the downfall of some common functionality without extra work (e.g., logging into a website).

- [ ] Brick

  - [ ] ``<div>`` and minimal CSS layouts
  - [ ] CSS colors (and maybe a few CSS3 transitions)
  - [ ] enough JS to allow logins to prominent websites
  - [ ] basic security features (DNT, noscript, &c.)
  - [ ] allow extensibility through Lua (probably Haskell, actually)
  - [ ] allow framebuffer display of images (via libsixel? Make it an extension?)

- [ ] Graphical

  - [ ] Wayland
  - [ ] vim-like modal browsing
  - [ ] basic security features (DNT, noscript, adblocking, &c.)
  - [ ] dwb-like control over widget visibility
