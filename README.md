# Creative Theme

Creative Theme is a one page portfolio for creatives based on the [original Bootstrap theme](//github.com/IronSummitMedia/startbootstrap-creative) by [David Miller](//github.com/davidtmiller). Noteworthy features of this Hugo theme are several content sections and a responsive portfolio grid with hover effects and full page portfolio item modals.

![Hugo Creative Theme Screenshot](https://raw.githubusercontent.com/digitalcraftsman/hugo-creative-theme/dev/images/screenshot.png)


## Installation

Inside the folder of your Hugo site run:

    $ cd themes
    $ git clone https://github.com/digitalcraftsman/hugo-creative-theme

For more information read the official [setup guide](//gohugo.io/overview/installing/) of Hugo.


## Getting started

After installing the Creative Theme successfully it requires a just a few more steps to get your site running.


### The config file

Take a look inside the [`exampleSite`](//github.com/digitalcraftsman/hugo-creative-theme/tree/master/exampleSite) folder of this theme. You'll find a file called [`config.toml`](//github.com/digitalcraftsman/hugo-creative-theme/blob/master/exampleSite/config.toml).

To use it, copy the [`config.toml`](//github.com/digitalcraftsman/hugo-creative-theme/blob/dev/exampleSite/config.toml) in the root folder of your Hugo site. Feel free to change strings as you like to customize your website.


### Change the hero background

The hero acts as an eye-catcher for your site. So consider to give him a nice background. You just need to replace the [`header.jpg`](//github.com/digitalcraftsman/hugo-creative-theme/blob/master/static/img/header.jpg) at [`static/img`](//github.com/digitalcraftsman/hugo-creative-theme/tree/master/static/img) with your own. But it's important that you use the same filename.


### Add your services

This section should show your capabilities and skills. You can change the services under  at `[params.services.list]` in the [`config.toml`](//github.com/digitalcraftsman/hugo-creative-theme/blob/dev/exampleSite/config.toml).

All icons using Fontawesome's icon font. Look at the website of [Fontawesome](//fortawesome.github.io/Font-Awesome/icons/) for more icons. The icons are represented by their corresponding CSS class. A skill is defined like this example:

```toml
[[params.services.list]]
    icon = "fa-diamond"
    title = "Sturdy Templates"
    description = "Our templates are updated regularly so they don't break."
```

### Create your portfolio

Beside the config file, there is in `data` another subfolder called [`projects`](//github.com/digitalcraftsman/hugo-creative-theme/tree/master/exampleSite/data/projects) which hosts the files that will appear as your projects in the portfolio section. Such a project file might look like [this one](//github.com/digitalcraftsman/hugo-creative-theme/blob/dev/exampleSite/data/projects/2014-07-05-project-1.yaml) written in YAML:

```yaml
title: Project Title
date: 2017-10-13
img: projectImage.jpg
link: "https://linkto.project"
category: Web Development
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
```

Copy the folder [`projects`](//github.com/digitalcraftsman/hugo-creative-theme/tree/master/exampleSite/data/projects) inside the `data` folder in the **root** directory of your site. Let's make some changes to show your work.

Furthermore, you can use Markdown syntax for URLs like here `[text](//url.to/source)` in the description.

To give your projects an image, save those under [`static/img/portfolio`](//github.com/digitalcraftsman/hugo-creative-theme/tree/master/static/img/portfolio). The dimensions should be 650 x 350 pixels. Don't forget to set the **filename** under 'img' in your project.

### Blog

This theme has been extended to feature a blog. Within the config file, the blog can be enabled/disabled by uncommenting/commenting the `params.blog` option and it's options.

Specific features can be enabled and disabled via the config:

- `showHomeSection` - Shows the blog section on the homepage. (Default: `true`.)
- `showHomePosts` - Shows the first 4 latest posts within the blog section. (Default: `true`.)
- `showHomePostExcerpts` - Show post excerpts on the homepage. (Default: `true`.)

Newly created posts look like this:

```markdown
date: 2017-10-11T03:14:31-04:00
title: "Hello World, This is My First Post!"
description: "This is my very first post on the blog."
author: "Your Name"
featured_image: "/images/post-featured-image.jpg"
draft: true
---
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vel enim aliquid dicta ullam in repellendus amet perspiciatis adipisci architecto obcaecati sit voluptas ipsam, deleniti neque placeat tenetur cum tempore velit...
```

On the blog article pages, the header will be filled in with the `featured_image` link. If it's empty, it defaults to a solid color.

To let blog posts be published just set the `draft` meta tag to false.

Although the blog can be "disabled" on the front-end, it can't be completely disabled. It will be hidden, but it's still reachable via direct links. This is a limitation of Hugo itself, unfortunately. Until the ability to enable/disable sections is built in, this will continue to be a limitation.

### Blog Pagination

The main blog page has a pagination function to only show a certain number of posts today. This can be found within the `config.toml` file in the `Pagination` property. For the purposes of the example site it's set to 3. However, this value can be modified to show any number of posts per page.
### Footer Copyright and Links

The footer copyright mark uses the automatic current year and `name` parameter set in `config.toml` to generate the statement. This functionality can be changed in the `footer.html` partial template.

Footer links are generated the same way the primary navigation links are. To extend it, just modify the parameters under the `params.footer.nav` parameter in `config.toml`. The typical structure for it is as such (where `name` is the name of the link):

```markdown
[params.footer.nav.name]
text = "Display Text"
link = "https://link.address"
```

Once it's been added to the config, it must also be added to the `footer.html` partial within the list contained within the `footer__links` div, using the following structure:

```markdown
{{ if and .Site.Params.footer.nav .Site.Params.footer.nav.name }}
<li><a href="{{ .Site.Params.footer.nav.name.link }}">{{ .Site.Params.footer.nav.name.text }}</a></li>
{{ end }}
```
### Nearly finished

In order to see your site in action, run Hugo's built-in local server. 

    $ hugo server

Now enter [`localhost:1313`](https://localhost:1313) in the address bar of your browser.


## Contributing

Did you found a bug or got an idea for a new feature? Feel free to use the [issue tracker](//github.com/digitalcraftsman/hugo-creative-theme/issues) to let me know. Or make directly a [pull request](//github.com/digitalcraftsman/hugo-creative-theme/pulls).

Please create a separate branch for your pull request.


## License

This theme is released under the Apache License 2.0 For more information read the [license](//github.com/digitalcraftsman/hugo-creative-theme/blob/master/LICENSE).


## Acknowledgements

Thanks to 

- [Steve Francia](//github.com/spf13) for creating Hugo and the awesome community around the project
- [David Miller](//github.com/davidtmiller) for creating the original theme
