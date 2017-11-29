```
```
# About us:
  * Forward Financing is a Boston-based fintech company with one main objective — a laser-like focus on helping and empowering our small business clients
  * checkout out out tech blog [here](http://tech.forwardfinancing.com/)


```
```

# About the code_styles Repo:

## Purpose:

* This is a listing of our company code styles for languages and/or frameworks.
* We use this to facilitate automated checking of our code styles.


## Rational:

### Why have code style rules:
* Writing code that is easier to understand makes it:
  1. easier to find and correct bugs
  2. easier to bring team members up to speed
  3. easier to extend features
  4. easier to review the code


## Updates:

### How to make a change to a rule:
  1. open a PR with the updated rule
  2. post PR for code review to get input from the whole team
  3. all engineers should approve/disapprove or actively abstain
  4. a rule change can be merged after 2/3 of those voting approve of it


## Use:

### How it is used in repositories:
* Code Ship runs the tests and Code Climate runs linting
* It is recommended you use the [code climate chrome extension](https://chrome.google.com/webstore/detail/code-climate/phgahogocbnfilkegjdpohgkkjgahjgk?hl=en)
* When a PR is opened against master or develop branches:
  1. tests run in code ship based on the project settings for that repo
  2. code linting is run on code climate
  3. a summary of both those checks will be present near the merge button when viewing the PR
* Both checks should pass before posting the PR for review
* Unless you are looking for help with the issues identified by the checks

## Specifics by Language:

### Check out each language doc
* [ruby](https://github.com/ForwardFinancing/code_styles/blob/master/RUBY.md)
* [scss](https://github.com/ForwardFinancing/code_styles/blob/master/SCSS.md)
* [javascript](https://github.com/ForwardFinancing/code_styles/blob/master/JAVASCRIPT.md)
* [elixir](https://github.com/ForwardFinancing/code_styles/blob/master/ELIXIR.md)


```
```
MIT License

Copyright (c) 2017

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
