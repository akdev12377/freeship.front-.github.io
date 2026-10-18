# LIZE storefront

Premium clothing storefront: Home, Shop, Brand Story, product details, procedural 3D previews, wishlist and bag. Includes 120 demo products in the standalone preview.

## Preview now

Open `preview.html` in a browser. This read-only offline preview uses demo data; it does not connect to the backend. Management screens in this preview are intentionally unlocked and contain no private data.

## Connect the real backend

1. Deploy the private `akdev12377/freeship.back` repository on Render using its `render.yaml`.
2. Set `window.LIZE_API_URL` in `config.js` to the exact returned HTTPS backend URL, without a trailing slash. No secret belongs in this public file.
3. Publish this repository through GitHub Pages (main branch, root directory), Render Static Sites, or another static host.
4. For GitHub Pages, the expected project path is `https://akdev12377.github.io/freeship.front-.github.io/`. Asset links are relative to support this path. Hosting has not been enabled or verified by this source push.
5. Confirm the backend `CORS_ALLOWED_ORIGINS` includes the storefront origin. The included backend configuration permits `https://akdev12377.github.io`. If you use a different host/domain, update that value to the exact origin (no path).

Store management opens on the backend domain so admin cookies stay first-party. The public storefront does not receive the admin password. Blank `LIZE_API_URL` means same-origin API mode; GitHub Pages cannot run the Python backend and shows a connection message until configured.

## Local storefront check

Run `python -m http.server 8080`, visit localhost:8080, and open the offline preview; to use a running backend, configure its URL and allow the exact frontend origin on that backend. Run `node test_ui.cjs` for rendering/filter checks. Layout and 3D interaction still require browser QA.

The illustrations and 3D volumes are simplified concept assets, not realistic garment scans. Checkout is for demo orders only; no payments or shipping are connected.
