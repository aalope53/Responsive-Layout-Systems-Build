# CSS-Architecture-Package

Refactoring Evidence

Before: Colors, spacing, border radiuses, font sizes, and other repeated design values could be written manually throughout the stylesheet, making it harder to keep the design consistent.

After: I created custom properties in :root for repeated design decisions such as --color-primary, --space-md, --radius-medium, and --focus-color. Components can reuse these values instead of repeating the same values throughout the CSS.   styles
-----------------------------------------------------------------------------------------------------------------
Before: Repeated elements such as cards could require separate CSS for common visual properties and interactions.

After: I grouped components that share styles. For example, .featured-card and .social-card share their border, border radius, margin, hover movement, shadow, and active state. This reduces duplicated declarations.   styles
-----------------------------------------------------------------------------------------------------------------
Before: Small changes such as centering text or adding spacing could require repeating properties or creating more specific selectors.

After: I created utility classes such as .text-center, .margin-top-lg, and .max-width-text. Each utility performs one predictable job and can be reused on different elements without increasing selector specificity.   styles
-----------------------------------------------------------------------------------------------------------------
Before: CSS names could describe appearance rather than the purpose of an element, making the stylesheet harder to understand as the website grew.

After: I used descriptive names based on each element's role, such as .site-header, .project-grid, .featured-card, .project-card, .social-card, and .social-card-content. This makes it easier to understand which part of the website each rule controls.   styles
-----------------------------------------------------------------------------------------------------------------

Architecture Notes 

Layer/order strategy: I organized the stylesheet using the layer order reset, base, layout, components, utilities, and overrides. The reset removes browser defaults, base contains global styles and design tokens, layout controls major page structures, components contain reusable interface elements, utilities provide small reusable adjustments, and overrides contain higher-priority states such as keyboard focus and the current navigation page.   styles   styles

Token decisions: I created tokens for colors, typography, spacing, shape, and focus. For example, the --space-* variables provide consistent spacing sizes, the --radius-* variables keep rounded corners consistent, and the color variables establish a reusable site-wide color palette. This allows major design decisions to be changed from one location.   styles

Naming approach: I used class names based on the purpose of an element. Names such as .featured-card, .project-card, .project-card-text, .social-card, and .nav-list make it clear what each rule controls. Utility names such as .text-center and .margin-top-lg instead describe the single styling change they apply.   styles   styles

Browser checks: I tested hover, active, keyboard :focus-visible, and the aria-current="page" navigation state. I also would use the browser's print preview to check the print-specific styles, including card page breaks, visible project information, reduced spacing, and black-and-white-friendly sections.

AI Disclosure: Some AI was used to make the CSS, mostly for the cards and the print, otherwise everything else was made by hand. AI was also used briefly for the refactoring evidence and notes to word it a little better, specifically the wording of the before and after portions.