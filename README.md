# Monomer (Polymer Base Theme for Drupal)
Monomer is a Drupal 8 base theme that allows theme builders to use Polymer elements in their theme design. 

## Table of contents
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Dependencies](#dependencies)
- [Installation procedure](#installation-procedure)
- [Demos](#demos)
- [Getting Started Guide](#getting-started-guide)
- [Tutorial: Building a simple studio site](#tutorial-building-a-simple-studio-site)
- [Warning](#warning)
- [Pre-built Reusable Components](#pre-built-reusable-components)
- [Development specs](#development-specs)
- [Simplified Variables](#simplified-variables)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Dependencies
 - [Twig Polymer Extension](https://github.com/ztl8702/twig_polymer/tree/dev) module.
 - Node.js and Bower.
 
## Installation procedure
  - Install [Twig Polymer Extension](https://github.com/ztl8702/twig_polymer/tree/dev).
  - Download this theme.
  - Run `bower install` in the downloaded theme.

## [Demos](https://github.com/ztl8702/polydemo/tree/polymer)

## [Getting Started Guide](docs/guide.md)

## [Tutorial: Building a simple studio site](docs/tutorial.md)

## Warning
According to latest spec, `<content>` element is [being deprecated](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) in favor of `<slot>`. However, Polymer still uses `<content>` and there is no clear documentation about `<slot>`.
For the time being we will use `<content>` but need to watch closely at updates in Polymer.

## Pre-built Reusable Components
_(Prefix `mm-` stands for `Monomer`.)_

 - grid
   - [mm-grid-row](my-elements/mm-grid/mm-grid-row.html)
   - [mm-grid-column](my-elements/mm-grid/mm-grid-column.html)
   - [mm-grid-item](my-elements/mm-grid/mm-grid-item.html)
 - [mm-tabs](my-elements/mm-tabs/mm-tabs.html)
 - mm-node
   - [mm-node-full](my-elements/mm-node/mm-node-full.html)
 - [mm-pager](my-elements/mm-pager/mm-pager.html)
   - [mm-pager-item](my-elements/mm-pager/mm-pager-item.html)
 - views
   - [mm-views-wrapper](my-elements/mm-views/mm-views-wrapper.html)
   - [mm-views-exposed-filters](my-elements/mm-views/mm-views-exposed-filters.html)
 - [mm-region](my-elements/mm-region/mm-region.html)
 - [mm-breadcrumb](my-elements/mm-breadcrumb/mm-breadcrumb.html)
 - [mm-status-message](my-elements/mm-status-message/mm-status-message.html)

## Development specs
[Development](docs/dev.md)

## Simplified Variables
Drupal Twig templates has a lot of obscure and cumbersome variables such as `attributes`, `title_prefix`.

In Polymer base theme we combine and simplify those variables into simple ones for your use in your Polymer element.

However, this could also mean less ability for customization.

To access more raw variables in the original Twig template (which are often big HTML blocs), override the respective Twig template in your sub-theme.

