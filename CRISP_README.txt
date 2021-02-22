This git repository contains a Hugo based version of the CRISP website. The following include some specifics
for building and deploying this particular website.

The most complicated part of this website deployment is the publications (research papers authored by CRISP members).
Displaying the publications requires maintaining them in a CSL-JSON format, which is the bibliography format supported
by markdown natively.

In order to maintain/generate the CSL-JSON format, you must either directly edit the json file (currently named
crisp_publications.json) in the root of the git repository, or generate the json format from some other format.
Some publication management software allows you to save in CSL-JSON format directly, or you can save in a bibtex
format and generate the json file using pandoc (requires pandoc 2.11 or later). An example for running pandoc to
generate the json file from a bibtex file is:

pandoc -t csljson crisp_publications.bib > crisp_publications.json

Note that maintaining the crisp_publications.bib file is the preferred way of adding/removing publications from
the json file. When a new publication is added, regenerate the json file and commit to the repo and the site will
get rebuilt on the server.