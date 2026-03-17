# THALA 7 — Pure CSS Sneaker Store

A fully functional multi-page sneaker e-commerce UI built with **zero JavaScript**. All interactivity — page navigation, product selectors, payment tabs, and order confirmation — is powered entirely by HTML and CSS.

---

## 📁 Project Structure

```
thala7-no-js/
└── thala7-no-js.html     # Single self-contained file (HTML + CSS)
```

No build tools, no dependencies, no frameworks. Just open the file in a browser.

---

## 🚀 Getting Started

```bash
# Clone or download the file, then simply open it:
open thala7-no-js.html
```

Or drag and drop `thala7-no-js.html` into any modern browser. No server required.

---

## 🗂️ Pages

The app has four pages, all in a single HTML file:

| Page | ID | Description |
|---|---|---|
| Landing | `#page-landing` | Hero section with shoe showcase and stats bar |
| Product | `#page-product` | Product detail with size/color picker and gallery |
| Cart | `#page-cart` | Cart table with order summary sidebar |
| Payment | `#page-payment` | Checkout form with multi-method payment tabs |

---

## ✨ Features

### Working (Pure CSS)
- **Multi-page navigation** — anchor links + CSS `:target` selector
- **Size selector** — radio inputs styled as toggle buttons
- **Color picker** — radio inputs styled as circular swatches
- **Payment method tabs** — radio inputs switching between Card, UPI, Crypto, Net Banking, Wallet panels
- **Order confirmation overlay** — checkbox toggle reveals a full-screen modal
- **All animations** — floating shoe, fade-up text, page transitions, bounce effect
- **Scroll gallery** — horizontal scroll with snap points
- **Sticky sidebar** — order summary stays fixed while scrolling
- **Responsive layout** — collapses to single-column on screens below 960px
- **Hover effects** — buttons, cards, color swatches, gallery items

### Static (JS required for full functionality)
| Feature | Reason |
|---|---|
| Cart total calculation | Requires arithmetic on dynamic values |
| Quantity +/− in cart | Requires DOM state mutation |
| Live card number preview | Requires input event listeners |
| Coupon code validation | Requires string comparison logic |
| Remove cart item | Requires DOM removal |
| Dynamic cart badge count | Requires running total |

---

## 🧠 CSS Techniques Used

### `:target` Page Routing
```css
/* Show a page when its ID is in the URL hash */
#page-product:target { display: block; }

/* Hide landing when another page is targeted */
body:has(#page-product:target) #page-landing { display: none; }
```

### Radio-Powered Tabs
```css
/* Show payment panel based on which radio is checked */
#tab-card:checked  ~ .pay-panels #ppanel-card  { display: block; }
#tab-upi:checked   ~ .pay-panels #ppanel-upi   { display: block; }
```

### Checkbox Modal Toggle
```css
/* Confirmation overlay appears when checkbox is checked */
#orderDone:checked ~ .confirm-overlay { display: flex; }
```

### Styled Radio Inputs as Buttons
```css
/* Hide the actual radio, style its label */
input[type="radio"] { display: none; }
input[type="radio"]:checked + label {
  background: var(--accent);
  border-color: var(--accent);
  color: #fff;
}
```

---

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| `--black` | `#0a0a0a` | Page background |
| `--white` | `#f5f0eb` | Primary text |
| `--accent` | `#ff3c1f` | CTAs, highlights, prices |
| `--blue` | `#2d81f7` | Checkout button, payment tab active |
| `--green` | `#4caf82` | Discounts, success states |
| `--card` | `#141414` | Card backgrounds |
| `--muted` | `#888` | Secondary text, labels |

**Fonts:** `Bebas Neue` (display/headings) + `DM Sans` (body/UI) via Google Fonts

---

## 🌐 Browser Support

| Browser | Support |
|---|---|
| Chrome 105+ | ✅ Full |
| Firefox 121+ | ✅ Full |
| Safari 15.4+ | ✅ Full |
| Edge 105+ | ✅ Full |

> Requires `:has()` support for the page routing system. All modern browsers support this. IE is not supported.

---

## 📦 Dependencies

| Resource | Purpose | Source |
|---|---|---|
| Bebas Neue | Display font | Google Fonts |
| DM Sans | Body font | Google Fonts |
| Product images | Shoe photography | Unsplash (free to use) |

No npm packages. No JavaScript libraries. No CSS frameworks.

---

## 🔧 Customization

### Changing the accent color
Edit the CSS variable at the top of the `<style>` block:
```css
:root {
  --accent: #ff3c1f; /* Change this */
}
```

### Adding a new page
1. Add a new `<div class="page" id="page-newpage">` section
2. Link to it with `<a href="#page-newpage">`
3. Add a CSS rule to hide landing when it's targeted:
```css
body:has(#page-newpage:target) #page-landing { display: none; }
```

### Adding a new size
```html
<input type="radio" name="size" id="sz12" />
<label for="sz12">12</label>
```

---

## 📄 License

Free to use for personal and educational projects.
