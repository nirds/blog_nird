####Blogging with Octopress

The [documentation](http://octopress.org/docs/blogging/),
the [NIRD blog repo](https://github.com/nirds/blog_nird),
the [Heroku repo](https://dashboard.heroku.com/apps/nird-blog/settings)

Our blog is using Ruby 2.0.0.

Clone the repo locally. Run 'rake new_post["Bradley Promoted to CFO"]' (your title goes within ""). Open the generated file, which should be in 'source/_posts'. Update the opening chunk of yaml as appropriate. Be sure to add an 'author: Your Name' attribute. We don't have a specific list of categories yet, so just make some stuff up or use ones that have been used before.

Under the ------ that closes the yaml, write your post in markdown. If you'd like to preview it, run 'rake generate' then 'rake preview'. It will then be available at localhost:4000.

When you're all done, commit and push to the Github and Heroku repos.

Bam! Your post is live and you're a superhero.

*not actually a superhero.

If you'd like to make changes to the styling, do so in the 'sass/custom/_styles.scss' file. It should override all other style sheets. To make those changes actually stick, after editing the file, run 'rake clean' then 'rake generate' to recompile the sass. This doesn't always actually work, but usually. [Documentation.](http://octopress.org/docs/theme/styles/)

We have a [theme](https://github.com/cherimarie/cleanpress_custom) installed that Cheri forked from someone else so she could customize it. It's pretty sweet. If you'd like to change the theme, Google up a good one, then use their provided instructions to install it. Do NOT make changes to files within the .themes/ directory of the blog repo.

Godspeed!

## What is Octopress?

Octopress is [Jekyll](https://github.com/mojombo/jekyll) blogging at its finest.

1. **Octopress sports a clean responsive theme** written in semantic HTML5, focused on readability and friendliness toward mobile devices.
2. **Code blogging is easy and beautiful.** Embed code (with [Solarized](http://ethanschoonover.com/solarized) styling) in your posts from gists, jsFiddle or from your filesystem.
3. **Third party integration is simple** with built-in support for Pinboard, Delicious, GitHub Repositories, Disqus Comments and Google Analytics.
4. **It's easy to use.** A collection of rake tasks simplifies development and makes deploying a cinch.
5. **Ships with great plug-ins** some original and others from the Jekyll community &mdash; tested and improved.

