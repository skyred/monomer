
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

## (Dev) Comment block

Sample:

```
<!--
/**
 * @file
 * Component for node
 *
 * Properties:
 * - wrapperClass: [String]
 * - headingAttributes: [String]
 * - url: [String]
 * - metadata: [String]
 * - showTitle: [Boolean]
 * - created: [String]
 *
 * DOM children:
 * - <data-label>: heading.
 * - <data-author-picture>
 * - <data-author-name>
 * - <data-date>
 * - <data-main-content>
 */
-->
```

## Polymer Template helper


## (Dev) Conventions

- HTML blocs are passed in via LightDOM. (use <content> to form Composed DOM).
- Structured data (array / object / simple string such as url) are passed in via properties.

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