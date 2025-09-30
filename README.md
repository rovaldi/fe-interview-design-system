# Frontend Interview - Design System

A modern, accessible tab component system built with React, TypeScript, and SCSS. This project demonstrates best practices in component design, testing, and developer experience.

## 🎨 Figma File

The figma file of the home test is available [here](https://www.figma.com/design/OclakAGLSXDoMKLFvwLNMP/%F0%9F%92%BB-Design-System-Home-Test---Tabs-Component?node-id=0-1&t=4pG7NN6HKxgxroDz-1).

## ✨ Features

- **🎯 Two Variants**: Pill and Underline styles
- **🏷️ Badge System**: Neutral, Positive, and Negative badge variants
- **♿ Accessible**: Full ARIA compliance
- **🎨 CSS Modules**: Scoped styling with SCSS and BEM methodology
- **📱 Responsive**: Works seamlessly across all device sizes
- **🔧 Type Safe**: Built with TypeScript for better developer experience
- **🧪 Well Tested**: Comprehensive test suite with 95%+ coverage
- **📚 Storybook**: Interactive component documentation
- **⚡ Modern Stack**: React, Vite, and modern tooling

## 🚀 Quick Start

### Prerequisites
- Node.js 20+ (LTS version recommended)
  - Using [nvm](https://github.com/nvm-sh/nvm) (recommended):
    ```bash
    # Install or switch to Node.js 20
    nvm install 20
    nvm use 20
    ```
  - Or download directly from [Node.js website](https://nodejs.org/)
- Corepack enabled (required for Yarn 3.8.5+)

### Installation

```bash
# If using nvm, ensure you're on Node.js 20
nvm use 20

# Enable corepack (if not already enabled)
corepack enable
corepack prepare yarn@3.8.5 --activate

# Verify versions
node --version  # Should show v20.x.x
yarn --version  # Should show 3.8.5 or higher

# Install dependencies
yarn install

# Start development server
yarn dev

# Open browser at http://localhost:5173
```

### Available Scripts

```bash
yarn dev          # Start development server
yarn build        # Build for production
yarn test         # Run test suite
yarn storybook    # Launch Storybook
yarn lint         # Run ESLint and Stylelint
yarn tsc          # Type check with TypeScript
```

## 🏗️ Architecture

### Component Structure

```
src/
├── components/
│   └── Tabs/
│       ├── Tabs.tsx                    # Main component
│       ├── Tabs.module.scss           # Styles
│       ├── Tabs.test.tsx              # Tests
│       ├── types.ts                   # TypeScript definitions
│       ├── components/
│       │   └── TabItem/               # Sub-component
│       ├── helpers/
│       │   └── getInitialActiveTab.ts # Utility functions
│       └── hooks/
│           └── useTabIndicator.ts     # Custom hooks
├── styles/
│   ├── tokens.css                     # Design tokens
│   ├── reset.css                      # CSS reset
│   └── index.css                      # Global styles
└── mockData.tsx                       # Demo data
```

### Key Design Decisions

#### 1. **Controlled vs Uncontrolled**
The component supports both patterns:
```tsx
// Uncontrolled (internal state management)
<Tabs tabs={tabs} defaultActiveTab="home" />

// Controlled (external state management)
<Tabs tabs={tabs} activeTab={activeTab} onChange={setActiveTab} />
```

#### 2. **CSS Modules with BEM**
- Scoped styling prevents conflicts
- BEM methodology for maintainable CSS
- SCSS for advanced features (nesting, variables)

#### 3. **TypeScript-First**
- Strong typing for all props and state
- IntelliSense support for better DX
- Runtime error prevention

#### 4. **Accessibility by Design**
- Full ARIA implementation
- Keyboard navigation (see [Future Improvements](#-future-improvements))
- Focus management with visual indicators

## 🧪 Testing Strategy

### Test Coverage
- **Unit Tests**: All utility functions and hooks
- **Component Tests**: Full component behavior and interactions
- **Integration Tests**: Complete user workflows
- **Accessibility Tests**: ARIA compliance

### Testing Philosophy
- Focus on **behavior over implementation**
- Use `data-testid` for reliable element selection
- Test user interactions, not internal state
- Comprehensive edge case coverage

### Run Tests
```bash
yarn test           # Run all tests
```

## 🎨 Styling System

### Design Tokens
```css
/* src/styles/tokens.css */
:root {
  /* Colors */
  --color-badge--neutral: #f1f1f7;
  --color-badge--positive: #b1ffc7;
  --color-badge--negative: #ffbfb1;
  --color-hover--underline: #c4c5cf;
  
  /* Spacing */
  --spacing-4xs: 0.2rem;
  --spacing-3xs: 0.4rem;
  --spacing-2xs: 0.8rem;
  --spacing-xs: 1.2rem;
  
  /* Typography */
  --font-size--12: 1.2rem;
  --font-size--14: 1.4rem;
}
```

### Component Styling
- **CSS Modules**: Scoped component styles
- **SCSS**: Advanced CSS features (nesting, variables)
- **BEM**: Block Element Modifier methodology
- **Responsive**: Mobile-first approach with breakpoints

## ♿ Accessibility

### Features Implemented
- **ARIA Roles**: `tablist`, `tab`, `tabpanel`
- **ARIA States**: `aria-selected`, `aria-disabled`, `aria-controls`
- **Labels**: Descriptive `aria-label` attributes
- **Focus Management**: Visual focus indicators with `:focus` pseudo-selector

### Focus Styling Note
Currently using `:focus` pseudo-selector for focus indicators to ensure visibility during review. In a production environment with full keyboard navigation, I would switch to `:focus-visible` for better UX (only shows focus ring when navigating with keyboard, not mouse clicks).

## 🔧 Future Improvements

### Keyboard Navigation
For enhanced accessibility, I would implement comprehensive keyboard support, however, I kept the implementation focused on the core tab functionality to demonstrate design system principles without overcomplicating the solution.

I would consider using libraries like **Radix UI**:

- **Radix UI Tabs**: Provides unstyled, accessible tab components
- **Headless Approach**: Full control over styling while maintaining accessibility
- **Keyboard Navigation**: Built-in keyboard support and focus management
- **ARIA Compliance**: Automatically handles all accessibility requirements

I chose not to use Radix UI for this project to showcase the ability to build accessible components from scratch and focus on the design system implementation.

## 🛠️ Development Tools

### Code Quality
- **ESLint**: JavaScript/TypeScript linting
- **Prettier**: Code formatting
- **Stylelint**: SCSS/CSS linting with BEM pattern support
- **TypeScript**: Type checking and IntelliSense

### Build & Development
- **Vite**: Fast development server and build tool
- **Vitest**: Unit testing framework
- **Storybook**: Component documentation and testing
- **Yarn**: Package management with workspaces support

### Browser Support
- **Modern Browsers**: Chrome, Firefox, Safari, Edge (latest 2 versions)
- **Mobile First**: Responsive design for all screen sizes

## 📚 Documentation

- **Storybook**: Interactive component playground at `http://localhost:6006`
- **Type Definitions**: Full TypeScript support
- **Code Comments**: Inline documentation for complex logic

## 📄 License

This project is part of a frontend interview process and is intended for evaluation purposes.