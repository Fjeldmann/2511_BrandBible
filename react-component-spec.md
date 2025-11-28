Below is a **clean, implementation-ready UI Component Library Spec** based fully on the styleguide and brand bible.
It’s written so developers can immediately build a design system (e.g., Tailwind, React components, or Figma tokens).

---

# Fjeldmann UI Component Library Specification

This spec defines **foundations**, **components**, **states**, and **interaction rules** for Fjeldmann’s web interfaces.
Everything reflects Fjeldmann’s visual identity: **human, clear, constructive, calm**.

---

# 1. Foundations

## 1.1 Typography Tokens

### Font Families

```
--font-primary: "Inter", sans-serif;
--font-secondary: "Montserrat", sans-serif;
```

### Type Scale (Web)

| Token | Font       | Weight | Size       | Line Height |
| ----- | ---------- | ------ | ---------- | ----------- |
| h1    | Inter      | 700    | 4rem       | 1.1         |
| h2    | Inter      | 700    | 3rem       | 1.15        |
| h3    | Inter      | 700    | 2.25rem    | 1.2         |
| h4    | Inter      | 700    | 1.75rem    | 1.25        |
| h5    | Inter      | 700    | 1.25rem    | 1.3         |
| h6    | Inter      | 700    | 1rem       | 1.35        |
| body  | Inter      | 400    | 1rem       | 1.5         |
| small | Inter      | 400    | 0.875rem   | 1.4         |
| label | Montserrat | 700    | 0.875–1rem | 1.1         |

* Label + Button text: **uppercase + 10–20% tracking**

---

## 1.2 Colour Tokens

### Neutral Palette

```
--black-ink: #222222;
--dark-gray: #6D6D6D;
--mid-gray: #D5D5D5;
--light-gray: #F8F8F8;
--white-snow: #FFFFFF;
```

### Accent Palette

```
--amber: #DC851F;      /* Primary accent */
--warm-sand: #E0BB89;  /* Soft backgrounds */
--blue-fir: #025951;   /* Secondary accent */
```

### Semantic Derived Tokens

```
--text-primary: var(--black-ink);
--text-secondary: var(--dark-gray);
--surface-default: var(--white-snow);
--surface-alt: var(--light-gray);
--border-default: var(--mid-gray);
--accent-primary: var(--amber);
--accent-secondary: var(--blue-fir);
```

---

## 1.3 Spacing & Layout Tokens

```
--radius-sm: 6px;
--radius-md: 10px;
--radius-lg: 16px;
--radius-pill: 999px;

--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 24px;
--space-6: 32px;

--container-max: 1200px;
--container-padding: 24px;
```

---

## 1.4 Iconography

* **Google Material Symbols — Outlined**
* Consistent stroke, geometric, minimal
* Default size: 24px
* Use 32–48px only in hero sections or high-impact components

---

# 2. Components

Below are production-grade requirements for the main UI components.

---

# 2.1 Buttons

## Primary Button

**Use:** main CTA actions (“Kontakt os”, “Prøv nu”)
**Style:** warm, confident, high contrast, but not aggressive

**Properties:**

```
font-family: Montserrat;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.05–0.1em;
background: var(--accent-primary);
color: var(--white-snow);
padding: 12px 24px;
border-radius: var(--radius-md);
border: none;
```

### Hover

```
background: #c6761b; /* Slightly darker amber */
```

### Active

```
background: #a76215;
transform: scale(0.98);
```

### Disabled

```
background: var(--mid-gray);
color: var(--white-snow);
opacity: 0.6;
cursor: not-allowed;
```

---

## 2.2 Secondary Button

**Use:** supporting actions

```
background: var(--light-gray);
color: var(--black-ink);
border: 2px solid var(--mid-gray);
font-family: Montserrat;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.05–0.1em;
padding: 12px 24px;
border-radius: var(--radius-md);
```

Hover:

```
background: var(--mid-gray);
```

---

## 2.3 Text Input

**Visual tone:** calm, clear, spacious, approachable.

```
background: var(--white-snow);
border: 1px solid var(--mid-gray);
padding: 12px 16px;
font-family: Inter;
font-size: 1rem;
border-radius: var(--radius-md);
color: var(--text-primary);
```

