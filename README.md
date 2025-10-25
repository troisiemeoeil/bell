# Helmet Configurator

## Problem Aspects Solvable by a Program

- Allowing users to visually customize helmet features (color, finish, size, decals, environment).
- Providing instant feedback and previews for selections.
- Streamlining the process of selecting and ordering a customized helmet.

## Changes to the Original Process

- Replaces manual or paper-based selection with an interactive web interface.
- Reduces errors and ambiguity in customer choices.
- Speeds up the configuration and ordering process.

## Program Requirements

- Intuitive UI for customization.
- Real-time state management for selections.
- Responsive design for various devices.
- Integration with product images and environment maps.
- Option to add products to basket or find a dealer.

## Changes to the Operating Model

- Customers interact directly with the configurator, reducing the need for sales staff intervention.
- Dealers receive more accurate, pre-configured orders.
- The process becomes more self-service and scalable.

## Business Benefits: Customer Retention

- **Personalization:** Customers can tailor products to their preferences, increasing satisfaction and loyalty.
- **Engagement:** Interactive experience encourages longer site visits and repeat usage.
- **Accuracy:** Reduces errors in orders, improving customer trust and reducing returns.
- **Self-Service:** Empowers customers to explore options independently, freeing up sales resources.

## Technical Benefits: SEO

- **Client-Side Rendering:** Fast, interactive UI improves user experience metrics (dwell time, bounce rate).
- **Semantic HTML:** Use of headings, alt tags, and accessible navigation helps search engines index content.
- **Shareable URLs:** Configurator can be extended to generate shareable links for specific configurations.
- **Performance:** Lightweight, static deployment ensures fast load times, which is favored by search engines.

## Software Architecture

- **Frontend:** React-based single-page application (SPA) with modular components for maintainability.
- **State Management:** Valtio (`utils/store.jsx`) for reactive state updates.
- **Static Assets:** Assets like `.hdr` environment maps and `.glb` models are served from the `public` directory.
- **AR Integration:** `<model-viewer>` for AR functionality, ensuring cross-platform compatibility.
- **Hosting:** Static hosting platforms (e.g., Netlify, Vercel) for scalability and ease of deployment.

<img src="https://i.ibb.co/GQWcpsWg/flowchart.png" alt="Software Architecture Flowchart" style="width: 100%; max-width: 800px; height: 300px" />

**Reasoning:**  
This architecture enables fast, interactive UI updates and easy extensibility for new features.

## Ensuring Correct Functioning

- **Testing:**
  - Unit tests for individual components (e.g., `OuterShell.jsx`, `Sticker.jsx`) to ensure they render correctly.
  - Integration tests for the `Overlay.js` and `Customizer` components to verify the flow of the customization process.
  - Manual testing of AR functionality on supported devices (Android and iOS).
  - Cross-browser testing to ensure compatibility with Chrome, Safari, and Edge.

- **Error Handling:**
  - Add fallback UI for cases where assets (e.g., `.glb` models) fail to load.
  - Handle state-related errors gracefully in `utils/store.jsx`.

- **Performance Optimization:**
  - Optimize `.glb` models and images to reduce load times.
  - Use lazy loading for assets to improve initial page load performance.

## Usability Considerations

- **Responsive Design:**
  - The app is designed to work on both desktop and mobile devices, as evident from the AR functionality and the use of `<model-viewer>`.

- **Intuitive Navigation:**
  - The `Intro` and `Customizer` components provide a clear flow for users to start customizing their helmets.

- **Accessibility:**
  - Use of alt attributes for images (e.g., `<img src="./images/item-${color}.png" alt={color} />`) ensures screen reader compatibility.
  - AR button placement and styling make it easy to find and use.

- **Visual Feedback:**
  - Active states for buttons (e.g., `className={snap.color === color ? 'active' : ''}`) provide immediate feedback on user selections.

- **AR Integration:**
  - The AR feature allows users to visualize the helmet in their environment, enhancing the user experience and reducing uncertainty.

## How to Use the Program

1. Open the application in a web browser.
2. Start from the intro screen and click "Customize".
3. Select helmet options: finish, aspect, size, decals, environment.
4. Review the total price.
5. Use the "Try in AR" button to visualize the helmet in your environment.
6. Add to basket or find a dealer for purchase.
7. Use navigation and footer links for more information.

---

For more details, see the source code in [components/overlay/Overlay.js](components/overlay/Overlay.js) and [utils/store.jsx](utils/store.jsx).
---