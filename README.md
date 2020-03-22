# Jekyll + Github Pages Boilerplate
Boilerplate for standing up a static site (that isn't a blog and requires more control over markup and styling) with Jekyll and hosted on Github Pages.

## Using the boilerplate

### Dependencies
- Ruby (2.6.5)*
- Bundler (2.0.2)*

_*Versions as of this writing. Versions are't specified anywhere so could be source of annoyance as things update._

### Getting Started

1. Clone the boilerplate and rename local folder.
2. After `cd`-ing into the project, run `bundle install`.
3. Run `jekyll serve` and the site should be visible at `localhost:4000`.
4. Start developing.

## Notes & things to keep in mind

### CSS/SASS
- CSS/SASS structure is based on [GE's Predix design system](https://medium.com/ge-design/ges-predix-design-system-8236d47b0891):
  ```
  _sass
    /basics
    /components
    /principles
    etc...
  ...
  assests
    /css
      main.sass
  ```
  `main.sass` acts a manifest file that is loaded into the default layout.
- By default, `normalize` is imported in the manifest file. This could be moved to a location that compiles and loaded separately.

### Markup
- The main layout is located at `_layouts/default.html`.
- The main layout will use page `title` and `description`, if specified, otherwise will fall back to what is in the data file.
- The main layout does not contain any global wrapping markup layer or class. For a single page, this probably isn't an issue, but be mindful of repeating markup in other pages.

### Data
- *There is a yml file located at `_data/data.yml` that is automatically loaded into the default layout. This contains site title and description, but can be expanded to include other string-y content.

_*Intentionally not using Jekyll's default `site` variable because 1) it feels strange to mix content and config options and 2) the `github-pages` gem seems to be getting in the way (unconfirmed)._

## To-do
- Add default favicon
- Add a 404 page
- Consider global wrapping div or class
- Should probably stub out some JS stuff too
