# SIDZ CAFE

A clean, responsive static website for a local cafe/restaurant called SIDZ CAFE. This repo contains the site pages, styles, and a small client-side shopping cart that uses a local `dishes.json` file as its menu data source.

---

## Highlights

- Simple, static HTML/CSS/JavaScript site — no build step required.
- Menu data stored in `dishes.json` (over 700 lines of menu items across pizzas, shakes, snacks, and more).
- Client-side shopping cart UI (`shoppingcartjs.js`) that toggles a cart panel and loads menu items from `dishes.json`.
- Multiple menu pages: Italian, Chinese, American, Indian, Breakfast, Lunch, Shakes, Mocktails.
- Included screenshots in the `menu/` folder that showcase UI and layout.

---

## Repository structure (important files)

- `index.html` — Home page with menu entry points, banner, and embedded Google Map.
- `style.css` — Base site styles.
- `index.js`, `script.js` — Small interactive scripts for sliders/navigation.
- `shoppingcartjs.js` — Shopping cart behavior (open/close, load products from `dishes.json`).
- `dishes.json` — JSON array of products used by the site (id, name, price).
- `italian.html`, `chinese.html`, `american.html`, `indian.html`, `breakfast.html`, `lunch.html`, `shakes.html`, `mocktails.html` — Menu category pages (each with its own CSS file like `italianstyle.css`, etc.).
- `menu/` — Contains several screenshot images used for previews.

(There are additional CSS files for page-specific styling: `menustyle.css`, `americanstyle.css`, `chinesestyle.css`, `indianstyle.css`, `breakfaststyle.css`, `shakesstyle.css`, `mocktailsstyle.css`.)

---

## What I found while inspecting the code

- The site fetches `dishes.json` from `shoppingcartjs.js` to initialize the menu: initApp -> fetch('dishes.json') -> store in `listProducts`.
- The shopping cart UI toggles by adding/removing a `showcart` class on the `body`.
- `script.js` contains logic to create horizontally-scrollable dish containers with next/previous buttons.
- `index.js` appears to contain leftover example code (console logs / a sample `interestRate` variable) and may not be needed in production.

---

## Run / Preview locally

Since this is a static site you have two easy options:

1) Open the site directly in a browser

- Double-click `index.html` or open it from your browser (works for basic previews). Some browsers restrict fetch() from local files — if you see the menu not loading, use option 2.

2) Start a simple HTTP server (recommended)

- If you have Python 3 installed, from the project root run:

```powershell
# from repository root e:\Github\Sidz Cafe\sidz-cafe
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

- Or use Node's `http-server` (if you prefer):

```powershell
# install once (globally)
npm install --global http-server
# run from repo root
http-server -p 8000
# then open http://localhost:8000
```

Note: Because the app fetches `dishes.json`, serving via HTTP avoids CORS/file:// fetch restrictions.

---

## Usage notes

- The menu is sourced from `dishes.json` (id, name, price). You can edit that file to add/remove or change items.
- The cart UI currently toggles but does not fully implement add/remove/checkout flows — there are placeholders (e.g., `alert('1')` in `shoppingcartjs.js` when an `.addcart` element is clicked).
- `index.js` contains sample JS lines and sets `interestRate` in a way that causes an assignment to a const — consider cleaning or removing it.

---

## Suggested improvements (low-risk)

- Implement full add-to-cart flow (create cart item structure, persist cart in localStorage).
- Replace `alert('1')` with a proper add-to-cart handler.
- Remove or fix unused sample code in `index.js`.
- Add a minimal automated preview step in `package.json` (optional) to make local serving easier.
- Add semantic markup and ARIA attributes for accessibility improvements.

---

## Screenshots

There are example screenshots inside the `menu/` folder (e.g. `menu/Screenshot_20240628-154629.jpg`) you can use in the README or GitHub project page for visuals.

---

## License & Contributing

- This project doesn't currently include a LICENSE file. If you plan to publish, add an appropriate license (MIT, Apache-2.0, etc.).
- Contributions: open issues or PRs. If you want, I can help by opening a PR that implements the add-to-cart flow and localStorage persistence.

---

## Contact / Author

SIDZ CAFE — repo maintained in this workspace. For development help or to request features, open an issue or create a pull request.

---

Thank you for sharing this repo — I created this README to help visitors understand, preview, and contribute to the site. If you want, I can also:

- Add a `LICENSE` file (suggest MIT).
- Implement the add-to-cart flow and 1-2 unit tests for cart logic.
- Clean up `index.js` and link proper scripts only where needed.

If you want any of those next steps done now, tell me which one and I'll proceed.