### Focus

```
border-color: var(--accent-primary);
outline: none;
box-shadow: 0 0 0 3px rgba(220,133,31,0.2);
```

### Error State

```
border-color: #cc3d3d;
```

Helper text:

```
font-size: 0.875rem;
color: #cc3d3d;
```

---

## 2.4 Textarea

Same as input, but:

```
min-height: 140px;
resize: vertical;
line-height: 1.5;
```

---

## 2.5 Navigation Bar

### Layout

* Height: 72px
* Logo left, items right
* Ample whitespace
* Background: `--white-snow`

### Link Style

```
font-family: Inter;
font-weight: 500;
color: var(--text-primary);
padding: 8px 16px;
border-radius: var(--radius-sm);
```

Hover:

```
background: var(--light-gray);
```

Active:

```
color: var(--accent-primary);
```

Mobile:

* Hamburger using Material Symbols
* Fullscreen or slide-down menu
* Minimum 48px tap targets

---

## 2.6 Cards

### Purpose

Use for feature explanations, product previews, service blocks.

### Style

```
background: var(--surface-alt);
border-radius: var(--radius-lg);
padding: var(--space-5);
box-shadow: 0 2px 6px rgba(0,0,0,0.06);
display: flex;
flex-direction: column;
gap: var(--space-3);
```

### Variants

1. **Media Card** (image top → title → text)
2. **Icon Card** (icon in circle)

---

## 2.7 CTA Section (Hero Callouts)

Fjeldmann’s identity is **human × tech × nature**, so hero CTAs often require contrast.

### Background Options:

* Deep nature photography with blurred background
* Light neutral surface
* 50% white overlay if logo is used

### Title style:

```
font-family: Inter;
font-size: 3rem;
font-weight: 700;
```

### Buttons:

Primary + Secondary

---

## 2.8 Badges / Labels

Used for category tags, status labels.

```
font-family: Montserrat;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.1em;
background: var(--light-gray);
color: var(--black-ink);
padding: 4px 8px;
border-radius: var(--radius-sm);
```

---

## 2.9 Modal

```
background: var(--white-snow);
padding: var(--space-5);
border-radius: var(--radius-lg);
max-width: 520px;
box-shadow: 0 6px 20px rgba(0,0,0,0.15);
```

### Backdrop

```
background: rgba(0,0,0,0.4);
```

---

## 2.10 Accordion

```
background: var(--light-gray);
border: 1px solid var(--mid-gray);
border-radius: var(--radius-md);
padding: var(--space-4);
```

Header:

```
display: flex;
justify-content: space-between;
font-weight: 600;
cursor: pointer;
```

Open state:

```
background: var(--white-snow);
```

---

## 2.11 Tabs

```
display: flex;
gap: var(--space-3);
border-bottom: 1px solid var(--mid-gray);
```

Tab:

```
padding: 8px 12px;
font-family: Inter;
font-weight: 600;
color: var(--text-secondary);
border-radius: var(--radius-sm);
```

Active:

```
color: var(--text-primary);
border-bottom: 2px solid var(--accent-primary);
```

---

# 3. Interactions

## Animation Guidelines

* Soft, natural, constructive
* Avoid gimmicky or bouncy effects
* Use:

  * fade
  * gentle slide
  * 100–200ms transitions

## Focus States

All interactive elements must have:

```
outline: none;
box-shadow: 0 0 0 3px rgba(220,133,31,0.3);
```

## Hover States

* Increase clarity, not noise
* Prefer slight shadow or colour shift (no large animations)

---

# 4. Responsive Guidelines

### Breakpoints

```
sm: 480px
md: 768px
lg: 1024px
xl: 1280px
```

### Rules

* Type scales down 10–20% under `md`
* Navigation collapses at `md`
* Cards become single-column below `md`
* Images crop to maintain simplicity

---

# 5. Optional: Tailwind Config (If you want it)

I can generate a full Tailwind preset with:
✔ colours
✔ typography
✔ spacing
✔ component classes
✔ custom utilities

Just say: **“Generate the Tailwind config”**.

---