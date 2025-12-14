# Project: Popoyo Shuttles - Technical Spec

## 1. Goal
Build a high-performance landing page for a private shuttle service in Popoyo, Nicaragua.
The site must be blazing fast (mobile-first) and optimized for conversion (WhatsApp Booking).

## 2. Tech Stack & Architecture
- **Framework:** Astro (Static Site Generation).
- **Styling:** Vanilla CSS (Scoped to components) OR Tailwind (if configured).
- **Deployment:** GitHub Pages.
- **Routing:** File-based routing (`src/pages/`).

## 3. Component Architecture (Astro Best Practices)
Do not build a monolithic HTML file. Break the UI into reusable chunks:

* **`layouts/Layout.astro`**: 
    * Contains the `<html>`, `<head>`, SEO tags, Favicon, and Global CSS.
    * Includes a `<slot />` for page content.
    * Includes `<Navbar />` and `<Footer />`.

* **`components/Navbar.astro`**:
    * Sticky header.
    * Logo (Text "Popoyo Shuttles" or SVG) on left.
    * Links: Rates, FAQ, Contact.

* **`components/RateCard.astro`**:
    * **Props:** `destination` (string), `price` (string), `duration` (string).
    * **Logic:** Renders a clean card with the price highlighted. Includes a "Book" button that links to a specific WhatsApp URL pre-filled with that destination.

* **`components/WhatsAppButton.astro`**:
    * **Props:** `message` (string), `label` (string).
    * **Logic:** Returns a standard styled button linking to `https://wa.me/19022137109?text={message}`.

## 4. Content & Data
* **Destinations:**
    * Managua Airport (MGA) - $90
    * Costa Esmeralda (ECI) - $50
    * San Juan del Sur - $45
    * Rivas / San Jorge - $35
    * Granada - $55
* **Trust Signals:** "Verified Local Drivers," "Pay Cash on Arrival," "24/7 Availability."
