# Responsive Laundry Hero Section - Learning Log

Hi! This is my submission for the CSS Laundry Services Responsive Layout assignment. I have reworked this project from scratch to focus on understanding responsive design principles, using exactly two breakpoints, and practicing structured layouts with Flexbox.

---

## 1. What is Responsive Design? (My Understanding)

Responsive design is an approach to web development where page layouts automatically adjust to fit the screen size and orientation of the device a user is on (whether it's a giant desktop monitor, an iPad, or a small mobile screen). 

Key concepts I focused on during this assignment:
*   **Fluid Layouts:** Using percentages (`%`) and relative units (`vh`, `vw`, `em`) instead of fixed pixels (`px`) so elements can scale dynamically.
*   **Media Queries:** CSS rules that apply specific styling blocks only when the viewport matches conditions like `max-width`.
*   **Flexible Media:** Ensuring images shrink and grow within their containers using properties like `max-width: 100%`.

---

## 2. Reworking the Breakpoints (Refactoring to Two Queries)

Initially, I had multiple complex breakpoints that made the code bloated and hard to maintain. For this version, I scaled back to exactly **two breakpoints** that target key devices:

1.  **Tablet View (`max-width: 1024px`):** 
    *   *Purpose:* Handles medium screens like laptops or iPads in portrait mode.
    *   *Adjustments:* Kept the layout side-by-side (flex-row) but reduced text sizes (`h1` goes from `56px` to `42px`), shrank the navbar padding, and reduced the image size to prevent text wrapping.
2.  **Mobile View (`max-width: 767px`):** 
    *   *Purpose:* Handles smartphones.
    *   *Adjustments:* Hid the central navigation links to save screen space, leaving only the logo and username. Stacked the columns vertically (`flex-direction: column`) with the text first and the image underneath.

*Note: I set the mobile query to `767px` instead of `768px`. This ensures that a standard iPad Mini screen (width `768px`) displays the tablet view (side-by-side layout) rather than triggering the stacked mobile view, which aligns with the sample outputs.*

---

## 3. Struggles and Problem Solving

During development, I ran into a few layout issues and had to experiment to fix them:

### Challenge 1: Navbar Layout Alignment
*   *Struggle:* At first, the navigation list items were wrapping awkwardly and stacking.
*   *Solution:* Instead of using `display: inline` or `display: inline-block` on the list items and trying to calculate margins, I applied `display: flex` to the parent `.nav-links` container. This instantly aligned the links horizontally, and I could easily adjust the spacing between them using the CSS `gap` property.

### Challenge 2: Image Overflowing on Mobile
*   *Struggle:* When switching the hero layout to `flex-direction: column` on mobile, the washing machine illustration was huge, extending off the side of the screen and causing horizontal scrolling.
*   *Solution:* I set the image width to `85%` with a maximum width limit of `320px` (`max-width: 320px`) inside the media query. This keeps the image sharp, centered at the bottom of the column, and fitting nicely on phone displays.

### Challenge 3: Text Alignment on Mobile
*   *Struggle:* I tried centering the text on mobile (`text-align: center`) because I thought it would look standard, but the text and the call-to-action button ended up looking disjointed.
*   *Solution:* I looked closely at the design mockups and realized left-aligned text (`text-align: left`) looked much cleaner. It keeps everything aligned with the brand logo and button on the left edge.

---

## 4. How to View the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/Simarpreetsaini/responsive-laundry-hero.git
   ```
2. Open `index.html` in any web browser.
3. Open Developer Tools (F12) and toggle device emulation to drag the screen width from desktop down to tablet and mobile to see the breakpoints in action!