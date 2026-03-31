# Paradise Nursery - E-Plant Shopping

A React + Redux shopping cart app for browsing plants, adding them to cart, updating quantities, and viewing cart totals.

## Live Demo

After deployment to GitHub Pages, your site URL will be:

https://<your-github-username>.github.io/e-plantShopping/

## Features

- Landing page with About Us section.
- Product catalog grouped by plant categories.
- Add to Cart button that disables and changes to Added to Cart once selected.
- Cart icon badge showing total quantity of items in cart.
- Cart page with:
  - Total amount for all items.
  - Per-item subtotal.
  - Increment and decrement quantity controls.
  - Remove item functionality.
  - Continue shopping navigation.

## Tech Stack

- React 18
- Redux Toolkit
- React Redux
- Vite
- ESLint
- gh-pages (for GitHub Pages deployment)

## Project Structure

e-plantShopping/

- src/
  - App.jsx
  - main.jsx
  - ProductList.jsx
  - CartItem.jsx
  - CartSlice.jsx
  - store.js
  - AboutUs.jsx
  - \*.css
- public/
- package.json
- vite.config.js

## Redux State Management

### Store

The global store is configured in src/store.js using configureStore from Redux Toolkit.

- cart slice key: cart
- reducer: cartReducer from CartSlice.jsx

### Cart Slice Actions

Defined in src/CartSlice.jsx:

- addItem: adds a product or increments quantity if already present.
- removeItem: removes an item completely by name.
- updateQuantity: updates the quantity for an existing cart item.

### Provider Setup

In src/main.jsx, App is wrapped with Provider and receives the global store:

<Provider store={store}>
	<App />
</Provider>

## Getting Started

### 1. Install dependencies

npm install

### 2. Run development server

npm run dev

### 3. Build for production

npm run build

### 4. Preview production build locally

npm run preview

### 5. Run lint checks

npm run lint

## Deployment to GitHub Pages

This project is configured to deploy with gh-pages.

### Scripts in package.json

- predeploy: npm run build
- deploy: gh-pages -d dist

### Vite base path

vite.config.js includes:

base: "/e-plantShopping/"

This must match your repository name.

### Deploy steps

1. Commit and push your latest code to main.
2. Run deployment:

npm run deploy

3. In GitHub repository settings:
   - Go to Settings > Pages.
   - Source: Deploy from a branch.
   - Branch: gh-pages.
   - Folder: /(root).
   - Save.
4. Wait 1-2 minutes and refresh the Pages section.
5. Open the generated site link.

## Notes

- If images or assets do not appear immediately after deployment, wait a few minutes and refresh.
- For every future update, run:

git add .
git commit -m "your message"
git push
npm run deploy
