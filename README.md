# EB-box Front-end

Modern web application for **EBBOX Kft.** (Csorvás), a pet food and livestock feed retail store. Visitors can browse the product catalog, filter by price and weight, view promotions, and contact the store directly.

---

## ✨ Features

- **Homepage hero slider** – automatic image rotation with featured content
- **Service highlights** – opening hours, product range, free delivery, premium quality
- **Sale products strip and modal** – featured deals with coupon functionality
- **Category picker** – pets (`/categories/pets`) and livestock (`/categories/livestock`)
- **Product listing** – card layout with detailed product info dialog
- **Advanced filtering** – text search, price range, weight filter (g / kg / pcs / l), price sorting
- **Pagination** – Material paginator with Hungarian localization
- **Contact form** – validation, reCAPTCHA, EmailJS integration
- **Map and Facebook feed** – Google Maps embed and Facebook page integration
- **Customer testimonials** – testimonial section
- **Responsive design** – mobile and desktop views
- **Scroll to top** button for easier navigation

---

## 🛠 Tech stack

| Category | Technology |
|----------|------------|
| Framework | [Angular 20](https://angular.dev/) |
| Language | TypeScript |
| Styling | Tailwind CSS 4, SCSS |
| UI components | Angular Material |
| State management | NgRx Store, Effects, Router Store, LocalStorage sync |
| Reactive programming | RxJS |
| Forms / email | Angular Reactive Forms, EmailJS |
| Date handling | dayjs |
| Build tool | Angular CLI (`@angular/build`) |
| Testing | Jest |
| Lint / formatting | ESLint, Prettier |

---

## 🚀 Installation / Running locally

### Prerequisites

- Node.js 20+
- npm, pnpm, or yarn

### Steps

```bash
git clone https://github.com/lali1998/ebbox-front-end.git
cd ebbox-front-end
npm install
npm start
```

The dev server runs at **http://localhost:4200/** by default.

### Build

```bash
npm run build
```

Build output goes to the `dist/ebbox-front-end/` directory.

### Other commands

```bash
npm run lint              # Run ESLint
npm run test              # Jest tests (watch mode)
npm run build-source-map  # Production build with source maps
```

> **Note:** The project includes a `pnpm-lock.yaml` file. If you use pnpm: `pnpm install` → `pnpm start`.

---

## 📖 Usage

### Homepage

1. Open the homepage – the hero slider, service highlights, and sale strip appear automatically.
2. Scroll down to the **Location** section: map, Facebook feed, and store photos.
3. On the **Send us a message** form, fill in the fields, complete the reCAPTCHA check, then submit.

### Browsing products

1. Click **Categories** in the header, or choose a **Pets** / **Livestock** category card.
2. Use the filter panel on the right to search by name, set price and weight ranges, and sort by price.
3. Click a product card for detailed information.
4. Use the **Contact** button to automatically insert product details into the message field.

### Promotions

- A sale products modal may appear when the page loads.
- The strip shows a scrollable list of discounted products.

---

## 👨‍💻 Developer info

### Project structure

```
src/app/
├── pages/                    # Page-level components
│   ├── home/                 # Homepage (map, promo, testimonials)
│   └── product-category/     # Product category page + filter
├── shared/
│   ├── components/           # Reusable UI components
│   ├── layouts/              # Header, footer
│   ├── services/             # Theme, pagination, modal services
│   ├── mocks/                # Product mock data
│   └── core/                 # Routing, app config, meta reducers
└── store/                    # NgRx product state
public/                       # Static assets (images, robots.txt)
```

### Architecture

- **Standalone components** with Angular 20 and `OnPush` change detection
- **Zoneless change detection** for better performance
- **NgRx** for product filtering, pagination, and state persistence (localStorage / sessionStorage)
- **Hungarian localization** (`hu-HU`) for prices and paginator labels
