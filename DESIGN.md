# UniCore — Design System

## 1. Visual Identity

UniCore is the academic platform for Universidad Abierta para Adultos (UAPA). Its visual identity must reflect UAPA's institutional branding while providing a modern, accessible, and intuitive user experience.

**Design direction:** Modern academic SaaS — clean layouts, strong visual hierarchy, restrained colors, and consistent components.

The interface should feel professional and welcoming, prioritizing usability and academic content over decoration.

### Brand principles

- **Institutional:** Preserve UAPA's recognizable navy blue and orange identity.
- **Clarity:** Make academic information easy to find and understand.
- **Consistency:** Maintain predictable patterns across all pages and user roles.
- **Accessibility:** Ensure readable typography, sufficient contrast, and keyboard-friendly interactions.
- **Responsive:** Deliver a seamless experience across desktop, tablet, and mobile devices.

## 2. Color Palette

Use UAPA's institutional navy and orange as the foundation of the visual identity. Complement them with neutral surfaces and semantic colors.

| Token | HEX | Usage |
|---|---|---|
| `primary-900` | `#101B46` | Deep navy, headings and navigation |
| `primary-800` | `#162456` | Primary buttons and brand elements |
| `primary-700` | `#233B78` | Hover and active states |
| `primary-100` | `#E9EEF9` | Selected navigation and subtle highlights |
| `accent-500` | `#FF8200` | Brand accent and important highlights |
| `accent-100` | `#FFF1DF` | Accent backgrounds |
| `background` | `#F7F8FA` | Main application background |
| `surface` | `#FFFFFF` | Cards, panels, and forms |
| `border` | `#E5E7EB` | Dividers and component borders |
| `text-primary` | `#172033` | Main text |
| `text-secondary` | `#64748B` | Supporting information |
| `success` | `#15803D` | Successful states |
| `warning` | `#D97706` | Warnings and pending states |
| `danger` | `#DC2626` | Errors and destructive actions |
| `info` | `#2563EB` | Informational states |

**Color usage guidelines:**
- Navy is the primary interface color.
- Orange is an accent, not a dominant background color.
- Use neutral backgrounds to separate content sections.
- Semantic colors communicate status, never decoration alone.
- Always maintain sufficient foreground/background contrast.

## 3. Typography

**Primary typeface: Inter**

Use Inter throughout the application for its readability, neutral appearance, and suitability for modern interfaces.

| Element | Size | Weight |
|---|---:|---:|
| Page title | 28–32px | 700 |
| Section heading | 20–24px | 600 |
| Card heading | 16–18px | 600 |
| Body text | 14–16px | 400 |
| Supporting text | 12–13px | 400 |
| Buttons and labels | 14px | 500–600 |

Use consistent line heights and avoid excessive font-weight variations. Prioritize readability in academic materials and long-form content.

## 4. Spacing & Layout

Follow an 8px-based spacing system to ensure consistent alignment and visual rhythm.

| Token | Value |
|---|---:|
| `space-1` | 4px |
| `space-2` | 8px |
| `space-3` | 12px |
| `space-4` | 16px |
| `space-6` | 24px |
| `space-8` | 32px |
| `space-12` | 48px |
| `space-16` | 64px |

### Application structure

- **Sidebar:** Primary navigation, approximately 250px on desktop.
- **Topbar:** Global actions, notifications, and user profile.
- **Main content:** Fluid layout on a neutral background.
- **Cards:** White surfaces with consistent padding and subtle borders.
- **Content width:** Use a reasonable maximum width when displaying long-form academic content.

### Responsive behavior

Design mobile-first, starting at a minimum supported viewport of 360px.

- Mobile: Collapsible navigation drawer or compact bottom navigation.
- Tablet: Adapted navigation and content grids.
- Desktop: Persistent sidebar and expanded content layout.
- Avoid horizontal scrolling and fixed-width content containers.

## 5. Components & UI Patterns

All components must follow shared design tokens and maintain consistent interaction states.

| Component | Guidelines |
|---|---|
| Buttons | Navy primary, neutral secondary, orange accent when appropriate |
| Inputs | White background, subtle border, visible focus state |
| Cards | White surface, 10–12px radius, subtle border |
| Badges | Muted semantic backgrounds and readable text |
| Navigation | Clear active state using navy and primary-100 |
| Tables | Consistent spacing, readable headers, responsive behavior |
| Modals | Clear hierarchy, accessible actions, restrained shadows |
| Alerts | Semantic colors with clear descriptions |

### Interaction states

Interactive components must provide consistent:
- Default state.
- Hover state.
- Focus-visible state.
- Active state.
- Disabled state.
- Loading state, when applicable.

Use Lucide icons consistently. Prefer icons accompanied by labels when their meaning might be ambiguous.

## 6. Surfaces, Borders & Elevation

- Border radius: 8–12px for standard components.
- Inputs and buttons: 6–8px.
- Cards: 10–12px.
- Borders: Prefer subtle neutral borders over heavy shadows.
- Shadows: Use sparingly for dropdowns, dialogs, and floating elements.
- Avoid gradients, excessive shadows, decorative effects, and unnecessary visual complexity.

## 7. Accessibility

Follow WCAG 2.2 AA as the accessibility target.

- Maintain sufficient text and component contrast.
- Support keyboard navigation and visible focus indicators.
- Associate form labels with their inputs.
- Never communicate status through color alone.
- Use semantic HTML elements and appropriate ARIA attributes.
- Respect reduced-motion preferences.
- Ensure interactive targets are comfortable to use on touch devices.

## 8. Implementation Guidelines

The global stylesheet lives in `css/styles.css`.

Organize styles around reusable design tokens and shared foundations:

1. CSS custom properties (design tokens).
2. CSS reset and base styles.
3. Typography and global elements.
4. Layout utilities and responsive foundations.
5. Shared component styles.
6. Accessibility and interaction states.

Use CSS variables for colors, typography, spacing, borders, and other reusable values. Avoid hardcoded design values when an existing token applies.

Components should consume shared tokens rather than introduce independent visual styles.

## 9. Design References

Use these products as inspiration, not as templates to copy:

- **UAPA:** [Official institutional identity](https://www.uapa.edu.do/nosotros/identidad-institucional/) — brand identity and visual consistency.
- **Canvas LMS:** [Student dashboard](https://community.canvaslms.com/) — course organization and academic workflows.
- **D2L Brightspace:** [Official website](https://www.d2l.com/brightspace/) — academic navigation and learning experience.
- **Penpot:** [Design and prototyping](https://penpot.app/) — interface design, reusable components, and prototypes.

**Final direction:** UniCore should look and feel like a modern evolution of UAPA's digital academic experience: recognizable institutional branding, intuitive navigation, clean academic dashboards, and a consistent responsive interface.
