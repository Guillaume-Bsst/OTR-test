# OTRetarget project page

Skeleton taken from the Nerfies template, through the lab's
[survival-value-learning](https://simple-robotics.github.io/publications/survival-value-learning/)
page, emptied of its content.

Final destination: `simple-robotics.github.io/publications/otretarget/`
(every lab page is a self-contained folder, this one drops in as is).

## Viewing the page locally

Double-click `index.html`. For everything to behave as it does online:

    python3 -m http.server -d . 8000    # then http://localhost:8000

## What is left to do

Every spot is marked `TODO` in `index.html`:

- [ ] Authors: one `team-member` block each, photos in `static/images/authors/`
- [ ] Links: arXiv ID, code repository, PDF in `static/paper/otretarget.pdf`
- [ ] Abstract
- [ ] Teaser video in `static/videos/`, then uncomment the TEASER block
- [ ] Result sections
- [ ] BibTeX
- [ ] `og:` meta tags (share preview) + `static/images/teaser.png` image

## Videos

The sources are too heavy for the web. Compression:

    ffmpeg -i input.mp4 -vf "scale='min(960,iw)':-2" -c:v libx264 -crf 28 \
           -preset slow -an -movflags +faststart output.mp4

Benchmark: the OmniRetarget page publishes 30 videos for 31 MB, i.e. ~1 MB each.

## License

Template under CC BY-SA 4.0. The Nerfies credit in the footer is a requirement
of that license: do not remove it.
