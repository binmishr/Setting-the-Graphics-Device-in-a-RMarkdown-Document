# Setting-the-Graphics-Device-in-a-RMarkdown-Document

The details of the codeset and plots are included in the attached Adobe Acrobat reader (.pdf) file in this repository. 
You need to download the same to view the contents. There are referrals to other contents in BLUE colour also to follow.

A Brief Introduction
======================

Saving R Graphics across OSs Documentation : https://www.jumpingrivers.com/blog/r-graphics-cairo-png-pdf-saving/

Load the Library Knitr from CRAN site with command Library(Knitr). Knitr Documentation Reference : https://yihui.org/knitr/options/#plots

For saving R graphics, it became obvious that achieving consistent graphics across platforms or even saving the “correct” graph on a particular OS was challenging. Getting consistent fonts across platforms often failed, and for the default PNG device under Windows, anti-aliasing was also an issue. The conclusion of the post was to use

    1.grDevices::cairo_pdf() for saving PDF graphics or
    2.grDevices::png(..., type = "cairo_png") for PNGs or alternatively
    3.the new ragg package.

In many workflows, function calls to graphic devices are not explicit. Instead, the call is made by another package, such as knitr.

When kniting an Rmarkdown document, the default graphics device when creating PDF documents is grDevices::pdf() and for HTML documents it’s grDevices::png(). As we
demostrated, these are the worst possible choices!
