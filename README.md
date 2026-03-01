# BOSTON GAMEDEV WEEK

[![Deploy Jekyll with GitHub Pages dependencies preinstalled](https://github.com/YWainczak/bostonIndies/actions/workflows/jekyll-gh-pages.yml/badge.svg)](https://github.com/YWainczak/bostonIndies/actions/workflows/jekyll-gh-pages.yml)

The official Boston Gamedev Week website.

Written using HTML, SCSS, and Liquid. Compiled by Github Page's version of Jekyll.

Google Font Icon settings
Weight: 400
Grade: 0
Optical Size: 48px
Style:
 - Material Symbols
 - Rounded

To build locally, use `bundle exec jekyll serve`.

"To make things live, once you've got everything created, you use rvm. (Ruby Version Manager.) I'm on Ruby 3.3.7. You use bundle exec jekyll serve to spin up locally. That and the command bundle exec jekyll server create the site in a _site folder. So, because I had to write a piece of code to check if dates are in a certain range, you have to manually push the site. After you commit to main and push that (not including the _site folder), you have to switch to the gh-pages branch. Then I just cp -r _site/* . and git add . and then git commit -m "some message" and then git push origin gh-pages." - Chad
