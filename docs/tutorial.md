# Tutorial: Building a simple studio site with Monomer base theme in Drupal 8

Before reading this, make sure you have read [Getting Started Guide](guide.md).

## Goal
We are building a website like this:

![Studio](animations.gif)

Check out the [Live demo](http://monomerdemok87tjp6c5v.devcloud.acquia-sites.com/) or [Code repo](https://github.com/ztl8702/polymer-demo).


## Setting up folder structure
 - Create a `studio` folder in `themes` folder of your Drupal 8 installation.
 - Create a `studio.info.yml` file in your theme folder.
```yaml
name: Studio
type: theme
core: 8.x
base theme: monomer
description: 'A demo studio theme using Polymer base theme.'
package: Web Components
regions:
  header: Header
  primary_menu: 'Primary menu'
  highlighted: Highlighted
  content: Content
libraries-override:
  classy/base: false
```
- Run `bower init`, follow the instructions.
- Your theme folder structure should look like this:
```
├── bower_components
│   └── ... (3rd party Web Components, installed by bower)
├── bower.json
├── my-elements
│   └── ... (Custom built Polymer elements)
├── studio.info.yml
├── studio.libraries.yml
├── studio.theme
└── templates
    └── ...
```
 - Optionally, you can add a `.gitignore` file and exclude `bower_components` from your repository.

## Drupal Configuration

The site we are creating has two content types. To keep things simple, we are going to configure them as: 
  - Event (machine name: `event`). 
    - Body field
    - Image field
  - Basic Page (machine name: `page`).
    - Body field
    - Image field

We also want to put the Main Navigation menu in the region `Primary menu`.

For the front page, we are going to modify the `frontpage` view to displaying 12 nodes maximum.

## An anatomy of page layout
![Structure](tutorial-0.png)

We are going to create 3 custom Polymer elements:
 - `<my-page>`: Overall page wrapper.
 - `<my-home>`: Frontpage view.
 - `<my-node>`: Displaying node content.

Our `my-elements/` folder will eventually look like this:
```
my-elements/
├── my-home
│   ├── my-home.html
│   └── my-home-styles.html
├── my-node
│   ├── my-node.html
│   └── my-node-styles.html
└── my-page
    ├── image
    │   └── techyizu_header_bg.jpg
    ├── my-page.html
    └── my-page-styles.html
```
## Step 1: set up basic page layout
Override the template `page.html.twig` to use our `<my-page>` element.

`templates/page.html.twig`:

```twig
{% polymer import "my-page/my-page.html" %}
<div class="layout-container">
  <my-page>
    <header role="banner">
      {{ page.header }}
    </header>
    {{ page.primary_menu }}
    {{ page.highlighted }}
    <a id="main-content" tabindex="-1"></a>{# link is in html.html.twig #}
    <my-app-content>
      {{ page.content }}
    </my-app-content>{# /.layout-content #}
    {% if page.footer %}
      <footer role="contentinfo">
        {{ page.footer }}
      </footer>
    {% endif %}
  </my-page>
</div>{# /.layout-container #}
```

`my-elements/my-page/my-page.html`:

```html
...
<template>
  <content select="paper-tabs">
  </content>
  <content select="my-app-content"></content>
</template>
...
```
## Step 2: Auto-collapse header
We are going to use `<paper-scroll-header-panel>` element. First install it via Bower.

```
> bower install --save PolymerElements/paper-scroll-header-panel
```

`my-elements/my-page/my-page.html`:

```html
...
<paper-scroll-header-panel condenses keep-condensed-header header-height="128" condensed-header-height="48">

  <paper-toolbar id="toolbar">
    <div class="spacer"></div>
    <div class="middle indent bottom-text">
      <div class="title">[[ siteName ]]</div>
      <div class="subtitle">[[ siteSlogan ]]</div>
    </div>
    <content select="paper-tabs">
    </content>
  </paper-toolbar>

  <div class="content">
   <content select="my-app-content"></content>
  </div>

</paper-scroll-header-panel>
...
```

> Note that we used `[[ siteName ]]` and `[[ siteSlogan]]` in our **DOM template**. To display site name and site slogan, we first need to write a preprocess function:
>
> `studio.theme`:
>
>```php
>function studio_preprocess_page(array &$variables) {
>  $config = \Drupal::config('system.site');
>  $variables['site_name'] = $config->get('name');
>  $variables['site_slogan'] = $config->get('slogan');
>}
>```
> and pass the variable into the element as attributes:
> `templates/page.html.twig`:
>
>```twig
>  <my-page site-name="{{ site_name }}"
>           site-slogan="{{ site_slogan }}">
>  ...
>```
> then in the Polymer element definition, add this to the `properties` object:
>
> `my-elements/my-page/my-page.html`:
> ```js
> properties: {
>   siteName: String,
>   siteSlogan: String,
>   ...
> }
>```

Add styles accordingly (see [code](https://github.com/ztl8702/polymer-demo/themes/studio/my-elements/my-page/my-page-styles.html)).

See also: [`<paper-scroll-header-panel>` docs on Polymer Catalog](https://elements.polymer-project.org/elements/paper-scroll-header-panel)

## Step 3: Front page view with animations

## Step 4: Content pages


## Drupal-specific tweaks and tricks
