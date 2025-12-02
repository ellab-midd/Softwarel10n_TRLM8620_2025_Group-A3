# Softwarel10n_TRLM8620_2025_Group-A3
Final project submission for TRLM8620 Fall 2025 Group A3

# TRLM8620-Final
This is the final project for TRLM8620. Our group is Group A3: Ella Barton, James Kuba, Jonathan Myers and Marley Uyemura. Here we have cloned the final project repository and created our l10n/i18n-readiness plan, shopping website by switching the content in Japanese, and fully localized website without any hard-coded strings, incorrect date, time and currency formatting, or truncation.

## Project Overview
Galaxy L10n Supplies is an e-commerce website that has been fully internationalized and localized for both English (en-US) and Japanese (ja-JP) markets. The project demonstrates proper i18n implementation including string externalization, locale-aware formatting, and culturally appropriate UI adaptations.

## Internationalization (i18n) Implementation

### 1. String Externalization
All user-facing strings have been externalized from the codebase into locale-specific resource files:
-English locale: `src/content/en-US/strings.json`
-Japanese locale: `src/content/ja-JP/strings.json`

**Main areas that were externalized:**
- Navigation labels (HOME, DROIDS, VEHICLES)
- Product titles and descriptions (13 products)
- Form labels and placeholders
- Button text and CTAs
- Error messages and status indicators
- Shopping cart and checkout flow text

### 2. Locale-Aware Date Formatting
The `i18n.formatShortDate()` function provides culturally appropriate date formats:
- **English (en-US)**: MM/DD/YYYY (e.g., 12/01/2025)
- **Japanese (ja-JP)**: YYYY年MM月DD日 (e.g., 2025年12月01日)

Date formatting is applied to:
- Order history dates
- Order placement timestamps
- All date displays throughout the application

### 3. Currency Formatting
The `i18n.formatCurrency()` function uses `Intl.NumberFormat` for proper currency display:
- **English (en-US)**: USD with $ symbol (e.g., $1,234.56)
- **Japanese (ja-JP)**: JPY with ¥ symbol (e.g., ¥1,234)

Currency formatting appears in:
- Product prices
- Shopping cart totals
- Order history
- Checkout page

### 4. Locale-Specific Form Elements
The checkout page includes locale-aware form input ordering:
- **Credit Card Expiration Date**:
  - English: Month/Year (MM/YY)
  - Japanese: Month/Year (月/年) with Japanese labels
- **Name Fields**:
  - English: First Name, Last Name
  - Japanese: 名 (given name), 姓 (family name)
- **Input Placeholders**:
  - Credit card format: 1234 5678 9012 3456 (standard 16-digit format)
  - Security code: 123 (3-digit CVV)

### 5. Dynamic Asset Loading
The application dynamically loads locale-specific assets:
- **Logos**:
  - English: `img/logo.png`
  - Japanese: `img/logo-jp.png`
- **Terms and Conditions**:
  - English: `src/static/en-US/terms.html`
  - Japanese: `src/static/ja-JP/terms.html`

### 6. UI/UX Adaptations for Japanese

**Navigation Bar Adjustments:**
- Greeting text reduced in size and split across two lines for better fit
- Japanese text: "こんにちは、G11Nウォリアー" (Hello, G11N Warrior)
- Adjusted spacing and layout to accommodate longer Japanese text

**Language Selector:**
- Globe emoji 🌐 instead of text label for universal recognition
- Inline layout with flexbox for compact display
- Options: "English (USA)" and "日本語（日本）"

**Typography Considerations:**
- Japanese text properly renders with appropriate line-height
- No text truncation issues
- Proper character encoding (UTF-8) throughout
- Proper Japanese fonts

## File Structure

### Core i18n Service
- `src/services/i18n.js` - Central internationalization service handling:
  - String retrieval (`getString()`)
  - Currency formatting (`formatCurrency()`)
  - Date formatting (`formatDate()`, `formatShortDate()`)
  - Locale-specific HTML file paths (`getHTML()`)

### Modified Components
- `src/views/components/Navbar.js` - Dynamic logo, locale selector
- `src/views/pages/Home.js` - Externalized welcome messages
- `src/views/pages/Checkout.js` - Locale-aware form elements
- `src/views/pages/OrderHistory.js` - Currency and date formatting
- `src/views/classes/Order.js` - Date formatting and status strings
- `src/css/style.css` - Japanese text layout adjustments

## Features Implemented

### Locale Detection and Switching
- User can switch between en-US and ja-JP via language selector
- Entire UI updates dynamically on locale change

### Proper Number and Date Handling
- Uses native JavaScript `Intl` APIs
- Respects locale conventions
- Handles Japanese year/month/day order
- Currency symbols and decimal places appropriate to locale

### Cultural Adaptations
- Japanese date format with 年月日 suffixes
- Appropriate name field ordering
- Locale-specific logos and branding
- Translated terms and conditions

## Testing Considerations

**Verify the following in both locales:**
1. All text displays correctly without truncation
2. Dates appear in the correct format
3. Currency symbols and amounts are properly formatted
4. Form inputs have appropriate placeholders
5. Product descriptions are fully translated
6. Checkout flow works with locale-specific formats
7. Order history displays correctly

## Future Enhancements
- Localized shipping options and costs 
