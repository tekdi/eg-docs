---
sidebar_position: 2
tags: [css, styleguide]
---

# Stylelint

## About
- Stylelint is a powerful tool for linting CSS and other stylesheet languages. It helps maintain consistent styles and catch potential errors in your CSS code.
- Stylelint analyzes your CSS code without actually running it. It checks for errors, enforces a coding standard, looks for code smells.

### Links
- [Stylelint Homepage](https://stylelint.io/)

### Stylelint Plugins
Along with stylelint, we recommend to use following plugins:
- [stylelint-config-standard](https://www.npmjs.com/package/stylelint-config-standard): is a widely-used configuration for Stylelint, providing a set of standard rules and best practices for CSS and SCSS code quality, ensuring consistency and reducing potential errors
- [stylelint-config-rational-order](https://www.npmjs.com/package/stylelint-config-rational-order): plugin organizes CSS properties in a specific, rational order, improving readability and maintainability by enforcing a logical sequence for property declarations.

:::info
The stylelint-config-rational-order plugin's rational order is based on grouping CSS properties by their functions and logical significance. This typically involves organizing properties into categories like:
- Positioning (e.g., position, top, right, bottom, left, z-index)
- Box Model (e.g., display, width, height, margin, padding, border)
- Typography (e.g., font-family, font-size, font-weight, line-height, color)
- Visual (e.g., background, box-shadow, opacity)
- Miscellaneous (e.g., transition, transform, animation)
:::

This structured approach improves the readability and maintainability of CSS code by grouping related properties together.

## Installation
- First, navigate to your project directory and install Stylelint along with some essential plugins and configurations. 
-  If using npm
```
npm install stylelint stylelint-config-standard stylelint-config-rational-order --save-dev
```
-  Or if using yarn
```
yarn add stylelint stylelint-config-standard stylelint-config-rational-order --dev
```

:::warning
Remember to save these as `devDependencies` in your project.
:::

## Config file for .stylelintrc
- Create and use a file named `.stylelintrc.json` in your python project root folder
- You can use the `.stylelintrc.json` file contents given below

```JSON
{
  "extends": [
    "stylelint-config-standard",
    "stylelint-config-rational-order",
  ],
  "ignoreFiles": [
    "**/*.min.css",
    "**/*.min.js"
  ]
}
```

### package.json commands for Stylelint
To easily run Stylelint, add the following scripts to your package.json file:

```JSON
"scripts": {
    "lint:css": "stylelint '**/*.{css,scss}'",
    "lint:css:fix": "stylelint '**/*.{css,scss}' --fix"
}
```

## How to use Stylelint?
### A) Using stylelint outside the editor, via terminal
- Goto your project repo `cd my-web-project`
- Run stylelint as 
```
npm run lint:css
or 
yarn lint:css
```
- To automatically fix linting errors, run:
```
npm run lint:css:fix
OR
yarn lint:css:fix
```

### B) Using stylelint inside VSCode editor
#### 1) Install this VSCode extension for Stylelint
- [Stylelint VSCode Extension](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)

#### 2) VSCode Settings for stylelint
You can edit `settings.json` of VSCode as below
- To disable the built-in CSS, Less, and SCSS linters:

```json
{
  "css.validate": false,
  "less.validate": false,
  "scss.validate": false
}
``` 

#### 3) Open any python file in editor
- Open `Problems` tab in console, to see  linting errors if any