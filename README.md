# Monomer (Polymer Base Theme for Drupal)

`Polymer` namespace is already taken on d.o. New name candidate: `Monomer`.

## Installation procedure
  - Install [twig_polymer](https://github.com/ztl8702/twig_polymer/tree/dev).
  - Download this theme.
  - Run `bower install` in the downloaded theme.

## [Demo](https://github.com/ztl8702/polydemo/tree/polymer)

## Development guides
[Development](docs/dev.md)

## Warning
According to latest spec, `<content>` element is [being deprecated](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) in favor of `<slot>`. However, Polymer still uses `<content>` and there is no clear documentation about `<slot>`.
For the time being we will use `<content>` but need to watch closely at updates in Polymer.

## Reusable Components
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

## Simplified Variables
Drupal Twig templates has a lot of obscure and cumbersome variables such as `attributes`, `title_prefix`.

In Polymer base theme we combine and simplify those variables into simple ones for your use in your Polymer element.

However, this could also mean less ability for customization.

To access more raw variables in the original Twig template (which are often big HTML blocs), override the respective Twig template in your sub-theme.


## Tutorial: Creating a sub-theme
 - See the [guide](docs/guide.md).