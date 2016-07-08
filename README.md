# Polymer Base Theme for Drupal

`Polymer` namespace is already taken on d.o. New name candidate: `Monomer`.

## Installation procedure
  - Download this theme.
  - Run `bower install` in the downloaded theme.

## Development guides
[Development](docs/dev.md)

## Warning
According to latest spec, `<content>` element is [being deprecated](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) in favor of `<slot>`. However, Polymer still uses `<content>` and there is no clear documentation about `<slot>`.
For the time being we will use `<content>` but need to watch closely at updates in Polymer.

## Porting progress
 - pager.html.twig
 - breadcrumb.html.twig
 - node.html.twig
 - status-messages.html.twig
 - views-view.html.twig

## Reusable Components
 - Grids
   - grid-row
   - grid-column
   - grid-cell
 - Tabs

## Simplified Variables
Drupal Twig templates has a lot of obscure and cumbersome variables such as `attributes`, `title_prefix`.

In Polymer base theme we combine and simplify those variables into simple ones for your use in your Polymer element.

However, this could also mean less ability for customization.

To access more raw variables in the original Twig template (which are often big HTML blocs), override the respective Twig template in your sub-theme.


## Tutorial: Creating a sub-theme
 - Coming soon
