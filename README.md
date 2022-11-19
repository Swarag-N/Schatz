# Schatz

Simple and minimal Jekyll blog. 
Forked from [Gesko](https://github.com/P0WEX/Gesko).

This is a code repository of Solutions to most of the topics in DSA from basic to advanced from reputed websites.

### Features

- [x] Responsive Design
- [x] Dark/Ligh theme 🌗
- [x] Inline CSS
- [x] Anchor headings
- [x] Tags & Tag pages 
- [x] 404 page (Customized)
- [x] Robots.txt 🤖
- [x] Atom & Json feeds 📡
- [x] Sass 
- [x] About page, with Timeline! 🗣️
- [x] PageSpeed and w3Validator tests PASSED ✔️
- [x] Search bar 🔎
- [x] Next & Previous Post ⏮️ ⏭️
- [x] Pagination Support

## Installation

Run local server:

```bash
$ git clone https://github.com/Swarag-N/Schatz/
$ cd Schatz
$ bundle install
$ bundle exec jekyll build
$ bundle exec jekyll serve
```

Navigate to `localhost:4000`. You're Welcome, Fork and be Stargazer.
If you want to upload it to Github Pages, remember to update the `_congif.yml` and if you are going to upload in a repo called yournickname.github.io, remember to update the `{{ site.baseurl }}` to `{{ site.url }}` .
Note that there is also a gtag in the [`_layouts/default.html`](https://github.com/P0WEX/Gesko/blob/6776e4afc384dc3d50ce2001715929c8e70a914c/_layouts/default.html#L9), you should remove it.

To create new tag, create a folder in `tag/` with the name of the new one. In this folder add an `index.html` file and just add this header:
```
---
layout: tag
tag: yourNewTag
---
```
Then build again and you're ready!!

## Contributing

Yeaaa feel free to open a pull request.


If you see any typos or formatting errors in a post, or want to helping reduce backlogs or any other issue that needs to be addressed, please do not hesitate to open a pull request and fix it!, please read [contributing](./CONTRIBUTING.md) before PR.

## License

This project is open source and available under the [MIT License](LICENSE.md).