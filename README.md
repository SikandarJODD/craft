# Svelte Craft Design System

Svelte Craft is a lightweight, flexible design system for building responsive layouts in Svelte and handling prose. It provides a set of foundational components that make it easy to create consistent, maintainable layouts while leveraging the power of Tailwind CSS.

## Credits

This is a Svelte port of **[Craft](https://github.com/brijr/craft)**, originally created by [Bridger Tower](https://github.com/brijr).
The original project was built using Next.js and Tailwind CSS, and I have ported it to Svelte while preserving its core design and functionality.

All credit for the original idea, design, and implementation goes to **Bridger Tower**.
This port is simply an adaptation for the Svelte ecosystem.

## Features

- **Modern Styling**: Built with Tailwind CSS and compatible with shadcn-svelte
- **Responsive Design**: First-class support for responsive layouts
- **Type-Safe**: Written in TypeScript with strong type inference
- **Performance**: Zero runtime overhead, all styles are compiled
- **Accessible**: Built with WCAG guidelines in mind
- **Lightweight**: No external dependencies beyond Tailwind CSS

## Requirements

- Sveltekit
- shadcn-svelte (for the color system)
- Tailwind CSS
- TypeScript (recommended)

## Quick Start

```bash
npx jsrepo add --repo github/sikandarjodd/craft
```

The installer will:

1. Install and configure required packages - tailiwnd-merge and clsx
2. Set up the Craft component in your project
3. Add <code>Layout, Prose, Container, Section</code> Components in you project

## Usage

### Example 1

```svelte
<script>
  import { Prose } from "$lib/components/blocks/craft";
  import { marked } from "marked";
  let readme = `
  # Learn Sveltekit Blog
  web development for the rest of us
  `;
</script>

<Prose>
  {@html marked(readme)}
</Prose>
```

### Example 2

```svelte
<script>
  import { Prose } from "$lib/components/blocks/craft";
</script>

<Prose>
  <h1>Learn Sveltekit</h1>
  <p>web development for the rest of us</p>
</Prose>

```

### Example 3

```svelte
<script>
  import { Container, Section } from "$lib/components/blocks/craft";

  // Container : Centers content and provides consistent horizontal padding.
  // Section : A semantic section container for grouping related content.
</script>

<Container>
  <Section>
    <h1>Usage</h1>
    <p>
      This is a simple example of how to use the <code>Container</code> and
      <code>Section</code> components.
    </p>
  </Section>
</Container>

```

## Core Components

### Layout

The root component that provides base styling and structure.

```svelte
<Layout>
  <!--  Your page content -->
</Layout>
```

### Main

The primary content area of your page. Applies typography styles without header spacing.

```svelte
<Main>
  <h1>Welcome</h1>
  <p>This content will have typography styles applied.</p>
</Main>
```

### Section

A semantic section container for grouping related content.

```svelte
<Section>
  <h2>Features</h2>
  <!-- Section content -->
</Section>
```

### Container

Centers content and provides consistent horizontal padding.

```svelte
<Container>
  <!-- Centered content with padding -->
</Container>
```

### Article

Applies typography and spacing styles (including header spacing), ideal for long-form content.

```svelte
<Article>
  <h1>Article Title</h1>
  <p>Article content with proper typography and spacing.</p>
</Article>
```

### Prose

Similar to Article but without max-width constraints and header spacing. Perfect for rich text content.

```svelte
<Prose>
  <!-- Rich text content -->
</Prose>
```

#### Grid Layout Example:

```svelte
<!-- Not Responsive -->
<Box cols={3} gap={4}>
  <div>Grid Item 1</div>
  <div>Grid Item 2</div>
  <div>Grid Item 3</div>
</Box>
```

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

```svelte
<Container class="bg-gray-100 dark:bg-gray-900">
  <Section class="py-12">
    <h1>Custom Styled Section</h1>
  </Section>
</Container>
```

## Best Practices

### Layout Structure

```svelte
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
```

### Content Structure

```svelte
<Article>
  <h1>Article Title</h1>
  <p>Introduction paragraph...</p>

  <h2>Section Title</h2>
  <p>Section content...</p>

  <Box cols={3} gap={4}>
    <!-- Grid content  -->
  </Box>
</Article>
```

## License

Published under the [MIT](https://github.com/SikandarJODD/craft/blob/master/LICENSE) license.
