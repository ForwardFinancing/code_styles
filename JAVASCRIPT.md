# Javascript Linter Rules

###### Below is a list of rules we use for our `eslint`.
###### this is adapted from documentation [here](https://eslint.org/docs/rules/)
###### note: we use `"extends": "eslint:recommended"` property in our configuration file ([read more](https://eslint.org/docs/user-guide/configuring#extending-configuration-files))

* [constructor-super](#constructor-super)
* [jsx-quotes](#jsx-quotes)
* [jsx-one-expression-per-line](#jsx-one-expression-per-line)
* [max-len](#max-len)
* [max-statements](#max-statements)
* [no-case-declarations](#no-case-declarations)
* [no-class-assign](#no-class-assign)
* [no-compare-neg-zero](#no-compare-neg-zero)
* [no-cond-assign](#no-cond-assign)
* [no-console](#no-console)
* [no-const-assign](#no-const-assign)
* [no-constant-condition](#no-constant-condition)
* [no-control-regex](#no-control-regex)
* [no-debugger](#no-debugger)
* [no-delete-var](#no-delete-var)
* [no-dupe-args](#no-dupe-args)
* [no-dupe-class-members](#no-dupe-class-members)
* [no-dupe-keys](#no-dupe-args)
* [no-duplicate-case](#no-duplicate-case)
* [no-empty-character-class](#no-empty-character-class)
* [no-empty-pattern](#no-empty-pattern)
* [no-empty](#no-empty)
* [no-ex-assign](#no-ex-assign)
* [no-extra-boolean-cast](#no-extra-boolean-cast)
* [no-extra-semi](#no-extra-semi)
* [no-fallthrough](#no-fallthrough)
* [no-func-assign](#no-func-assign)
* [no-global-assign](#no-global-assign)
* [no-inner-declarations](#no-inner-declarations)
* [no-invalid-regexp](#no-invalid-regexp)
* [no-irregular-whitespace](#no-irregular-whitespace)
* [no-mixed-spaces-and-tabs](#no-mixed-spaces-and-tabs)
* [no-new-symbol](#no-new-symbol)
* [no-obj-calls](#no-obj-calls)
* [no-octal](#no-octal)
* [no-redeclare](#no-redeclare)
* [no-regex-spaces](#no-regex-spaces)
* [no-self-assign](#no-self-assign)
* [no-sparse-arrays](#no-sparse-arrays)
* [no-this-before-super](#no-this-before-super)
* [no-undef](#no-undef)
* [no-unexpected-multiline](#no-unexpected-multiline)
* [no-unreachable](#no-unreachable)
* [no-unsafe-finally](#no-unsafe-finally)
* [no-unsafe-negation](#no-unsafe-negation)
* [no-unused-labels](#no-unused-labels)
* [no-unused-vars](#no-unused-vars)
* [no-useless-escape](#no-useless-escape)
* [no-var](#no-var)
* [react/display-name](#react/display-name)
* [react/forbid-prop-types](#react/forbid-prop-types)
* [react/jsx-curly-spacing](#react/jsx-curly-spacing)
* [react/jsx-key](#react/jsx-key)
* [react/jsx-no-duplicate-props](#react/jsx-no-duplicate-props)
* [react/jsx-no-undef](#react/jsx-no-undef)
* [react/jsx-pascal-case](#react/jsx-pascal-case)
* [react/jsx-uses-react](#react/jsx-uses-react)
* [react/jsx-uses-vars](#react/jsx-uses-vars)
* [react/no-danger](#react/no-danger)
* [react/no-did-mount-set-state](#react/no-did-mount-set-state)
* [react/no-did-update-set-state](#react/no-did-update-set-state)
* [react/no-direct-mutation-state](#react/no-direct-mutation-state)
* [react/no-multi-comp](#react/no-multi-comp)
* [react/no-unknown-property](#react/no-unknown-property)
* [react/prefer-es6-class](#react/prefer-es6-class])
* [react/prop-types](#react/prop-type)
* [react/react-in-jsx-scope](#react/react-in-jsx-scope)
* [react/self-closing-comp](#react/self-closing-comp)
* [react/sort-comp](#react/sort-comp)
* [require-yield](#require-yield)
* [semi](#semi)
* [use-isnan](#use-isnan)
* [valid-typeof](#valid-typeof)

## no-compare-neg-zero
  * disallow comparing against -0
  [read more](https://eslint.org/docs/rules/no-compare-neg-zero)

## no-cond-assign
  * disallow assignment operators in conditional expressions
  [read more](https://eslint.org/docs/rules/no-cond-assign)

## no-console
  * disallow the use of `console`
  [read more](https://eslint.org/docs/rules/no-console)

## no-constant-condition
  * disallow constant expressions in conditions
  [read more](https://eslint.org/docs/rules/no-constant-condition)

## no-control-regex
  * disallow control characters in regular expressions
  [read more](https://eslint.org/docs/rules/no-control-regex)

## no-debugger
  * disallow the use of `debugger`
  [read more](https://eslint.org/docs/rules/no-debugger)

## no-dupe-args
  * disallow duplicate arguments in `function` definitions
  [read more](https://eslint.org/docs/rules/no-dupe-args)

## no-dupe-keys
  * disallow duplicate keys in object literals
  [read more](https://eslint.org/docs/rules/no-dupe-keys)

## no-duplicate-case
  * disallow duplicate case labels
  [read more](https://eslint.org/docs/rules/no-duplicate-case)

## no-empty
  * disallow empty block statements
  [read more](https://eslint.org/docs/rules/no-empty)

## no-empty-character-class
  * disallow empty character classes in regular expressions
  [read more](https://eslint.org/docs/rules/no-empty-character-class)

## no-ex-assign
  * disallow reassigning exceptions in `catch` clauses
  [read more](https://eslint.org/docs/rules/no-ex-assign)

## no-extra-boolean-cast
  * disallow unnecessary boolean casts
  [read more](https://eslint.org/docs/rules/no-extra-boolean-cast)

## no-extra-semi
  * disallow unnecessary semicolons
  [read more](https://eslint.org/docs/rules/no-extra-semi)

## no-func-assign
  * disallow reassigning `function` declarations
  [read more](https://eslint.org/docs/rules/no-func-assign)

## no-inner-declarations
  * disallow variable or `function` declarations in nested blocks
  [read more](https://eslint.org/docs/rules/no-inner-declarations)

## no-invalid-regexp
  * disallow invalid regular expression strings in `RegExp` constructors
  [read more](https://eslint.org/docs/rules/no-invalid-regexp)

## no-irregular-whitespace
  * disallow irregular whitespace outside of strings and comments
  [read more](https://eslint.org/docs/rules/no-irregular-whitespace)

## no-obj-calls
  * disallow calling global object properties as functions
  [read more](https://eslint.org/docs/rules/no-obj-calls)

## no-regex-spaces
  * disallow multiple spaces in regular expressions
  [read more](https://eslint.org/docs/rules/no-regex-spaces)

## no-sparse-arrays
  * disallow sparse arrays
  [read more](https://eslint.org/docs/rules/no-sparse-arrays)

## no-unexpected-multiline
  * disallow confusing multiline expressions
  [read more](https://eslint.org/docs/rules/no-unexpected-multiline)

## no-unreachable
  * disallow unreachable code after `return`, `throw`, `continue`, and `break` statements
  [read more](https://eslint.org/docs/rules/no-unreachable)

## no-unsafe-finally
  * disallow control flow statements in`finally`blocks
  [read more](https://eslint.org/docs/rules/no-unsafe-finally)

## no-unsafe-negation
  * disallow negating the left operand of relational operators
  [read more](https://eslint.org/docs/rules/no-unsafe-negation)

## use-isnan
  * require calls to`isNaN()` when checking for `NaN`
  [read more](https://eslint.org/docs/rules/use-isnan)

## valid-typeof
  * enforce comparing `typeof` expressions against valid strings
  [read more](https://eslint.org/docs/rules/valid-typeof)

## no-case-declarations
  * disallow lexical declarations in case clauses
  [read more](https://eslint.org/docs/rules/no-case-declarations)

## no-empty-pattern
  * disallow empty destructuring patterns
  [read more](https://eslint.org/docs/rules/no-empty-pattern)

## no-fallthrough
  * disallow fallthrough of `case` statements
  [read more](https://eslint.org/docs/rules/no-fallthrough)

## no-global-assign
  * disallow assignments to native objects or read-only global variables
  [read more](https://eslint.org/docs/rules/no-global-assign)

## no-octal
  * disallow octal literals
  [read more](https://eslint.org/docs/rules/no-octal)

## no-redeclare
  * disallow variable redeclaration
  [read more](https://eslint.org/docs/rules/no-redeclare)

## no-self-assign
  * disallow assignments where both sides are exactly the same
  [read more](https://eslint.org/docs/rules/no-self-assign)

## no-unused-labels
  * disallow unused labels
  [read more](https://eslint.org/docs/rules/no-unused-labels)

## no-useless-escape
  * disallow unnecessary escape characters
  [read more](https://eslint.org/docs/rules/no-useless-escape)

## no-delete-var
  * disallow deleting variables
  [read more](https://eslint.org/docs/rules/no-delete-var)

## no-undef
  * disallow the use of undeclared variables unless mentioned in `/*global*/` comments
  [read more](https://eslint.org/docs/rules/no-undef)

## no-unused-vars
  * disallow unused variables
  [read more](https://eslint.org/docs/rules/no-unused-vars)

## no-mixed-spaces-and-tabs
  * disallow mixed spaces and tabs for indentation
  [read more](https://eslint.org/docs/rules/no-mixed-spaces-and-tabs)

## constructor-super
  * require `super()` calls in constructors
  [read more](https://eslint.org/docs/rules/constructor-super)

## no-class-assign
  * disallow reassigning class members
  [read more](https://eslint.org/docs/rules/no-class-assign)

## no-const-assign
  * disallow reassigning `const` variables
  [read more](https://eslint.org/docs/rules/no-const-assign)

## no-dupe-class-members
  * disallow duplicate class members
  [read more](https://eslint.org/docs/rules/no-dupe-class-members)

## no-new-symbol
  * disallow `new` operators with the `Symbol` object
  [read more](https://eslint.org/docs/rules/no-new-symbol)

## no-this-before-super
  * disallow `this`/`super` before calling `super()` in constructors
  [read more](https://eslint.org/docs/rules/no-this-before-super)

## require-yield
  * require generator functions to contain `yield`
  [read more](https://eslint.org/docs/rules/require-yield)

## no-var
  * require let or const instead of var
  [read more](https://eslint.org/docs/rules/no-var)

## semi
  * require semicolons
  [read more](https://eslint.org/docs/rules/semi)

## jsx-quotes
  * enforce the consistent use of double quotes in JSX attributes
  [read more](https://eslint.org/docs/rules/jsx-quotes)

## max-len
  * enforce a maximum line length
  [read more](https://eslint.org/docs/rules/max-len)

## max-statements
  * enforce a maximum number of statements allowed in function blocks
  [read more](https://eslint.org/docs/rules/max-statements)

## react/display-name
  * prevent missing displayName in a React component definition
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/display-name.md)

## react/forbid-prop-types
  * checks all JSX components and verifies that no forbidden propsTypes are used.
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/forbid-prop-types.md)

## react/jsx-curly-spacing
  * aims to maintain consistency around the spacing inside of JSX attributes and expressions inside element children.
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-curly-spacing.md)

## react/jsx-key
  * warn if an element that likely requires a key prop--namely, one present in an array literal or an arrow function expression.
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-key.md)

## react/jsx-no-duplicate-props
  * prevent duplicate properties in JSX
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-no-duplicate-props.md)

## react/jsx-no-undef
  * disallows undeclared variables in JSX
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-no-undef.md)

## react/jsx-pascal-case
  * enforces coding style that user-defined JSX components are defined and referenced in PascalCase.
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-pascal-case.md)

## react/jsx-uses-react
  * prevent React being incorrectly marked as unused
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-uses-react.md)

## react/jsx-uses-vars
  * prevent variables used in JSX to be incorrectly marked as unused
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-uses-vars.md)

## react/no-danger
  * prevent usage of dangerous JSX properties
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-danger.md)

## react/no-did-mount-set-state
  * prevent usage of setState in componentDidMount
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-did-mount-set-state.md)

## react/no-did-update-set-state
  * prevent usage of setState in componentDidUpdate
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-did-update-set-state.md)

## react/no-direct-mutation-state
  * prevent direct mutation of this.state
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-direct-mutation-state.md)

## react/no-multi-comp
  * prevent multiple component definition per file
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-multi-comp.md)

## react/no-unknown-property
  * prevent usage of unknown DOM property
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/no-unknown-property.md)

## react/prefer-es6-class
  * enforce ES6 class for React Components
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prefer-es6-class.md)

## react/prop-types
  * prevent missing props validation in a React component definition
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md)

## react/react-in-jsx-scope
  * Prevent missing React when using JSX
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/react-in-jsx-scope.md)

## react/self-closing-comp
  * prevent extra closing tags for components without children
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/self-closing-comp.md)

## react/sort-comp
  * enforce component methods order
  [read more](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/sort-comp.md)
