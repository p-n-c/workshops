# Workshops

A series of web development workshops created by [People and Code](https://people-and-code.com/).
The [workshop home](https://workshops.people-and-code.com/).

## Workshop One

An introduction to HTML and CSS fundamentals.

## Workshop Two

An introduction to HTTP messages, SOP and CORS.

## Workshop Three

Website testing with Cypress.

## How to deploy

There is one trunk, and one permanent branch:

### main

`main`, the trunk, is the definitive, production ready version of the site.

### netlify-deploy

The `netlify-deploy` branch is the current deployed version of the site.

- Update `netlify-deploy` to the version you want to deploy in production, typically by merging from `main`.
- Push your changes
- **netlify** is configured to listen to changes to `netlify-deploy` in GitHub.
- When **netlify** detects changes, it will run the build script from package.json, `build`, and, if successful deploy to the [production site](https://people-and-code.com/).
