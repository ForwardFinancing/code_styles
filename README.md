# code_styles


## Purpose

* This is a listing of our company code styles for languages and/or frameworks.
* We use this to facilitate automated checking of our code styles.


## Rational

### Why have code style rules:
* Writing code that is easier to understand makes it:
  1. easier to find and correct bugs
  2. easier to bring team members up to speed
  3. easier to extend features
  4. easier to review the code


## Updates

### How to make a change to a rule:
  1. open a PR with the updated rule
  2. post PR for code review to get input from the whole team
  3. all engineers should approve/disapprove or actively abstain
  4. a rule change can be merged after 2/3 of those voting approve of it


## Use

### How it is used in current repositories:
* Code Ship runs the tests and Code Climate runs linting
* It is recommended you use the [code climate chrome extension](https://chrome.google.com/webstore/detail/code-climate/phgahogocbnfilkegjdpohgkkjgahjgk?hl=en)
* When a PR is opened against master or develop branches:
  1. tests run in code ship based on the project settings for that repo
  2. code linting is run on code climate
  3. a summary of both those checks will be present near the merge button when viewing the PR
* Both checks should pass before posting the PR for review
* Unless you are looking for help with the issues identified by the checks

## Specifics by Language

### Check out each language doc
* [ruby](https://github.com/ForwardFinancing/code_styles/blob/master/RUBY.md)
* [scss](https://github.com/ForwardFinancing/code_styles/blob/master/SCSS.md)
* [javascript](https://github.com/ForwardFinancing/code_styles/blob/master/JAVASCRIPT.md)
* TODO: add documents for elixir
