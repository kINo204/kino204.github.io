---
layout: post
title: Instrument-irrelevant Techniques for Improvisation
date: 2026-09-14 13:18 +0800
---
## Color Is All You Need

- Color maps with chord types.
- Inversion of chords hardly change color.

```
\version "2.26.0"

maj = { <c e g> }
min = { <c ees g> }
dim = { <c ees ges> }
aug = { <c e gis> }

majJ = { <c e g b> }
domJ = { <c e g bes> }
minmajJ = { <c ees g b> }
minJ = { <c ees g bes> }
hdimJ = { <c ees ges bes> }
dimJ = { <c ees ges beses> }

test = {
  \transpose c c
  \invertChords 0
  {
    \maj
    \min
    \dim
    \aug
    \majJ
    \domJ
    \minmajJ
    \minJ
    \hdimJ
    \dimJ
  }
}

main = \transpose c g {
  \invertChords 0
}

\score {
  \main
  \midi {}
}
```
