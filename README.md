# ToDo App | Vite + TypeScript + React + Redux Toolkit + Tailwind (with SCSS modules)

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

## Project Structure Overview:

- `public` : Common static files (e.g., images, icons, fonts) and index.html used by the entire app. These files are directly served without processing.
- `assets` : Component-specific static files like images, icons, or fonts.
- `components` : Reusable UI components that make up your app (e.g., forms, lists, buttons).
- `constants` : Centralized static values or configurations (e.g., app settings, API URLs).
- `hooks` : Custom React hooks for encapsulating reusable logic.
- `pages` : Top-level components representing different pages or views in your app.
- `services` : API calls and other services for interacting with external systems.
- `store` : Redux Toolkit slices and global state management logic.
- `styles` : Necessary files for styling (reset and modules).
- `types` : TypeScript type definitions and interfaces.
- `utils` : Helper functions (e.g., localStorage handling, date formatting) to avoid repeated logic.
- `App.tsx` : The main app container, where routes and global providers (like Redux) are set up.
- `index.html` : The main HTML file that includes the root div for the React app.
- `index.scss` : The main stylization file that includes all necessary additional styling modules and Tailwind CSS layers 
- `main.tsx` : App entry point; mounts App.tsx into the DOM and initializes global configurations.
- `vite.env.d.ts` : TypeScript definitions for Vite-specific features like import.meta.
