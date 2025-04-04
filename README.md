# Jekyll custom snippet

This repo demonstrates how to get custom snippets up and running in Jekyll. Refer to [these docs](https://cloudcannon.com/documentation/articles/snippets-reference/#key-values-parser).

`site/collections/_posts/2018-11-13-that-which-does-not-kill-us-makes-us-stronger.markdown`

```markdown
Natura sic ab iis investigata est, ut nulla pars caelo, mari, terra, ut poëtice loquar, praetermissa sit. Eadem nunc means adversum te oratio est. Mihi quidem Homerus huius modi quiddam vidisse videatur in nis.

{% include snippets/image.html url="http://jekyllrb.com" max-width="200px" file="/images/image-example-1.jpg" alt="Tropics" caption="This is a custom snippet." %}


```

`cloudcannon.config.yml`

```yaml
_snippets:
  image:
    snippet: '{% include snippets/image.html [[arguments]] %}'
    params:
      arguments:
        parser: key_values
        options:
          models:
            - editor_key: url
            - editor_key: max-width
            - editor_key: file
            - editor_key: alt
            - editor_key: caption
          format:
            string_boundary:
              - '"'
            root_value_delimiter: '='
    _inputs:
      caption:
        type: textarea
      file:
        type: image
```

`site/_includes/snippets/image.html`

```html
<figure>
   <a href="{{ include.url }}">
   <img src="{{ include.file }}" style="max-width: {{ include.max-width }};"
      alt="{{ include.alt }}"/>
   </a>
   <figcaption>{{ include.caption }}</figcaption>
</figure>
```


# Vonge

Vonge is a Personal portfolio/blog site template for Jekyll. Browse through a [live demo](https://jazzed-kale.cloudvent.net/).
Increase the web presence of your brand with this configurable theme.

![Vonge template screenshot](_screenshot.png)

Vonge was made by [CloudCannon](http://cloudcannon.com/), the JAMStack Cloud CMS.
The component library is built and maintained for use with [Bookshop](https://github.com/cloudcannon/bookshop/)

Find more templates, themes and step-by-step Jekyll tutorials at [CloudCannon Community](https://cloudcannon.com/community/).

[![Deploy to CloudCannon](https://buttons.cloudcannon.com/deploy.svg)](https://app.cloudcannon.com/register#sites/connect/github/CloudCannon/vonge-jekyll-bookshop-template)

## Features

* Component library for website building
* Fully configurable Website
* Pre-built pages
* Pre-styled components
* Blog
* Category pages
* Testimonials
* Portfolio
* Live editing with [CloudCannon](http://cloudcannon.com/)
* Optimised for editing in [CloudCannon](http://cloudcannon.com/)
* Search engine optimisation

## Develop

Vonge was built with [Jekyll](http://jekyllrb.com/) version 4.2.1, but should support newer versions as well.

Install the dependencies for Bookshop:

~~~bash
$ npm install
~~~

Install the Jekyll dependencies with [Bundler](http://bundler.io/):

~~~bash
$ npm run jekyll:install
~~~

Run the website:

~~~bash
$ npm start
~~~


> [!IMPORTANT]
> When running locally, the pagination will not work. Deploy to CloudCannon to see successful pagination. 

