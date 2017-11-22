# SCSS Linter Rules

###### Below is a list of rules we use for our `scss-lint`.
###### this is adapted from SCSS-Lint documentation [here](https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md)

* [BangFormat](#bangformat)
* [BorderZero](#borderzero)
* [ColorKeyword](#colorkeyword)
* [ColorVariable](#colorvariable)
* [Comment](#comment)
* [DebugStatement](#debugstatement)
* [DeclarationOrder](#declarationorder)
* [DuplicateProperty](#duplicateproperty)
* [ElsePlacement](#elseplacement)
* [EmptyLineBetweenBlocks](#emptylinebetweenblocks)
* [EmptyRule](#emptyrule)
* [FinalNewline](#finalnewline)
* [HexLength](#hexlength)
* [HexNotation](#hexnotation)
* [HexValidation](#hexvalidation)
* [IdSelector](#idselector)
* [ImportantRule](#importantrule)
* [ImportPath](#importpath)
* [Indentation](#indentation)
* [LeadingZero](#leadingzero)
* [MergeableSelector](#mergeableselector)
* [NameFormat](#nameformat)
* [NestingDepth](#nestingdepth)
* [PlaceholderInExtend](#placeholderinextend)
* [PropertySortOrder](#propertysortorder)
* [PropertySpelling](#propertyspelling)
* [PropertyUnits](#propertyunits)
* [PseudoElement](#pseudoelement)
* [QualifyingElement](#qualifyingelement)
* [SelectorDepth](#selectordepth)
* [SelectorFormat](#selectorformat)
* [Shorthand](#shorthand)
* [SingleLinePerProperty](#singlelineperproperty)
* [SingleLinePerSelector](#singlelineperselector)
* [SpaceAfterComma](#spaceaftercomma)
* [SpaceAfterComment](#spaceaftercomment)
* [SpaceAfterPropertyColon](#spaceafterpropertycolon)
* [SpaceAfterPropertyName](#spaceafterpropertyname)
* [SpaceAfterVariableColon](#spaceaftervariablecolon)
* [SpaceAfterVariableName](#spaceaftervariablename)
* [SpaceAroundOperator](#spacearoundoperator)
* [SpaceBeforeBrace](#spacebeforebrace)
* [SpaceBetweenParens](#spacebetweenparens)
* [StringQuotes](#stringquotes)
* [TrailingSemicolon](#trailingsemicolon)
* [TrailingWhitespace](#trailingwhitespace)
* [TrailingZero](#trailingzero)
* [TransitionAll](#transitionall)
* [UnnecessaryMantissa](#unnecessarymantissa)
* [UnnecessaryParentReference](#unnecessaryparentreference)
* [UrlFormat](#urlformat)
* [UrlQuotes](#urlquotes)
* [VariableForProperty](#variableforproperty)
* [VendorPrefix](#vendorprefix)
* [ZeroUnit](#zerounit)

## BangFormat

Reports when you use improper spacing around `!` (the "bang") in `!default`, `!global`, `!important`, and `!optional` flags.

You can prefer a single space or no space both before and after the `!`.

**Bad**
```scss
color: #000!important;
```

**Good**
```scss
color: #000 !important;
```

Configuration Option | Description
---------------------|---------------------------------------------------------
`space_before_bang`  | Whether a space should be present *before* the `!`, as in `color: #000 !important;` (default **true**)
`space_after_bang`   | Whether a space should be present *after* the `!`, as in `color: #000 ! important;` (default **false**)

## BorderZero

Prefer the terser `border: 0` over `border: none`, as it is usually what is intended.

You can specify preferring `border: none` over `border: 0` by setting the
`convention` option.

*WARNING*: `border: 0` and `border: none` are fundamentally different, as they
are both shorthands. The intent of this linter is to enforce consistency,
rather than define which is "better."

Configuration Option | Description
---------------------|---------------------------------------------------------
`convention`         | Whether to prefer `0` (**zero**) or `none` (**none**) (default **zero**)

## ColorKeyword

Prefer hexadecimal color codes over color keywords.

**Bad: color keyword**
```scss
color: green;
```

**Good: hexadecimal color**
```scss
color: #0f0;
```

Color keywords look like variables but are not variables. See the
[ColorVariable](#colorvariable) linter for more justification on why you should
always refer to colors via variables.

## ColorVariable

Prefer color literals (keywords or hexadecimal codes) to be used only in
variable declarations. They should be referred to via variables everywhere else.

**Bad: literal color**
```scss
p {
  color: green;
}
```

**Good: refer to color by variable name**
```scss
$body-color: #0f0;

...

p {
  color: $body-color;
}
```

Defining colors directly in properties is usually a smell. When you color your
body text in a number of places, if you ever want to change the color of the
text you'll have to update the explicitly defined color in a number of places,
and finding all those places can be difficult if you use the same color for
other elements (i.e. a simple find/replace may not always work).

A better approach is to use global variables like `$color-text-body` and refer
to this variable everywhere you want to use it. This makes it easy to update
the color, as you only need change it in one place. It is also more
intention-revealing, as seeing the name `$color-text-body` is more descriptive
than `#333` or `black`. Using color keywords can obfuscate this, as they look
like variables.

## Comment

Prefer `//` comments over `/* ... */`.

**Bad**
```scss
/* This is a comment that gets rendered */
```

**Good**
```scss
// This comment never gets rendered
```

`//` comments should be preferred as they don't get rendered in the final
generated CSS, whereas `/* ... */` comments do.

Furthermore, comments should be concise, and using `/* ... */`
encourages multi-line comments which tend to not be concise.

If you want to allow multi-line comments containing certain text, such as
copyright notices, set the `allowed` option to a regular expression. This will
allow multi-line comments that match the regular expression.

Configuration Option | Description
---------------------|---------------------------------------------------------
`allowed`            | Regular expression for matching allowed comments, such as '^[/\* ] Copyright'
`style`              | Style of comment to enforce (`silent` or `loud`) (default **silent**)

## DuplicateProperty

Reports when you define the same property twice in a single rule set.

**Bad**
```scss
h1 {
  margin: 10px;
  text-transform: uppercase;
  margin: 0; // Second declaration
}
```

Having duplicate properties is usually just an error. However, they can be used
as a technique for dealing with varying levels of browser support for CSS
properties. In the example below, some browsers might not support the `rgba`
function, so the intention is to fall back to the color `#fff`.

```scss
.box {
  background: #fff;
  background: rgba(255, 255, 255, .5);
}
```

In this situation, using duplicate properties is acceptable, but you will have
to configure DuplicateProperty with the `ignore_consecutive` option, so that it
won't consider such cases to be lint. `ignore_consecutive` can be set to `true`,
`false` (default), or a list of property names to be allowed. For example, to
ignore consecutive `background` and `transition` properties, as above, you can
configure DuplicateProperty with:

```yaml
DuplicateProperty:
  ignore_consecutive:
    - background
    - transition
```

Configuration Option | Description
---------------------|---------------------------------------------------------
`ignore_consecutive` | Whether to ignore consecutive duplicate properties (default **false**), or a whitelist.

## ElsePlacement

Place `@else` statements on the same line as the preceding curly brace.

**Bad**
```scss
@if {
  ...
}
@else {
  ...
}
```

**Good**
```scss
@if {
  ...
} @else {
  ...
}
```

This will ignore single line `@if`/`@else` blocks, so you can write:

```scss
@if { ... } @else { ... }
```

You can prefer to enforce having `@else` on its own line by setting the `style`
configuration option to `new_line`.

Configuration Option  | Description
----------------------|--------------------------------------------------------
`style`               | `same_line` or `new_line` (default `same_line`)

## EmptyLineBetweenBlocks

Separate rule, function, and mixin declarations with empty lines.

**Bad: no lines separating blocks**
```scss
p {
  margin: 0;
  em {
    ...
  }
}
a {
  ...
}
```

**Good: lines separating blocks**
```scss
p {
  margin: 0;

  em {
    ...
  }
}

a {
  ...
}
```

By default, this will ignore single line blocks, so you can write:

```scss
.icon-chevron-up    { &:before { content: "\e030"; } }
.icon-chevron-down  { &:before { content: "\e031"; } }
.icon-chevron-left  { &:before { content: "\e032"; } }
.icon-chevron-right { &:before { content: "\e033"; } }
```

Configuration Option        | Description
----------------------------|---------------------------------------------------
`ignore_single_line_blocks` | Don't enforce for single-line blocks (default **true**)

## EmptyRule

Reports when you have an empty rule set.

```scss
.cat {
}
```

## FinalNewline

Files should always have a final newline. This results in better diffs when
adding lines to the file, since SCM systems such as git won't think that you
touched the last line.

You can customize whether or not a final newline exists with the `present`
option.

Configuration Option | Description
---------------------|---------------------------------------------------------
`present`            | Whether a final newline should be present (default **true**)

## HexLength

You can specify whether you prefer shorthand or long-form hexadecimal
colors by setting the style option to `short` or `long`, respectively.

**short**
```scss
color: #f2e;
```

**long**
```scss
color: #ff22ee;
```

Configuration Option | Description
---------------------|--------------------------------------------
`style`              | Prefer `short`

## HexNotation

Checks if hexadecimal colors are written in lowercase. You can specify which
case with the `style` option.

Configuration Option | Description
---------------------|---------------------------------------------------------
`style`              | Prefer `lowercase`

## HexValidation

Ensure hexadecimal colors are valid (either three or six digits).

**Bad**
```scss
p {
  background: #ab; // Clearly a typo
}
```

**Good**
```scss
p {
  background: #abc;
}
```

## IdSelector

Avoid using ID selectors.

**Bad: highly-specific styling for a single element via ID**
```scss
#submit-button {
  ...
}
```

**Good: reusable class**
```scss
.submit-button {
  ...
}
```

While the CSS specification allows for multiple elements with the same ID to
appear in a single document, in practice this is a smell. [ID selectors should
never be used](http://screwlewse.com/2010/07/dont-use-id-selectors-in-css/) for
the purposes of styling an element, as it leads to overly specific styles that
aren't easily shared with other elements.

## ImportantRule

Avoid using `!important` in properties. It is usually indicative of a
misunderstanding of CSS
[specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
and can lead to brittle code.

*Bad*
```scss
p {
  color: #f00 !important;
}
```

*Good*
```scss
p {
  color: #f00;
}
```

## ImportPath

The basenames of `@import`ed SCSS partials should not begin with an underscore
and should include the filename extension.

**Bad**
```scss
@import "foo/_bar.scss";
@import "_bar.scss";
@import "_bar";
@import "bar.scss";
```

**Good**
```scss
@import "foo/bar.scss";
@import "bar.scss";
```

`@import` declarations that Sass compiles directly into CSS `@import` rules
will be ignored.

Configuration Option | Description
---------------------|---------------------------------------------------------
`leading_underscore` | `false`
`filename_extension` | `true`

## Indentation

Use two spaces per indentation level.

**Bad: four spaces**
```scss
p {
    color: #f00;
}
```

**Good: two spaces**
```scss
p {
  color: #f00;
}
```

For projects that follow BEM, you may prefer to allow arbitrary indentation for
rule sets that aren't nested in order to give the visual hints of hierarchy
without actually nesting selectors (which has a performance cost). For example:

```scss
.component {}
  .component__image {}
  .component__text {}
    .component-subblock {}
    .component-subblock__text {}
  .component-category {}
    .component-other {}
```
Configuration Option           | Description
-------------------------------|---------------------------------------------------------
`allow_non_nested_indentation` | Whether non-nested rule sets can be arbitrarily indented (`false`)
`character`                    | `space`
`width`                        | Number of `character`s per indentation level (`2`)

## LeadingZero

Don't write leading zeros for numeric values with a decimal point.
Note that is rule is not enabled, but we do in general prefer leading zeros

**Bad: no leading zero**
```scss
margin: .5em;
```

**Good: leading zero**
```scss
margin: 0.5em;
```

You can configure this to prefer including leading zeros.

Configuration Option | Description
---------------------|---------------------------------------------------------
`style`              | `include_zero`

## MergeableSelector

Reports when you define the same selector twice in a single sheet.

**Bad**
```scss
h1 {
  margin: 10px;
}

.baz {
  color: red;
}

// Second copy of h1 rule
h1 {
  text-transform: uppercase;
}
```

**Good**
```scss
h1 {
  margin: 10px;
  text-transform: uppercase;
}

.baz {
  color: red;
}
```

Combining duplicate selectors can result in an easier to read sheet, but
occasionally the rules may be purposely duplicated to set precedence
after a rule with the same CSS specificity. However, coding your
stylesheets in this way makes them more difficult to comprehend, and can
usually be avoided.

You can specify that rule sets which can be nested within another rule
set must be nested via the `force_nesting` option, e.g.

**Bad**
```scss
h1 {
  color: #fff;
}

h1.new {
  color: #000;
}
```

**Good**
```scss
h1 {
  color: #fff;

  &.new {
    color: #000;
  }
}
```

Configuration Option | Description
---------------------|------------------------------------------------------------------
`force_nesting`      | Ensure rule sets which can be nested are nested (default **true**)
`whitelist`          | A list of selectors that can MergeableSelector, list those used in [CSS Shims][]

[CSS Shims]: https://github.com/angular/angular.dart/wiki/CSS-Shim

## NameFormat

Functions, mixins, variables, and placeholders should be declared with all
lowercase letters and hyphens instead of underscores.

**Bad: uppercase characters**
```scss
$myVar: 10px;

@mixin myMixin() {
  ...
}
```

**Good: all lowercase with hyphens**
```scss
$my-var: 10px;

@mixin my-mixin() {
  ...
}
```

The Sass parser automatically treats underscores and hyphens the same, so even
if you're using a library that declares a function with an underscore, you can
refer to it using the hyphenated form instead.


Configuration Option            | Description
--------------------------------|----------------------------------------------
`allow_leading_underscore`      | Whether to allow names to start with a single underscore (`true`)
`convention`                    | Name of convention to use (`hyphenated_lowercase`)

## NestingDepth

Avoid nesting selectors too deeply.

**Bad: deeply nested**
```scss
.one {
  .two {
    .three {
      .four {
        ...
      }
    }
  }
}
```

**Good**
```scss
.three:hover {
}

.three {
  &:hover {
    ...
  }
}
```

Overly nested rules will result in over-qualified CSS that could prove hard to
maintain, output unnecessary selectors and is generally considered bad
practice.

**No error**
```scss
.one .two .three {
  ...
}
```

**Error**
```scss
.one {
  .two {
    .three {
      ...
    }
  }
}
```

Configuration Option        | Description
----------------------------|---------------------------------------------------------
`max_depth`                 | Maximum depth before reporting errors (`3`)
`ignore_parent_selectors`   | Whether to report errors for parent selectors (`false`)

## PlaceholderInExtend

Always use placeholder selectors in `@extend`.

**Bad: extending a class**
```scss
.fatal {
  @extend .error;
}
```

**Good: extending a placeholder**
```scss
.fatal {
  @extend %error;
}
```

Using a class selector with the `@extend` directive usually results in more
generated CSS than when using a placeholder selector. Furthermore, Sass
specifically introduced placeholder selectors in order to be used with
`@extend`.

## PropertySortOrder

Sort properties in a strict order. By default, will require properties be
sorted in alphabetical order, as it's brain dead simple (highlight lines and
execute `:sort` in `vim` or `f5` in `atom`).

Configuration Option | Description
---------------------|---------------------------------------------------------
`ignore_unspecified` | Whether to ignore properties that are not explicitly specified in `order` (`false`)
`min_properties`     | Minimum number of sortable properties (`5`)
`separate_groups`    | Whether gaps between groups of properties should be enforced. (`false`)

## PropertySpelling

Reports when you use an unknown or disabled CSS property (ignoring vendor-prefixed
properties).

```scss
diplay: none; // "display" is spelled incorrectly
```

------------------------|---------------------------------------------------------
`extra_properties`      | List of extra properties to allow (`[]`)
`disabled_properties`   | List of existing properties to deny (`[]`)

## PropertyUnits

Configure which units are allowed for property values.

Configuration Option | Description
---------------------|---------------------------------------------------------
`global`             | List of allowed units (by default any unit is allowed)
`properties`         | Hash of property names and their list of allowed units. (empty by default)

## PseudoElement

Pseudo-elements, like `::before`, and `::first-letter`, should be declared with
two colons. Pseudo-classes, like `:hover` and `:first-child`, should be
declared with one colon.

**Bad: wrong colons**
```scss
p:before {
  content: '>'
}

p::hover {
  color: red;
}
```

**Good: correct colons**
```scss
p::before {
  content: '>'
}

p:hover {
  color: red;
}
```

## QualifyingElement

Avoid qualifying elements in selectors (also known as "tag-qualifying").

**Bad: qualifying elements**
```scss
div#thing {
  ...
}

ul.list {
  ...
}

ul li.item {
  ...
}

a[href="place"] {
  ...
}
```

**Good**
```scss
#thing {
  ...
}

.list {
  ...
}

ul .item {
  ...
}

[href="place"] {
  ...
}
```

Since IDs are unique, they will not apply to multiple elements, so there is no
good reason to qualify an ID selector with an element.

In most cases, qualifying a class or attribute selector with an element adds
unnecessary or undesirable specificity. Often the element qualifier is
already superfluous; and if it is not, you will probably be better off
refactoring so that it *can* be removed.

Use the options to allow certain qualifying elements.

Configuration Option           | Description
-------------------------------|-------------------------------------------------------
`allow_element_with_attribute` | Allow elements to qualify attributes (`false`)
`allow_element_with_class`     | Allow elements to qualify classes (`false`)
`allow_element_with_id`        | Allow elements to qualify ids (`false`)

## SelectorDepth

Don't write selectors with a depth of applicability greater than 3.

**Bad: selectors with depths of 4**
```scss
.one .two .three > .four {
  ...
}

.one .two {
  .three > .four {
    ...
  }
}
```

**Good**
```scss
.one .two .three {
  ...
}

.one .two {
  .three {
    ...
  }
}
```

Selectors with a large depth of applicability lead to CSS tightly-coupled to your
HTML structure, making it brittle to change.

Deep selectors also come with a performance penalty, which can affect rendering
times, especially on mobile devices. While the default limit is 3, ideally it
is better to use less than 3 whenever possible.

Configuration Option | Description
---------------------|---------------------------------------------------------
`max_depth`          | Maximum depth before reporting errors (`3`)

## SelectorFormat

It is good practice to choose a convention for naming selectors.

[`hyphenated_BEM`](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/).

**Good**
```scss
  // convention: 'hyphenated_BEM'
  .site-search {} /* Block */
  .site-search__field {} /* Element */
  .site-search--full {} /* Modifier */
```

Configuration Option     | Description
-------------------------|-----------------------------------------------------
`convention`             | Name of convention to use (`hyphenated_BEM`)

### Limitations

`SelectorFormat` will not resolve the parent selector reference (`&`),
and will ignore selectors containing any parent references.
This is because these references cannot be resolved without compiling
the Sass into actual CSS. If you would like to see such functionality,
we'd love to merge a pull request!

## Shorthand

Prefer the shortest shorthand form possible for properties that support it.

**Bad: all 4 sides specified with same value**
```scss
margin: 1px 1px 1px 1px;
```

**Good: equivalent to specifying 1px for all sides**
```scss
margin: 1px;
```

Configuration Option | Description
---------------------|---------------------------------------------------------
`allowed_shorthands` | Array of allowed shorthand lengths (`[1, 2, 3, 4]`)

## SingleLinePerProperty

Properties within rule sets should each reside on their own line.

**Bad**
```scss
p {
  margin: 0; padding: 0;
}
```

**Good**
```scss
p {
  margin: 0;
  padding: 0;
}
```

A special exception is made for single line rule sets. For example the
following is acceptable:

```scss
p { margin: 0; padding: 0; }
```

Configuration Option          | Description
------------------------------|----------------------------------------------
`allow_single_line_rule_sets` | `true`

## SingleLinePerSelector

Split selectors onto separate lines after each comma, and have each individual
selector occupy a single line.

**Bad: comma-separated selectors not on their own lines**
```scss
.error p, p.explanation {
  ...
}
```

**Bad: descendent selector spread over multiple lines**
```scss
.error
  p,
  p.explanation {
  ...
}
```

**Good: each selector sequence is on its own individual line**
```scss
.error p,
p.explanation {
  ...
}
```

## SpaceAfterComma

Commas in lists should be followed by a space.

**Bad: no space after commas**
```scss
@include box-shadow(0 2px 2px rgba(0,0,0,.2));
color: rgba(0,0,0,.1);
```

**Good: commas followed by a space**
```scss
@include box-shadow(0 2px 2px rgba(0, 0, 0, .2));
color: rgba(0, 0, 0, .1);
```

Configuration Option | Description
---------------------|---------------------------------------------------------
`style`              | `one_space`

## SpaceAfterComment

Comment literals should be followed by a space.

**Bad: no space after comment literal**
```scss
//no space
/*no space*/
/*!no space for loud comment*/
```

**Good: comment literals followed by a space**
```scss
// one space
/* one space*/
/*! one space for loud comment*/
```

The `style` option allows you to specify a different preferred style.

Configuration Option   | Description
-----------------------|---------------------------------------------------------
`style`                | `one_space`

## SpaceAfterPropertyColon

Properties should be formatted with a single space separating the colon from
the property's value.

**Bad: no space after colon**
```scss
margin:0;
```

**Bad: more than one space after colon**
```scss
margin:  0;
```

**Good**
```scss
margin: 0;
```

Configuration Option | Description
---------------------|---------------------------------------------------------
`style`              | `one_space`

## SpaceAfterPropertyName

Properties should be formatted with no space between the name and the colon.

**Bad: space before colon**
```scss
margin : 0;
```

**Good**
```scss
margin: 0;
```

## SpaceAfterVariableName

Variables should be formatted with no space between the name and the colon.

**Bad: space before colon**
```scss
$my-var : 0;
```

**Good**
```scss
$my-var: 0;
```

## SpaceAroundOperator

Operators should be formatted with a single space on both sides of an infix
operator. These include `+`, `-`, `*`, `/`, `%`, `==`, `!=`, `>`, `>=`, `<`,
and `<=`.

**Bad: no space around operator**
```scss
margin: 5px+5px;
```

**Bad: more than one space around operator**
```scss
margin: 5px   +   5px;
```

**Good**
```scss
margin: 5px + 5px;
```

Note that this linter only applies to actual, evaluated operators. So values
like `nth-child(2n+1)`, `10px/12px`, and `my-font` will not be linted, as they
are valid CSS.

The `style` option allows you to specify a different preferred style.

Configuration Option | Description
---------------------|---------------------------------------------------------
`style`              | `one_space`

## SpaceBeforeBrace

Opening braces should be preceded by a single space.

**Bad: no space before brace**
```scss
p{
  ...
}
```

**Bad: more than one space before brace**
```scss
p  {
  ...
}
```

**Good**
```scss
p {
  ...
}
```

Configuration Option        | Description
----------------------------|---------------------------------------------------
`allow_single_line_padding` | Allow single line blocks to have extra spaces for nicer formatting (`false`)
`style`                     | `space`

## SpaceBetweenParens

Parentheses should not be padded with spaces.

**Bad**
```scss
@include box-shadow( 0 2px 2px rgba( 0, 0, 0, .2 ) );
color: rgba( 0, 0, 0, .1 );
```

**Good**
```scss
@include box-shadow(0 2px 2px rgba(0, 0, 0, .2));
color: rgba(0, 0, 0, .1);
```

Configuration Option | Description
---------------------|---------------------------------------------------------
`spaces`             | 0

## StringQuotes

String literals should be written with single quotes unless using double quotes
would save on escape characters.

**Bad: double quotes**
```scss
content: 'hello';
```

**Good:**
```scss
content: "hello";
```

Single quotes are easier to type by virtue of not requiring the `Shift` key on
most popular keyboard layouts.

Configuration Option | Description
---------------------|---------------------------------------------------------
`style`              | `double_quotes`

## TrailingSemicolon

Property values; `@extend`, `@include`, and `@import` directives; and variable
declarations should always end with a semicolon.

**Bad: no semicolon**
```scss
p {
  color: #fff
}
```

**Bad: space between value and semicolon**
```scss
p {
  color: #fff ;
}
```

**Good**
```scss
p {
  color: #fff;
}
```

CSS allows you to omit the semicolon if the statement is the last statement in
the rule set. However, this introduces inconsistency and requires anyone adding
a property after that property to remember to append a semicolon.

## TrailingWhitespace

Reports lines containing trailing whitespace.

## UnnecessaryMantissa

Numeric values should not contain unnecessary fractional portions.

**Bad**

```scss
margin: 1.0em;
```

**Good**

```scss
margin: 1em;
```

Sass will automatically convert integers to floats when necessary, making the
use of a fractional component in a value to "force" it to be a floating point
number unnecessary. For example, the following code:

```scss
$margin: 1;
p { margin: $margin / 2; }
```

...will compile to:

```css
p { margin: 0.5; }
```

## UnnecessaryParentReference

Do not use parent selector references (`&`) when they would otherwise be
unnecessary.

**Bad**

```scss
.foo {
  & > .bar {
    ...
  }
}
```

**Good**

```scss
.foo {
  > .bar {
  }
}
```

## UrlFormat

URLs should be valid and not contain protocols or domain names.

Including protocols or domains in URLs makes them brittle to change, and also
unnecessarily increases the size of your CSS documents, reducing performance.

**Bad: protocol and domain present**

```scss
background: url('https://example.com/assets/image.png');
```

**Good**

```scss
background: url('assets/image.png');
```

## UrlQuotes

URLs should always be enclosed within quotes.

**Bad: no enclosing quotes**
```scss
background: url(example.png);
```

**Good**
```scss
background: url('example.png');
```

Using quoted URLs is consistent with using other Sass asset helpers, which also
expect quoted strings. It also works better with most syntax highlighters, and
makes it easier to escape characters, as the escape rules for strings apply,
rather than the different set of rules for literal URLs.

See the [URL type](http://dev.w3.org/csswg/css-values/#url-value) documentation
for more information.

## VendorPrefix

Avoid vendor prefixes. That is, don't write them yourself.

Instead, you can use Autoprefixer or mixins

At-rules, selectors, properties, and values are all checked. (See the examples below.)

The default `identifier_list`, `base`, should include everything that Autoprefixer addresses.

**Bad: vendor prefixes**
```scss
@-webkit-keyframes anim {
  0% { opacity: 0; }
}

::-moz-placeholder {
  color: red;
}

.foo {
  -webkit-transition: none;
}

.bar {
  position: -moz-sticky;
}
```

**Good**
```scss
// With Autoprefixer ...
@keyframes anim {
  0% { opacity: 0; }
}

::placeholder {
  color: red;
}

.foo {
  transition: none;
}

.bar {
  position: sticky;
}

// With Bourbon mixin
@include placeholder {
  color: red;
}
```

Configuration Option     | Description
-------------------------|---------------------------------------------------------
`identifier_list`        | `base`

## ZeroUnit

Omit length units on zero values.

**Bad: unnecessary units**
```scss
margin: 0px;
```

**Good**
```scss
margin: 0;
```

Zero is zero regardless of the units of length.

Note that this only applies to
[lengths](https://developer.mozilla.org/en-US/docs/Web/CSS/length),
since it is invalid to omit units for other types such as
[angles](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) or
[times](https://developer.mozilla.org/en-US/docs/Web/CSS/time).
