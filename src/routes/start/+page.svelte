<script lang="ts">
  import { Section, Container, Prose } from "$lib/components/blocks/craft";
  let readMe = `
# Svelte Craft Design System

Svelte Craft is a lightweight, flexible design system for building responsive layouts in Svelte and handling prose. It provides a set of foundational components that make it easy to create consistent, maintainable layouts while leveraging the power of Tailwind CSS.

## Features

- **Modern Styling**: Built with Tailwind CSS and compatible with shadcn-svelte
- **Responsive Design**: First-class support for responsive layouts
- **Type-Safe**: Written in TypeScript with strong type inference
- **Performance**: Zero runtime overhead, all styles are compiled
- **Accessible**: Built with WCAG guidelines in mind
- **Lightweight**: No external dependencies beyond Tailwind CSS

## Requirements

- Sveltekit or higher (recommended 20+)
- Shadcn-svelte (for the color system)
- Tailwind CSS
- TypeScript (recommended)

## Quick Start

\`\`\`bash
# Using npm
npx jsrepo add --repo github/sikandarjodd/craft

# Using pnpm (recommended)
pnpx jsrepo add --repo github/sikandarjodd/craft

# Using yarn
yarn npx jsrepo add --repo github/sikandarjodd/craft
\`\`\`

The installer will:

1. Check your environment and dependencies
2. Install and configure required packages
3. Set up the Craft component in your project

## Core Components

### Layout

The root component that provides base styling and structure.

\`\`\`svelte
<Layout>
  <!--  Your page content -->
</Layout>
\`\`\`

### Main

The primary content area of your page. Applies typography styles without header spacing.

\`\`\`svelte
<Main>
  <h1>Welcome</h1>
  <p>This content will have typography styles applied.</p>
</Main>
\`\`\`

### Section

A semantic section container for grouping related content.

\`\`\`svelte
<Section>
  <h2>Features</h2>
  <!-- Section content -->
</Section>
\`\`\`

### Container

Centers content and provides consistent horizontal padding.

\`\`\`svelte
<Container>
  <!-- Centered content with padding -->
</Container>
\`\`\`

### Article

Applies typography and spacing styles (including header spacing), ideal for long-form content.

\`\`\`svelte
<Article>
  <h1>Article Title</h1>
  <p>Article content with proper typography and spacing.</p>
</Article>
\`\`\`

### Prose

Similar to Article but without max-width constraints and header spacing. Perfect for rich text content.

\`\`\`svelte
<Prose>
  <!-- Rich text content -->
</Prose>
\`\`\`


#### Type-Safe Props

\`\`\`typescript
interface BoxProps {
  direction?: ResponsiveValue<"row" | "col">;
  wrap?: ResponsiveValue<"wrap" | "nowrap">;
  gap?: ResponsiveValue<0 | 1 | 2 | 3 | 4 | 5 | 6 | 8 | 10 | 12>;
  cols?: ResponsiveValue<1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12>;
  rows?: ResponsiveValue<1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12>;
}
\`\`\`


## Typography System

Svelte Craft provides a comprehensive typography system that handles:

- Headings (h1-h6) with proper sizing and spacing
- Paragraphs with comfortable line height
- Lists (ordered, unordered, and nested)
- Code blocks and inline code
- Tables with proper borders and spacing
- Block quotes and citations
- Figures and captions
- And more...

### Typography Components

Choose the right typography component for your needs:

- **Article**: Full typography with header spacing
- **Prose**: Typography without header spacing
- **Main**: Basic typography without header spacing

## Customization

### Tailwind Configuration

Craft works seamlessly with your Tailwind configuration. You can customize:

- Colors through your color palette
- Spacing through your spacing scale
- Typography through your font settings
- Breakpoints through your screen configurations

### Component Styling

All components accept a \`class\` prop for custom styling:

\`\`\`svelte
<Container class="bg-gray-100 dark:bg-gray-900">
  <Section class="py-12">
    <h1>Custom Styled Section</h1>
  </Section>
</Container>
\`\`\`

## Best Practices

### Layout Structure

\`\`\`svelte
<Layout>
  <Main>
    <Section>
      <Container>
        <h1>Page Title</h1>
        <Box cols={2} gap={6}>
         <!-- Content -->
        </Box>
      </Container>
    </Section>
  </Main>
</Layout>
\`\`\`

### Content Structure

\`\`\`svelte
<Article>
  <h1>Article Title</h1>
  <p>Introduction paragraph...</p>

  <h2>Section Title</h2>
  <p>Section content...</p>

  <Box cols={3} gap={4}>
    <!-- Grid content  -->
  </Box>
</Article>
\`\`\`
`;
  import { marked } from "marked";
</script>

<Section>
  <Container>
    <Prose>{@html marked(readMe)}</Prose>
  </Container>
</Section>
