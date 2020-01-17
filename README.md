# Personal Website v2

A retrofit dark version of [Type on Strap](https://github.com/sylhare/Type-on-Strap) theme for [Jekyll](https://jekyllrb.com).

**Note:** This is not intended to be a comprehensive version and it's intended for personal use. If you do want to try using it, refer to the original [Type on Strap](https://github.com/sylhare/Type-on-Strap) repo for information

* Responsive design
* Portfolio page for projects* _(TODO: Reinstate after renovate)_
* Tags compatibility _(TODO: Cleanup from stray pages)_
* Bootstrap : [Get Bootstrap](http://getbootstrap.com/)
* Search feature : [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search)
* Math Rendering : [KateX](https://github.com/Khan/KaTeX)
* Nice fonts : [Font Awesome](https://fontawesome.com/), [Inter](https://rsms.me/inter/)
* SEO Tags : [Jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag)
* Syntax Highlighting: Easily customisable [Base16](https://github.com/chriskempson/base16)
* ~~Free of rights images from [pexels](https://www.pexels.com/)~~ _(TODO: Cleanup old pages)_

## Table of Contents

1. [To-Do](https://github.com/EndyPremier/endypremier.github.io#To-Do)
2. [Usage](https://github.com/EndyPremier/endypremier.github.io#Usage)
3. [Structure](https://github.com/EndyPremier/endypremier.github.io#Structure)
4. [License](https://github.com/EndyPremier/endypremier.github.io#License)

## To-Do

- [ ] Reinstate Portfolio section after renovation.
- [ ] Cleanup Tags from stray pages.
- [ ] Cleanup Old Pages and other dependent images.
- [ ] _Maybe(?)_ deprecate the Gallery section.

## Usage

1. Fork and clone this [repo](https://github.com/EndyPremier/endypremier.github.io): `git clone hhttps://github.com/EndyPremier/endypremier.github.io.git`
2. Install [Jekyll](https://jekyllrb.com/docs/installation/): `gem install jekyll`, check [from the old repo](https://github.com/Sylhare/Type-on-Strap/issues/1) if you have a problem.
3. Install the theme's dependencies: `bundle install`
4. Customize the theme
	- Github Page: [update `_config.yml`](https://github.com/Sylhare/Type-on-Strap#site-configuration)
5. Run the Jekyll server: `bundle exec jekyll serve`

## Structure

Here are the main files of the template

```bash
jekyll-theme-basically-basic
├── _includes	               # theme includes
├── _layouts                   # theme layouts (see below for details)
├── _portfolio	               # collection of article to be populated in the portfolio page
├── _posts                     # Blog posts
├── _sass                      # Sass partials
├── assets
|  ├── js	               # theme javascript, Katex, jquery, bootstrap, jekyll search,
|  ├── css                     # isolated Bootstrap, font-awesome, katex and main css
|  ├── fonts		       # Font-Awesome, and other fonts
|  └── img		       # Images used for the template
├── pages
|   ├── 404.md		       # To be displayed when url is wrong
|   ├── about.md               # About example page
|   ├── gallery.md             # Gallery page for your photos
|   ├── portfolio.md	       # Portfolio page for your projects
|   ├── search.html	       # Search page
|   └── tags.md                # The tag page
├── _config.yml                # sample configuration
├── _data.yml                  # extra configuration
└── index.html                 # sample home page (blog page paginated)
```

## License

The original theme, the Font Awesome font, and the extra components are under [The MIT License (MIT)](https://raw.githubusercontent.com/Sylhare/Type-on-Strap/master/LICENSE) where as the Inter font was is under the [SIL Open Font License](https://choosealicense.com/licenses/ofl-1.1/).
