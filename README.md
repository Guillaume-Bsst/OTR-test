# Page projet OTRetarget

Squelette repris du template Nerfies, via la page
[survival-value-learning](https://simple-robotics.github.io/publications/survival-value-learning/)
du labo, videe de son contenu.

Destination finale : `simple-robotics.github.io/publications/otretarget/`
(chaque page du labo est un dossier autonome, celui-ci s'y depose tel quel).

## Voir la page en local

Double-clic sur `index.html`. Pour que tout se comporte comme en ligne :

    python3 -m http.server -d . 8000    # puis http://localhost:8000

## Ce qui reste a faire

Tous les emplacements sont marques `TODO` dans `index.html` :

- [ ] Auteurs : un bloc `team-member` chacun, photos dans `static/images/authors/`
- [ ] Liens : ID arXiv, depot du code, PDF dans `static/paper/otretarget.pdf`
- [ ] Abstract
- [ ] Video teaser dans `static/videos/`, puis decommenter le bloc TEASER
- [ ] Sections de resultats
- [ ] BibTeX
- [ ] Meta `og:` (apercu au partage) + image `static/images/teaser.png`

## Videos

Les sources sont trop lourdes pour le web. Compression :

    ffmpeg -i entree.mp4 -vf "scale='min(960,iw)':-2" -c:v libx264 -crf 28 \
           -preset slow -an -movflags +faststart sortie.mp4

Repere : la page d'OmniRetarget publie 30 videos pour 31 Mo, soit ~1 Mo piece.

## Licence

Template sous CC BY-SA 4.0. Le credit a Nerfies dans le pied de page est
une obligation de cette licence : ne pas le retirer.
