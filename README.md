# README

Sources for the Fondata, LLC website

Fondata's website is a static site, hosted on Github Pages. This site is created with Quarto. Quarto places the website files in _site/. To work with Github pages, these files are committed to the 'publish' branch by first copying them into the docs/ directory before commiting the publish branch. 

# Pushing changes to the website
Assume updates have been committed to 'main',
Here's the history of a commit-to-publish workflow:

$ quarto render
$ git checkout publish
$ git pull
$ git merge main
$ cp -R _site/* docs/
$ git push

# Optionally update main to be consistent with publish
$ git checkout main
$ git add -A
$ git commit -m'merged changes from main'
$ git push
