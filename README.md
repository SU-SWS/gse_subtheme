# [GSE Subtheme](https://github.com/SU-SWS/gse_subtheme)

## Description

GSE Subtheme is a Stanford sub-theme, and is a child theme of the Stanford Basic theme.

## Customizations

This theme's changes from a stock Stanford Basic subtheme are limited to the local footer:

- **Local footer styling**: `src/scss/components/local-footer/_local-footer.scss` recolors the local footer (background, text, links, and social icons) for the GSE dark footer treatment.
- **Local footer lockup override**: The local footer always shows the GSE logo-only lockup, regardless of what's configured on the site's Local Footer settings page. This requires two pieces working together:
  - `gse_subtheme_preprocess_config_pages__stanford_local_footer()` in `gse_subtheme.theme` sets the lockup variables (logo path, lines, lockup option).
  - `templates/config-pages--stanford-local-footer.html.twig` overrides `stanford_basic`'s template of the same name, because that template reads the lockup values directly off the site's `config_pages` fields rather than from preprocess variables. If `stanford_basic` changes this template upstream, diff it against this override and re-apply.

## Documentation
See subtheming guides and best practices here: 
https://devguide.sites.stanford.edu/front-end/drupal/sub-themes 

## Installation
1. Review the documentation link above for best practices, particularly the Do's and Don't's sections.
2. Fork or download this theme repository. 
3. Change all theme file names from including "stanford_starter" to including the machine name of your theme.
4. Run a search and replace throughout the theme files to replace "stanford_starter" with the machine name of your theme.
5. Add any specific brand colors you need (in addition to the decanter colors that are already available) to src/scss/utilities/variables/_colors.scss. 
See all the colors already available through decanter: https://decanter.stanford.edu/page/brand-design-elements-color/ 
6. If desired, add font settings if you need to override and use fonts other than decanter fonts ( https://decanter.stanford.edu/page/brand-design-elements-typography/ ) [link],
by defining a font library in the themename.libraries.yml file.
7. If desired, add button mixins in src/scss/utilities/mixins/_buttons.scss with your button styles and then reference them and use them in src/scss/theme/_button.scss.
8. If desired, add cta and link mixins in src/scss/utilities/mixins/_cta.scss with your button styles and then reference them and use them in src/scss/theme/_cta.scss.
9. If you want to skin or theme a component, like a paragraph, create a _mycomponent.scss file in src/scss/components folder. Consider using a subfolder like 'cards' or 'banners' if applicable.

## Configuration

Nothing special needed. Install, enable, and set as the default active theme.

## Developer

If you wish to develop on this theme you will most likely need to compile some new css. Please use the sass structure provided and compile with the sass compiler packaged in this theme. To install:

```
yarn install
```
After you've made a change you want to see processed, you can run:
```
yarn build
```
This will process scss, js, and asset files, preparing them from the src directory to the dist directory.

```
yarn watch
```
This will watch the scss files and compile them upon saving.

## Contribution / Collaboration

You are welcome to contribute functionality, bug fixes, or documentation to this theme. If you would like to suggest a fix or new functionality you may add a new issue to the GitHub issue queue or you may fork this repository and submit a pull request. For more help please see [GitHub's article on fork, branch, and pull requests](https://help.github.com/articles/using-pull-requests)
