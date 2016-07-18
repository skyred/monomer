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

## Anatomy of page layout
![Structure](tutorial-0.png)

We are going to create 3 custom Polymer elements:
 - `<my-page>`: Overall page wrapper.
 - `<my-home>`: Frontpage view.
 - `<my-node>`: Displaying node content.

Set up the following files in `my-elements/`:
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

## Step 2: Auto-collapse header

## Step 3: Front page view with animation

## Step 4: Content pages


## Drupal-specific tweaks and tricks
