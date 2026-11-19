# FRONTEND.md — Frontend Development Guidelines

## 1. Technology Stack

- Use **HTML5, Tailwind CSS, and Vanilla JavaScript** as the default stack.
- Do not use React, Vue, Angular, or other frontend frameworks 
- Prefer lightweight solutions with minimal dependencies.
- Use jQuery only when genuinely necessary, especially for advanced components or existing integrations.
- Libraries such as Chart.js, DataTables, and similar tools are acceptable when they provide meaningful functionality.
- Avoid unnecessary JavaScript libraries and dependencies.

## 2. HTML Standards

- Always use semantic HTML5 elements.
- Use appropriate elements: `header`, `nav`, `main`, `section`, `article`, `aside`, and `footer`.
- Use proper heading hierarchy (`h1` through `h6`). Every page should have one primary `h1`.
- Use `<button>` for actions and `<a>` for navigation.
- Use native HTML elements whenever possible instead of recreating their behavior with JavaScript.
- Always define character encoding (`UTF-8`) and viewport metadata.
- Add meaningful `title` and meta description tags.
- Use descriptive `alt` attributes for meaningful images.
- Ensure all forms have properly associated labels.
- Use appropriate input types (`email`, `number`, `date`, etc.).
- Avoid unnecessary nested elements and excessive wrapper divs.
- Validate HTML markup and fix structural errors.

## 3. CSS and Styling

- Use Tailwind CSS utility classes as the primary styling method.
- Avoid writing custom CSS unless Tailwind cannot reasonably handle the requirement.
- Keep custom CSS organized and reusable.
- Avoid excessive inline styles.
- Maintain consistent spacing, typography, colors, borders, and corner radiuses.
- Use a consistent design system rather than arbitrary styling values.
- Prefer CSS Grid and Flexbox for layouts.
- Use CSS variables for reusable design tokens when appropriate.
- Avoid unnecessary animations and transitions.
- Ensure hover, focus, active, disabled, and loading states are properly designed.

## 4. Visual Design and UX

- Aim for professional, modern, polished, and production-quality interfaces.
- Avoid generic, amateur-looking layouts and excessive decorative elements.
- Establish a clear visual hierarchy.
- Use consistent typography and a limited color palette.
- Provide sufficient whitespace and avoid overcrowded layouts.
- Make navigation intuitive and predictable.
- Design buttons, forms, tables, cards, and dialogs consistently.
- Provide visual feedback for user interactions.
- Use skeleton loaders or loading indicators for asynchronous operations when appropriate.
- Display meaningful empty states and error messages.
- Avoid unnecessary gradients, shadows, borders, and animations.
- Do not use emojis as interface icons. Prefer SVG icons or a consistent icon library.

## 5. Responsive Design

- Use a mobile-first design approach.
- Support mobile phones, tablets, laptops, and desktop screens.
- Use responsive Tailwind breakpoints.
- Avoid fixed widths that cause horizontal scrolling.
- Ensure navigation adapts to smaller screens.
- Make tables usable on mobile, using horizontal scrolling or responsive layouts where appropriate.
- Ensure buttons and interactive elements have adequate touch targets.
- Test layouts at different viewport sizes.

## 6. JavaScript

- Use Vanilla JavaScript by default.
- Prefer modern JavaScript (ES6+).
- Use `const` by default and `let` when reassignment is necessary.
- Avoid global variables and unnecessary global functions.
- Organize code into small, reusable functions.
- Separate frontend behavior from HTML markup.
- Use event delegation when appropriate.
- Use `addEventListener` instead of inline event handlers.
- Use `fetch()` and async/await for API requests.
- Handle network errors and unexpected responses.
- Avoid blocking operations and unnecessary DOM manipulation.
- Use `textContent` instead of `innerHTML` for untrusted text.
- Clean up event listeners and resources when necessary.

## 7. jQuery and Third-Party Libraries

- Use jQuery only when it significantly simplifies a complex interaction or integrates with an existing component.
- Do not introduce jQuery merely for basic DOM manipulation or event handling.
- Chart.js is acceptable for charts and data visualization.
- Use DataTables or similar libraries for advanced table functionality when necessary.
- Prefer libraries that are actively maintained and have minimal dependencies.
- Avoid loading multiple libraries that provide overlapping functionality.
- Keep third-party libraries and their versions documented.

## 8. Accessibility

- Follow WCAG accessibility guidelines.
- Ensure keyboard navigation works throughout the application.
- Provide visible focus indicators.
- Use appropriate ARIA attributes when native HTML semantics are insufficient.
- Ensure sufficient color contrast.
- Do not communicate important information through color alone.
- Support screen readers with meaningful labels and descriptions.
- Make dialogs and dropdowns keyboard accessible.
- Respect reduced-motion preferences.

## 9. Images, Icons, and Favicons

- Always check whether the project already contains a favicon before making changes.
- If a favicon exists, preserve it unless replacement is requested.
- If no favicon exists, create or recommend a suitable favicon.
- Include appropriate favicon references in the HTML document.
- Support standard favicon formats and sizes where appropriate.
- Use SVG icons whenever possible.
- Optimize images before using them.
- Use modern image formats such as WebP or AVIF when appropriate.
- Specify image dimensions to reduce layout shifts.
- Use lazy loading for below-the-fold images.

## 10. SEO and Metadata

- Give every page a meaningful and unique title.
- Include a relevant meta description.
- Use canonical URLs when appropriate.
- Use semantic HTML and descriptive link text.
- Include Open Graph metadata when social sharing matters.
- Use structured data (Schema.org) when relevant.
- Avoid duplicate IDs and misleading page metadata.

## 11. Performance

- Minimize JavaScript and CSS payloads.
- Avoid unnecessary dependencies and third-party requests.
- Load scripts with `defer` when appropriate.
- Lazy-load images and non-critical resources.
- Avoid layout shifts and unnecessary reflows.
- Use browser caching and compression where supported by the server.
- Optimize fonts and avoid loading unnecessary font weights.
- Prefer efficient DOM operations.
- Measure performance rather than optimizing blindly.

## 12. Security

- Never trust user-provided input.
- Avoid inserting untrusted content using `innerHTML`.
- Prevent XSS by properly escaping and sanitizing dynamic content.
- Never expose API keys, secrets, or credentials in frontend code.
- Validate input on both frontend and backend.
- Use HTTPS for external requests.
- Avoid unsafe third-party scripts.
- Do not rely on frontend validation as a security boundary.

## 13. Code Organization

- Keep HTML, CSS, and JavaScript logically separated.
- Use descriptive filenames and variable names.
- Avoid duplicating components or functionality.
- Keep JavaScript modules small and focused.
- Avoid unnecessary abstractions.
- Do not introduce build tools or complicated frontend infrastructure unless needed.
- Follow the existing project structure and conventions.

## 14. Final Quality Checklist

Before considering frontend work complete:

- [ ] HTML structure is semantic and valid.
- [ ] Tailwind CSS is used consistently.
- [ ] No unnecessary frontend frameworks or dependencies.
- [ ] Existing favicon has been checked and preserved.
- [ ] Responsive behavior works on mobile and desktop.
- [ ] Forms have labels and appropriate validation.
- [ ] Keyboard navigation and focus states work.
- [ ] Loading, empty, success, and error states are handled.
- [ ] No obvious console errors or warnings.
- [ ] Images and assets are optimized.
- [ ] Page metadata is present and meaningful.
- [ ] No secrets or unsafe handling of user input.
- [ ] Overall design looks polished and production-ready.
