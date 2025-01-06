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

#### Versioning

When new code is committed to `netlify-deploy` a GitHub action, Release Management, is triggered.  
This workflow contains the following steps:

- Gets the package.json version number e.g. 0.0.1 (major.minor.build)
- Increments the build portion of the version by one e.g. 0.0.1
- Updates the package.json version to the new version
- Updates the content value of the meta tag `version` in index.html to the same version
- Commits these changes to `netlify-deploy`
- Pushes these changes to `main` so that the trunk and deploy branch are in sync

To see the full yml script, go to [release_management.yml](https://github.com/p-n-c/workshops/blob/main/.github/workflows/release_management.yml)
