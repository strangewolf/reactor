
# Reactor (Coming Soon)

## Features

- Four different layout based on Auth-type (Admin, Client, Customer and Guest).
- Fully **React** + **Redux Saga** based repo.
- [Material design](https://material-ui.com/) and [Ant Design](http://ant.design/).

## Project Architecture

```
- assets
  - fonts
  - images
- common (page router and page menus)
  - AdminDashboardRouter
  - adminSubMenu
  - ClientDashboardRouter
  - clientSubMenu
  - CustomerDashboardRouter
  - customerSubMenu
- components
- layouts
  - AdminDashboard
  - ClientDashboard
  - CustomerDashboard
  - LandingPage
- models
- routes
  - Admin
  - Client
  - Customer
  - Landing
  - Dashboard
  - Analytics
  - Workspace
  - Result
    - Success
    - Failed
  - Exception
    - 403
    - 404
    - 500
  - User
    - Login
    - Register
- services
  - api
  - error
  - user
- utils
  - Authorized
  - GuestRoute
  - FeatureRoute
  - Request
  - Utils
```

## Usage

# First Install Yarn

```bash
$ git clone *this repo path*
$ cd billeasy_react
$ yarn
$ yarn start         # visit http://localhost:8000
```

##eslint-setup

- Before start development please do install `Eslint`, no one like dirty codes.

# Step 1

`yarn add --save-dev eslint eslint-config-airbnb eslint-plugin-import eslint-plugin-react eslint-plugin-jsx-a11y babel-eslint`

- (Backup your eslintrc file in case you want to examine it.)

# Step 2

`eslint --init`
- 1. Select 'Use a popular style guide'
- 2. Select Airbnb
- 3. Select your options, pick JSON type (.eslintrc is the old filename based on my - research, but it's the same thing)
- 4. Allow it to update newer versions and/or install packages if it asks

# Step 3

- Restart your editors

# Step 4

Paste this into your `.eslintrc.json` :
and remove my comments which will cause the JSON to blow up.
(PS: writing rules for ESlint)

```
{
  "parser": "babel-eslint",
  "extends": "airbnb",
  "plugins": ["compat"],
  "env": {
    "browser": true,
    "node": true,
    "es6": true,
    "mocha": true,
    "jest": true,
    "jasmine": true
  },
  "rules": {
    "generator-star-spacing": [0],
    "consistent-return": [0],
    "react/forbid-prop-types": [0],
    "react/jsx-filename-extension": [1, { "extensions": [".js"] }],
    "global-require": [1],
    "import/prefer-default-export": [0],
    "react/jsx-no-bind": [0],
    "react/prop-types": [0],
    "react/prefer-stateless-function": [0],
    "react/jsx-wrap-multilines": ["error", {
      "declaration": "parens-new-line",
      "assignment": "parens-new-line",
      "return": "parens-new-line",
      "arrow": "parens-new-line",
      "condition": "parens-new-line",
      "logical": "parens-new-line",
      "prop": "ignore"
    }],
    "no-else-return": [0],
    "no-restricted-syntax": [0],
    "import/no-extraneous-dependencies": [0],
    "no-use-before-define": [0],
    "jsx-a11y/no-static-element-interactions": [0],
    "jsx-a11y/no-noninteractive-element-interactions": [0],
    "jsx-a11y/click-events-have-key-events": [0],
    "jsx-a11y/anchor-is-valid": [0],
    "no-nested-ternary": [0],
    "arrow-body-style": [0],
    "import/extensions": [0],
    "no-bitwise": [0],
    "no-cond-assign": [0],
    "import/no-unresolved": [0],
    "comma-dangle": ["error", {
      "arrays": "always-multiline",
      "objects": "always-multiline",
      "imports": "always-multiline",
      "exports": "always-multiline",
      "functions": "ignore"
    }],
    "object-curly-newline": [0],
    "function-paren-newline": [0],
    "no-restricted-globals": [0],
    "require-yield": [1],
    "compat/compat": "error"
  },
  "parserOptions": {
    "ecmaFeatures": {
      "experimentalObjectRestSpread": true
    }
  },
  "settings": {
    "polyfills": ["fetch", "promises"]
  }
}
```

# Step 5

- `yarn add eslint-plugin-compat --save-dev`
- restart server `yarn start`
- restart your editor too

## Extra

- Remove `transform-decorators-legacy` from `.webpackrc.js` to solve this issue ```Module build failed: TypeError: Property right of AssignmentExpression expected node to be of a type ["Expression"] but instead got null at Array.map``` if you get from latest babel update.
