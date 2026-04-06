# True Total Estimated Total Price Block

True Total is a frontend-only Shopify Theme App Extension designed to display the comprehensive final cost of a product, including estimated shipping and taxes, directly on the product page. By providing transparent pricing early in the buyer journey, this extension aims to reduce checkout friction and minimize cart abandonment.

## Key Features

* Precise Location Detection: Automatically identifies the visitor's city and country using IP-based geolocation via ipinfo.io.
* Real-Time Shipping Calculations: Utilizes the native Shopify AJAX API to retrieve actual shipping costs based on the merchant's specific store configuration and the visitor's location.
* International Tax Estimation: Includes a comprehensive tax and VAT matrix for major global markets, including North America, Europe, Asia, and Oceania.
* Integrated Tax Logic: Respects the Shopify "Taxes Included" setting to ensure accuracy and prevent redundant tax additions in the final estimate.
* Standalone Architecture: Operates entirely on the frontend without the requirement for a backend server or API tokens, ensuring a simplified deployment process.
* Customization Options:
    * Configurable message templates with placeholders for city, country, and price.
    * Adjustable font sizes and icon dimensions to maintain brand consistency.
    * Manual override settings for default shipping and tax rates.

## Installation and Configuration

1. Deployment: Deploy the extension to the target Shopify store using the Shopify CLI.
2. Integration:
    * Navigate to the Shopify Online Store, select Themes, and then Customize.
    * Open the Product Page template.
    * Add the Estimated Total block to the product information section.
3. Configuration:
    * Define default shipping and tax rates to serve as fallbacks for unmapped regions.
    * Customize the message template to align with the store's voice.
    * Adjust visual parameters, including font size and icon width, within the block settings.

## Technical Methodology

* Location Services: Precise geographical data, including City, ZIP code, and Province, is retrieved via the ipinfo.io API.
* Shipping Rate Retrieval: The extension employs a transient cart operation. It temporarily adds the selected product variant to a background cart, requests real-time shipping rates from the Shopify AJAX endpoint, and immediately removes the item. This method ensures that shipping costs are calculated based on the merchant's live shipping zones and product specifications.
* Tax Calculation: The final estimate combines the subtotal (product price and shipping) with a regional tax matrix to calculate estimated VAT or Sales Tax.
* System Resilience: In the event of an API failure or an unsupported region, the system automatically reverts to the merchant-defined default rates.

## Developer Documentation

* Shopify Theme App Extensions Documentation: https://shopify.dev/docs/apps/build/app-extensions/build-extension-only-app
* Shopify CLI Reference: https://shopify.dev/docs/apps/tools/cli

This extension is developed as a high-performance standalone solution for the Shopify platform.
