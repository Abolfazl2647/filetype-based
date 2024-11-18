# Proaject Folder Structure

# api

in this folder there is two other folder called `types` and `routes`

### types

we define all the types for request and response of any apis.

### routes

we define all the actual request using Axios or Ky.

# app

in this folder we put out UI components of each page. (you can name this folder view if you like)

# assets

all the assets as you know.

# components

this folder act like a shared place. any re-useable component (small components that will be used in other places) for example you may like to use a button from MUI. you should create a folder `@mui-extends/button` and place the button in sub folder named button. or you use a link and button togheter you will create `linkbutton` folder for that matter. in the end we have something like this.

# configs

all constants and config goes in here

# hooks

only hooks that will be used more than once. and we have api folder in here again. the api folder contains only the hooks that will use `api` routes to commiunicate with server a nice place to put `tanstack-query` hooks.

# layout

auth layout - page layout - dashbaord layout will be placed in here.

`/partials` in this folder we keep `header`, `footer`, `aside` and layout parts of application.

# modules

contains modules

> [!NOTE]
> they are not big as page and not small as components. in fact they are something like widgets. imagine you have a component that you may use in diffrent pages or creating a modal system that handles different modals. or aa player component that comes to page by clicking on any button on the page. I'm hoping you get the idea. best example would be youtube player which can be minimized to lower corner of the page

# pages

just return the page component. nothing more. we should have a clean component and do the dirty stuff in app folder. maybe we just use this component to wrapping int around a HOC or using Helmet js inside it.

# routes

route navigation system only. using react-router-dom in here.

# services

in this file we make Axios interceptors. or any other services we might have.

# store

using `redux`, `zustand` stores we should not put contexts in here because we should not have global context at all. contexts are better to capsulate api inside of any other UI components.

# utils

helper functions and etc.

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ["./tsconfig.node.json", "./tsconfig.app.json"],
      tsconfigRootDir: import.meta.dirname,
    },
  },
});
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from "eslint-plugin-react";

export default tseslint.config({
  // Set the react version
  settings: { react: { version: "18.3" } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs["jsx-runtime"].rules,
  },
});
```
