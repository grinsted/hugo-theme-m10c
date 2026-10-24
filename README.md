# m10c theme

![Intro](https://github.com/vaga/hugo-theme-m10c/blob/master/images/cover.png)

A Hugo minimalistic theme for bloggers

Main features:

- Fully responsive
- Twitter Cards, Open Graph, Disqus and Google Analytics supported (see Hugo docs)
- Customizable colors
- Customizable picture and description
- Customizable menu on sidebar
- Customizable social media links on sidebar
- Optimized for performance 100/100 on Lighthouse
- All Feather and Simple Icons icons included

## Getting started

### Installation

Create a new Hugo site:
```bash
$ hugo new site [path]
```

Clone this repository into `themes/` directory:
```bash
$ cd [path]
$ git clone https://github.com/vaga/hugo-theme-m10c.git themes/hugo-theme-m10c
```

Add this line  in the `config.toml` file:
```toml
theme = "hugo-theme-m10c"
```

### Configuration

In your `config.toml` file, define the following variables in `params`:

- `author`: Name of the author
- `description`: Short description of the author
- `avatar`: Path of file containing the author avatar image
- `menu_item_separator`: Separator between each menu item. HTML allowed (default: " - ")
- `favicon`: Absolute path of your favicon.ico file (default: "/favicon.ico")

To add a menu item, add the following lines in `menu`:

```
[[menu.main]]
  identifier = "tags"
  name = "Tags"
  url = "/tags/"
```

[Read Hugo documentations](https://gohugo.io/content-management/menus/#readout) for more informations about menu

To add a social link, add the following lines in `params`:

```
[[params.social]]
  icon = "brand-github"
  name = "My Github"
  url = "https://github.com/vaga"
```

To change theme colors, add the following lines in `params`:

```
[params.style]
  darkestColor = "#d35050"
  darkColor = "#212121"
  lightColor = "#f5e3e0"
  lightestColor = "#f5f5f5"
  primaryColor = "#ffffff"
```

If you want the above theme colors, you can see the [exampleSite/config.toml](/exampleSite/config.toml) file.

### Icons

This theme uses two libraries for icons:

- [Feather](https://feathericons.com/) is used for application-related icons.
- [Simple Icons](https://simpleicons.org) is used for brand icons.

To differentiate brand icons from regular ones, the prefix `brand-` is added
to all icons from the Simple Icons library. (e.g., brand-github, brand-x, brand-mastodon...)

### Styling

To override styles using scss, add a file called `_extra.scss` to `[path]/assets/css/`

**Note:** Hugo releases come in two versions, `hugo` and `hugo_extended`. You need `hugo_extended` to automatically compile your scss.

### Math

LaTeX is rendered to HTML with KaTeX at build time, following
[Hugo's mathematics guide](https://gohugo.io/content-management/mathematics/).
No JavaScript is shipped; the KaTeX stylesheet and fonts are served from the
theme's `static/katex/` and only included on pages that contain math.

Hugo does not let themes set `markup` options, so enable the passthrough
extension in your site config:

```toml
[markup.goldmark.extensions.passthrough]
  enable = true
  [markup.goldmark.extensions.passthrough.delimiters]
    block = [['\[', '\]'], ['$$', '$$']]
    inline = [['\(', '\)'], ['$', '$']]
```

Then write `$...$` or `\(...\)` for inline math and `$$...$$` or `\[...\]` for
display math. Drop `['$', '$']` if you write literal dollar signs in prose.
Setting `math: true` in front matter forces the stylesheet onto a page.

## License

This theme is released under the [**MIT**](/LICENSE.md) License.

## Acknowledgements

- [Feather](https://feathericons.com/) - [MIT](https://github.com/feathericons/feather/blob/master/LICENSE)
- [Simple Icons](https://simpleicons.org) - [CC0 1.0](https://github.com/simple-icons/simple-icons/blob/develop/LICENSE.md)
