# Monomer (Polymer Base Theme for Drupal)
Monomer is a Drupal 8 base theme that allows theme builders to use Polymer elements in their theme design. 

## Status
The development of this theme is **put on hold** as the author is focused on [Web Components Renderer](http://github.com/ztl8702/wcr).

## Table of contents
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Dependencies](#dependencies)
- [Installation](#installation)
- [Demos](#demos)
- [Documentation](#documentation)
- [Development specs](#development-specs)
- [Simplified Variables](#simplified-variables)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Dependencies
 - [Twig Polymer Extension](https://github.com/ztl8702/twig_polymer/tree/dev) module.
 - Node.js and Bower.
 
## Installation
  - Install [Twig Polymer Extension](https://github.com/ztl8702/twig_polymer/tree/dev).
  - Download this theme.
  - Run `bower install` in the downloaded theme.

## Demos
 - [Basic examples](https://github.com/ztl8702/polydemo/tree/bartik)
 - [Animations](https://github.com/ztl8702/polydemo/tree/polymer)
 - [Replicate Bartik theme](https://github.com/ztl8702/polydemo/tree/bartik-replica)
 - [Full site example: Studio](https://github.com/ztl8702/polymer-demo)

## Documentation
 - [Getting Started Guide](docs/guide.md)
 - Tutorials:
   - [Tutorial: Styling buttons](docs/tutorial-button.md)
   - [Tutorial: Building a simple studio site](docs/tutorial.md)
 - [Pre-built Reusable Components](docs/prebuilt-elements.md)
 
## Development specs
[Development](docs/dev.md)

## Simplified Variables
Drupal Twig templates has a lot of obscure and cumbersome variables such as `attributes`, `title_prefix`.

In Polymer base theme we combine and simplify those variables into simple ones for your use in your Polymer element.

However, this could also mean less ability for customization.

To access more raw variables in the original Twig template (which are often big HTML blocs), override the respective Twig template in your sub-theme.

