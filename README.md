# True Total - Estimated Total Price Block

**True Total** is a lightweight, frontend-only Shopify Theme App Extension that helps customers see the *real* final cost of a product—including estimated shipping and taxes—directly on the product page. By showing the "True Total" early, you reduce checkout friction and abandoned carts.

## 🚀 Key Features

- **Dynamic Location Detection:** Automatically detects the visitor's City and Country via IP-based geolocation (using `ipinfo.io`).
- **Real-Time Shipping Rates:** Uses Shopify's native AJAX API to fetch actual shipping costs from your store's configuration for the visitor's specific location.
- **Global Tax Estimation:** Includes a built-in tax/VAT matrix for 14+ major global markets (US, CA, UK, EU, AU, JP, etc.).
- **Smart Tax Logic:** Automatically respects your store's "Taxes Included" setting to prevent double-charging in the estimate.
- **Zero-Backend / No Tokens:** Works entirely on the frontend. Merchants don't need to manage API tokens or setup complex backends.
- **Fully Customizable:**
  - Edit the message template using placeholders: `{city}`, `{country}`, and `{price}`.
  - Adjust font sizes and icon widths to match your theme's branding.
  - Set "Default Rates" for regions not covered by dynamic detection.

## 🛠️ Installation & Setup

1. **Install the Extension:** Deploy the app to your store via the Shopify CLI.
2. **Add the Block:**
   - Go to your **Online Store > Themes > Customize**.
   - Navigate to any **Product Page**.
   - Click **Add Block** in the product information section and select **Estimated Total**.
3. **Configure Settings:**
   - **Default Shipping/Tax:** Set fallback rates for when dynamic detection is unavailable.
   - **Message Template:** Customize the text (e.g., "Final total for {city}: {price}").
   - **Styling:** Adjust the font size and icon width to fit your design.

## 🧠 How It Works (Technical Detail)

- **Location:** Fetches precise location (City, ZIP, Province) via `ipinfo.io`.
- **Shipping:** Uses a "Silent Add" trick—temporarily adding the product to a hidden cart, fetching the real shipping rates from `/cart/shipping_rates.json`, and then immediately removing it. This ensures 100% accuracy based on your store's shipping zones.
- **Tax:** Combines the subtotal (Price + Shipping) with a regional tax matrix to estimate the final VAT or Sales Tax.
- **Resilience:** If any API fetch fails, the block gracefully falls back to your merchant-configured "Default Rates."

## 💻 Developer Resources

- [Shopify Theme App Extensions Documentation](https://shopify.dev/docs/apps/build/app-extensions/build-extension-only-app)
- [Shopify CLI Reference](https://shopify.dev/docs/apps/tools/cli)

---

Developed as a high-performance, standalone Shopify extension.
