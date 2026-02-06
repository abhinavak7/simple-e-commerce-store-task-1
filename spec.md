# Specification

## Summary
**Goal:** Build a simple e-commerce storefront with product browsing, cart, checkout-to-order flow, and order history, using Internet Identity login and Motoko canister persistence.

**Planned changes:**
- Implement Motoko single-actor data models and persistence for products, per-user carts, and per-user orders, including methods for product list/detail, cart CRUD, and order creation.
- Seed at least 6 demo products (id, name, price, description, image URL/path) so the UI works on fresh deploy.
- Add Internet Identity sign-in/sign-out on the frontend and scope cart/orders to the authenticated principal in backend calls.
- Create frontend pages/views: product listings (with basic sort/filter), product details (quantity + add to cart), cart (update/remove + totals), checkout (creates order, clears cart, shows confirmation), and account orders (list + detail).
- Apply a cohesive modern minimal theme across the UI (responsive; primary colors not blue/purple).
- Add generated static assets (logo, hero/banner, product placeholder) under `frontend/public/assets/generated` and wire them into header/listing/placeholder usage.

**User-visible outcome:** Users can sign in with Internet Identity, browse a seeded catalog, view product details, manage a persistent cart, place an order (without payments), see an order confirmation, and review past orders in an account area.
