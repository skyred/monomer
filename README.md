# Polymer Base Theme for Drupal

## Installation procedure
  - Download this theme.
  - Run `bower install` in the downloaded theme.

## (Dev) Naming pattern for variables
 Use this pattern for converting variable names:
 - Twig variable: underscore style. `content_attributes`
 - HTML data attribute: dash style. `content-attributes` or `data-content-attributes`
 - Inside Polymer DOM template: camel case. `contentAttributes`
 - Custom DOM:
   ```
   <div class="author-picture"></div>

   or

   <data-author-picture></data-author-picture>
   ```
   And in DOM template:
   ```
   <content select=".author-picture'>

   or

   <content select="data-author-picture">
   ```

## (Dev) Boolean variable conversion pattern
Twig variable:
```
{{ display_submitted }}
```
Converts to:
```
<element
  {% if display_submitted %}
   display-submitted="true"
  {% endif %}>
```
In Polymer element definition, add a property:
```
  displaySubmitted: Boolean,
```
In DOM template, use Polymer's `dom-if` binding:
```
    <template is="dom-if" if="{{ displaySubmitted }}">
        <footer>
            <content select="data-author-picture"></content>
            <div [[ authorAttributes ]]>
                Submitted by <content select="data-author-name"></content> on <content select="data-date"></content>
                [[ metadata ]]
            </div>
        </footer>
    </template>
```

## Simplified Variables
Drupal Twig templates has a lot of obscure and cumbersome variables such as `attributes`, `title_prefix`.

In Polymer base theme we combine and simplify those variables into simple ones for your use in your Polymer element.

However, this could also mean less ability for customization.

To access more raw variables in the original Twig template (which are often big HTML blocs), override the respective Twig template in your sub-theme.

## Creating a sub-theme
 - TODO
