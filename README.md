# OTRetarget project page

One self-contained folder, built on the Nerfies template through the lab's
[survival-value-learning](https://simple-robotics.github.io/publications/survival-value-learning/)
page. It drops into `simple-robotics.github.io/publications/otretarget/` as is.

## Viewing it locally

    python3 -m http.server -d . 8000    # then http://localhost:8000

## Still to fill in

- **arXiv identifier.** `XXXX.XXXXX` sits in three places: the arXiv button, and
  `eprint` and `url` in the BibTeX entry.
- **Code link.** The GitHub button carries the `code-soon` class, which greys it
  out and shows a tooltip. Give it an `href` and drop the class.
- **Page URL.** `og:url` and `main.tex`'s `\blfootnote` must agree, both
  lowercase: GitHub Pages serves paths case-sensitively.

## Where the assets come from

- `static/images/pipeline-icra-v11.jpg` — figure 2 of the ICRA submission,
  page 2 at 300 dpi, trimmed to the figure. Cut it from the submitted PDF, not
  from a `main.pdf` in the repo: the two builds do not write the same
  subscripts. The file is named after its build, so a new figure is a new URL
  that no cache can answer for.
- `static/videos/witness_solve.mp4` — the four witness families of
  `--witness-solve`, 70% speed, cropped 16:9 out of the 1920x1080 rush.
- `static/videos/floorlamp_v2.mp4`, `crawl.mp4` — rebuilt by
  `site_clips.sh`, which holds the exact cameras and labels.

Compression for the web, the same for every clip:

    ffmpeg -i input.mp4 -vf "scale='min(960,iw)':-2" -c:v libx264 -crf 28 \
           -preset slow -an -movflags +faststart output.mp4

For scale: the OmniRetarget page publishes 30 videos in 31 MB.

## What is loaded, and why

`bulma.min.css` for the layout, `fontawesome.all.min.js` for the icons, which
it swaps into inline SVG, and academicons from a CDN for the arXiv glyph. The
Font Awesome stylesheet is deliberately absent: it asks for webfonts this
folder does not ship, and the script covers every icon on the page. The Google
Analytics tag belongs to the lab and stays, since the page is published there.

## License

Template under CC BY-SA 4.0. The Nerfies credit in the footer is a requirement
of that license: do not remove it.
