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

See [section 9](#9-html-guide) for the HTML contracts and class reference.

## 9. HTML Guide

`css/styles.css` implements entire design directions. Use semantic HTML first; classes describe layout or intent. Do not add per-screen CSS when a shared class exists.

### Setup

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="css/styles.css">
```

Icons are Lucide SVGs. Use a local sprite so markup stays short:

```html
<svg class="icon" aria-hidden="true"><use href="icons.svg#user"></use></svg>
```

### Page shell

```html
<div class="app">
  <aside class="sidebar">
    <div class="sidebar__brand">
      <a class="brand" href="#">
        <span class="brand__mark"><span></span><span></span><span></span><span></span></span>
        <span class="brand__text">
          <span class="brand__name">UniCore</span>
          <span class="brand__institution">UAPA</span>
        </span>
      </a>
    </div>

    <nav aria-label="Principal">
      <div class="nav-group">
        <p class="nav-label">Principal</p>
        <a class="nav-item" href="#" aria-current="page">
          <svg class="icon" aria-hidden="true"><use href="icons.svg#home"></use></svg>
          Inicio
        </a>
        <a class="nav-item" href="#">
          <svg class="icon" aria-hidden="true"><use href="icons.svg#users"></use></svg>
          Usuarios
          <span class="nav-item__count">12</span>
        </a>
      </div>
    </nav>

    <div class="sidebar__footer">
      <div class="term-card">
        <span class="term-card__label">Trimestre actual</span>
        <div class="term-card__row">
          <span class="term-card__code">2026-34</span>
          <span class="badge badge-primary badge-sm">En curso</span>
        </div>
      </div>
    </div>
  </aside>

  <div class="app-main">
    <header class="topbar">
      <div class="topbar__title-group">
        <p class="breadcrumb">Administración / Usuarios</p>
        <h1 class="page-title">Usuarios</h1>
      </div>
      <div class="topbar__actions">
        <label class="searchbar">
          <svg class="icon" aria-hidden="true"><use href="icons.svg#search"></use></svg>
          <input aria-label="Buscar en UniCore" placeholder="Buscar en UniCore">
        </label>
        <button class="icon-btn" aria-label="Mensajes">
          <svg class="icon" aria-hidden="true"><use href="icons.svg#message-square"></use></svg>
          <span class="icon-btn__dot">3</span>
        </button>
        <span class="topbar__divider"></span>
        <button class="user-menu" aria-label="Cuenta de Ana Rodríguez">
          <span class="avatar">AR</span>
          <span class="user-menu__data">
            <span class="user-menu__name">Ana Rodríguez</span>
            <span class="user-menu__role">Administradora</span>
          </span>
          <svg class="icon" aria-hidden="true"><use href="icons.svg#chevron-down"></use></svg>
        </button>
      </div>
    </header>

    <header class="mobile-topbar">
      <div class="mobile-topbar__left">
        <button class="icon-btn" data-nav-toggle aria-label="Abrir menú">
          <svg class="icon" aria-hidden="true"><use href="icons.svg#menu"></use></svg>
        </button>
        <span class="mobile-topbar__title">Usuarios</span>
      </div>
    </header>

    <main class="content">
      <!-- page content -->
    </main>

    <nav class="bottom-nav" aria-label="Navegación móvil">
      <a class="bottom-nav__item" href="#" aria-current="page">
        <svg class="icon" aria-hidden="true"><use href="icons.svg#house"></use></svg>
        <span>Inicio</span>
      </a>
      <a class="bottom-nav__item" href="#">
        <svg class="icon" aria-hidden="true"><use href="icons.svg#users"></use></svg>
        <span>Usuarios</span>
      </a>
    </nav>
  </div>
</div>
```

`data-nav-toggle` is a JS hook. It should add `data-nav="open"` to `.app`; the drawer, backdrop, and scroll lock are handled by CSS. Use `.fab` for the mobile primary action; it sits above the bottom navigation.

### Layout and typography

- `.content` — page padding and vertical rhythm.
- `.stack` — vertical flex with `gap`.
- `.row` / `.row-between` — horizontal flex.
- `.cluster` — wrapping inline groups.
- `.grid-cards` — responsive card grid.
- `.spacer` — pushes siblings apart.
- `.page-title`, `.section-title`, `.card-title` — headings.
- `.text-body`, `.text-support`, `.text-muted`, `.kicker`, `.code` — text roles.

```html
<div class="row-between">
  <div class="stack" style="--stack-gap: 4px">
    <h2 class="section-title">Cursos del trimestre</h2>
    <p class="text-support">8 cursos · 184 estudiantes</p>
  </div>
  <div class="cluster">
    <button class="btn btn-secondary">Gestionar trimestres</button>
    <button class="btn btn-primary">Crear curso</button>
  </div>
</div>
```

Page-level tabs use `.page-tabs` and `.page-tab`:

```html
<nav class="page-tabs" aria-label="Cursos">
  <a class="page-tab is-active" href="#" aria-selected="true">Mis cursos <span class="badge badge-primary badge-sm">6</span></a>
  <a class="page-tab" href="#">Inscribirme <span class="badge badge-neutral badge-sm">4</span></a>
</nav>
```

### Buttons

```html
<button class="btn btn-primary">
  <svg class="icon" aria-hidden="true"><use href="icons.svg#plus"></use></svg>
  Crear usuario
</button>

<a class="btn btn-secondary" href="#">Cancelar</a>
<button class="btn btn-icon" aria-label="Buscar">…</button>

<button class="btn btn-primary" aria-busy="true">
  <span class="btn-spinner"></span>
  <span class="btn-label">Verificando…</span>
</button>
```

Available: `.btn-primary`, `.btn-secondary`, `.btn-ghost`, `.btn-danger`, `.btn-outline-success`, `.btn-sm`, `.btn-lg`, `.btn-icon`, `.btn-block`.

### Forms

```html
<label class="field">
  <span class="label">Usuario / Matrícula</span>
  <span class="input-group">
    <svg class="icon input-icon" aria-hidden="true"><use href="icons.svg#user"></use></svg>
    <input class="input" name="user" placeholder="Ej. 2026-0034" autocomplete="username">
  </span>
</label>

<label class="field">
  <span class="label">Contraseña</span>
  <span class="input-group input-group--action">
    <svg class="icon input-icon" aria-hidden="true"><use href="icons.svg#lock"></use></svg>
    <input class="input" type="password" aria-invalid="true" aria-describedby="pass-error">
    <button class="input-action" aria-label="Mostrar contraseña">…</button>
  </span>
  <small class="field-error" id="pass-error">Usuario o contraseña incorrectos</small>
</label>

<label class="check">
  <input type="checkbox">
  <span class="check__box"><svg class="icon" aria-hidden="true"><use href="icons.svg#check"></use></svg></span>
  Recordarme en este equipo
</label>

<label class="switch">
  <input type="checkbox" checked>
  <span class="switch__track"></span>
  <span class="toggle__label">Enviar credenciales por correo</span>
</label>
```

Other form classes: `.select`, `.textarea`, `.help`, `.toggle`, `.segmented`, `.segmented__item`.

### Badges, roles and chips

```html
<span class="badge badge-success">Activo</span>
<span class="badge badge-warning">Pendiente</span>
<span class="badge badge-primary">En curso</span>
<span class="badge role-facilitator">Facilitador</span>
<span class="badge role-admin">Administrador</span>

<button class="chip is-active"><span class="chip__dot"></span>2026-34</button>
<button class="chip">2026-35</button>
```

Trimestre selector strip:

```html
<div class="term-strip">
  <span class="term-strip__label">Trimestres</span>
  <span class="divider"></span>
  <button class="chip">2025-32</button>
  <button class="chip is-active"><span class="chip__dot"></span>2026-34</button>
</div>
```

Use `.badge-sm` inside cards and compact rows.

### Cards

```html
<article class="course-card">
  <div class="course-card__band">
    <div class="course-card__band-top">
      <span class="course-card__code">ISW-306</span>
      <span class="course-card__credits">4 créditos</span>
    </div>
    <span class="course-card__term">Trimestre 2026-34</span>
  </div>
  <div class="course-card__body">
    <h3 class="course-card__title">Desarrollo de Aplicaciones Web</h3>
    <div class="course-card__facilitator">
      <span class="avatar avatar-xs avatar-accent">LM</span>
      Laura Méndez
    </div>
    <div class="progress">
      <div class="progress__meta">
        <span class="progress__label">Progreso</span>
        <span class="progress__value">50% completado</span>
      </div>
      <div class="progress__track">
        <div class="progress__bar" style="--progress: 50%"></div>
      </div>
    </div>
    <div class="course-card__deadline">
      <svg class="icon" aria-hidden="true"><use href="icons.svg#clock"></use></svg>
      Entrega: 17 nov, 23:59
      <span class="badge badge-warning badge-sm">Pendiente</span>
    </div>
  </div>
</article>
```

The progress fill is data-driven; set `--progress` inline or from JS. For the navy pixel motif, add a `.pixel-field` with `.is-accent` cells inside `.course-card__band` or `.brand-panel`.

Use `.user-card` for mobile user lists:

```html
<article class="user-card">
  <div class="user-card__top">
    <span class="avatar avatar-lg avatar-accent">LM</span>
    <div class="user-card__data">
      <span class="user-card__name">Laura Méndez</span>
      <span class="user-card__meta">laura.mendez@uapa.edu.do</span>
    </div>
    <button class="table-actions" aria-label="Acciones de Laura Méndez">…</button>
  </div>
  <div class="user-card__badges">
    <span class="badge role-facilitator badge-sm">Facilitador</span>
    <span class="badge badge-success badge-sm">Activo</span>
    <span class="user-card__id">FAC-0142</span>
  </div>
</article>
```

Use `.course-row` for the enrollment list:

```html
<article class="course-row is-enrolled">
  <span class="course-row__code">MAT-201</span>
  <div class="course-row__info">
    <h3 class="course-row__title">Matemática Discreta</h3>
    <div class="course-row__meta">
      <span>José Ramírez</span>
      <span>35 cupos · 6 disponibles</span>
    </div>
  </div>
  <div class="course-row__action">
    <span class="btn btn-outline-success">Inscrito</span>
  </div>
</article>
```

### Data tables

```html
<div class="table-card">
  <div class="table-toolbar">
    <div class="tabs-inline" role="tablist">
      <button class="tab is-active" role="tab" aria-selected="true">Todos</button>
      <button class="tab" role="tab" aria-selected="false">Estudiantes</button>
    </div>
    <div class="table-toolbar__actions">
      <label class="searchbar">
        <svg class="icon" aria-hidden="true"><use href="icons.svg#search"></use></svg>
        <input aria-label="Buscar por nombre o matrícula" placeholder="Buscar por nombre o matrícula">
      </label>
      <button class="btn btn-primary">Crear usuario</button>
    </div>
  </div>

  <div class="selection-bar">
    <span class="selection-bar__count">2 usuarios seleccionados</span>
    <div class="selection-bar__actions">
      <button class="selection-action">Activar</button>
      <button class="selection-action">Exportar</button>
    </div>
  </div>

  <div class="table-scroll">
    <table class="data-table">
      <thead>
        <tr>
          <th class="cell-check"><span class="sr-only">Seleccionar</span></th>
          <th>Usuario</th>
          <th class="col-id">Matrícula / ID</th>
          <th class="col-role">Rol</th>
          <th class="col-status">Estado</th>
          <th class="col-date">Último acceso</th>
          <th class="col-actions"></th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="cell-check">
            <input class="row-select" type="checkbox" aria-label="Seleccionar Laura Méndez">
          </td>
          <td>
            <div class="table-user">
              <span class="avatar avatar-accent">LM</span>
              <span class="table-user__data">
                <span class="table-user__name">Laura Méndez</span>
                <span class="table-user__meta">laura.mendez@uapa.edu.do</span>
              </span>
            </div>
          </td>
          <td class="numeric">FAC-0142</td>
          <td><span class="badge role-facilitator badge-sm">Facilitador</span></td>
          <td><span class="badge badge-success badge-sm">Activo</span></td>
          <td class="text-support">Hoy, 08:42</td>
          <td class="cell-actions">
            <button class="table-actions" aria-label="Acciones de Laura Méndez">…</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="table-footer">
    <span>Mostrando 4 de 248</span>
    <a href="#">Cargar más</a>
  </div>
</div>
```

The selection bar appears automatically when a `.row-select` is checked. Use `.data-table--courses` for the taller course rows, with `.table-code`, `.table-stack`, `.table-person`, `.table-enrollment` and `.progress--sm` inside cells. Use `.user-card` lists on mobile.

### Overlays

```html
<dialog class="modal" id="create-user">
  <header class="modal__header">
    <div class="modal__heading">
      <h2 class="modal__title">Crear usuario</h2>
      <p class="modal__subtitle">La cuenta se crea con la matrícula institucional.</p>
    </div>
    <button class="modal__close" aria-label="Cerrar">…</button>
  </header>
  <div class="modal__body">…</div>
  <footer class="modal__footer">
    <button class="btn btn-secondary">Cancelar</button>
    <button class="btn btn-primary">Crear usuario</button>
  </footer>
</dialog>
```

```html
<dialog class="sheet">
  <header class="sheet__header"><button class="modal__close" aria-label="Cerrar">…</button><h2 class="sheet__title">Crear curso</h2></header>
  <div class="sheet__body">…</div>
  <footer class="sheet__footer"><button class="btn btn-primary btn-block">Crear curso</button></footer>
</dialog>
```

Use `dialog.showModal()` and `dialog.close()`. Use `.modal` on desktop and `.sheet` on mobile; add `.modal--lg` for 640px dialogs. If both exist in the DOM, add `.desktop-only` to the modal and `.mobile-only` to the sheet. Menus:

```html
<div class="menu-wrap">
  <button class="table-actions" aria-expanded="false" aria-controls="user-menu">…</button>
  <div class="menu" id="user-menu" data-state="closed">
    <button class="menu-item">Ver perfil</button>
    <div class="menu-divider"></div>
    <button class="menu-item menu-item--danger">Desactivar usuario</button>
  </div>
</div>
```

### Feedback and loading

```html
<div class="alert alert--danger">
  <svg class="icon" aria-hidden="true"><use href="icons.svg#circle-alert"></use></svg>
  Usuario o contraseña incorrectos
</div>

<div class="empty-state">
  <span class="empty-state__icon">…</span>
  <h3 class="empty-state__title">Aún no hay usuarios con estos filtros</h3>
  <p class="empty-state__text">Ajusta los filtros o crea un usuario nuevo.</p>
  <div class="empty-state__actions">
    <button class="btn btn-secondary">Limpiar filtros</button>
    <button class="btn btn-primary">Crear usuario</button>
  </div>
</div>

<div class="skeleton-row">
  <span class="skeleton skeleton-avatar"></span>
  <span class="skeleton-lines">
    <span class="skeleton skeleton-line"></span>
    <span class="skeleton skeleton-line skeleton-line--soft"></span>
  </span>
</div>
```

### Login

```html
<main class="login">
  <section class="login__form-panel">
    <a class="brand" href="#">…</a>
    <form class="login__form">
      <h1 class="login__title">Bienvenido a UniCore</h1>
      <p class="login__subtitle">Ingresa con tu matrícula o usuario institucional.</p>
      <div class="field">…</div>
      <button class="btn btn-primary btn-lg btn-block" type="submit">Iniciar sesión</button>
      <p class="text-center"><a class="link" href="#">¿Olvidaste tu usuario o contraseña?</a></p>
    </form>
    <p class="login__footer">© 2026 Universidad Abierta para Adultos</p>
  </section>
  <section class="brand-panel">
    <p class="brand-panel__eyebrow"><span class="brand-panel__dot"></span>Universidad Abierta para Adultos</p>
    <div class="brand-panel__message">
      <h2 class="brand-panel__title">Tu entorno virtual de aprendizaje</h2>
      <p class="brand-panel__text">Cursos, entregas, foros y calificaciones en un solo lugar.</p>
    </div>
  </section>
</main>
```

### State contract

| State | How to express it |
|---|---|
| Active navigation | `aria-current="page"` on `.nav-item` or `.bottom-nav__item` |
| Active tab | `aria-selected="true"` or `.is-active` |
| Mobile drawer | `data-nav="open"` on `.app` |
| Selected table rows | checked `.row-select`; selection bar appears automatically |
| Loading button | `aria-busy="true"` |
| Invalid field | `aria-invalid="true"` + `.field-error` |
| Open menu | `data-state="open"`; closed is `data-state="closed"` |
| Modal / sheet | `dialog.showModal()` and `dialog.close()` |
| Enrolled course | `.course-row.is-enrolled` |
| Pagination / load more | `.table-footer` text + link |

Use `.desktop-only` and `.mobile-only` to swap desktop tables for mobile card lists. Use `.btn-block-mobile` for full-width actions below 480px.

### Class quick reference

| Need | Classes |
|---|---|
| Shell | `.app`, `.sidebar`, `.app-main`, `.topbar`, `.mobile-topbar`, `.content`, `.bottom-nav` |
| Navigation | `.brand`, `.sidebar__brand`, `.sidebar__footer`, `.nav-group`, `.nav-label`, `.nav-item`, `.nav-item__count`, `.term-card`, `.help-link` |
| Typography | `.page-title`, `.section-title`, `.card-title`, `.text-body`, `.text-support`, `.kicker`, `.code` |
| Buttons | `.btn`, `.btn-primary`, `.btn-secondary`, `.btn-ghost`, `.btn-danger`, `.btn-sm`, `.btn-lg`, `.btn-icon` |
| Forms | `.field`, `.label`, `.input`, `.select`, `.textarea`, `.input-group`, `.check`, `.switch`, `.segmented` |
| Badges | `.badge`, `.badge-success`, `.badge-warning`, `.badge-danger`, `.badge-info`, `.role-admin`, `.role-facilitator`, `.role-student`, `.chip`, `.term-strip` |
| Cards | `.card`, `.course-card`, `.user-card`, `.course-row`, `.avatar`, `.progress` |
| Tables | `.table-card`, `.table-toolbar`, `.data-table`, `.table-user`, `.selection-bar`, `.table-footer` |
| Overlays | `.modal`, `.sheet`, `.menu`, `.menu-item` |
| Feedback | `.alert`, `.empty-state`, `.skeleton`, `.spinner` |
| Login | `.login`, `.login__form-panel`, `.login__form`, `.brand-panel` |

## 10. Design References

Use these products as inspiration, not as templates to copy:

- **UAPA:** [Official institutional identity](https://www.uapa.edu.do/nosotros/identidad-institucional/) — brand identity and visual consistency.
- **Canvas LMS:** [Student dashboard](https://community.canvaslms.com/) — course organization and academic workflows.
- **D2L Brightspace:** [Official website](https://www.d2l.com/brightspace/) — academic navigation and learning experience.
- **Penpot:** [Design and prototyping](https://penpot.app/) — interface design, reusable components, and prototypes.

**Final direction:** UniCore should look and feel like a modern evolution of UAPA's digital academic experience: recognizable institutional branding, intuitive navigation, clean academic dashboards, and a consistent responsive interface.
