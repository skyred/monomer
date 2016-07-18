# Tutorial: Building a simple studio site with Monomer base theme in Drupal 8

Before reading this, make sure you have read [Getting Started Guide](guide.md)

## Goal
We are building a website like this:

![Studio](animations.gif)

[Live demo](http://monomerdemok87tjp6c5v.devcloud.acquia-sites.com/)

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
  featured_top: 'Featured top'
  breadcrumb: Breadcrumb
  content: Content
  footer: 'Footer'
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
 
## Auto-collapse header

## Front page view with animation

## Content pages


## Drupal-specific tweaks and tricks
