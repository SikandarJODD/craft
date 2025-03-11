<script>
  import Container from "$lib/components/blocks/craft/Container.svelte";
  import Prose from "$lib/components/blocks/craft/Prose.svelte";
  import Section from "$lib/components/blocks/craft/Section.svelte";
  import Demo from "$lib/landing/Demo.svelte";
  import { marked } from "marked";

  let markdown = `
  # Learn SvelteKit Routing with Various Examples

<div>
    <img src="https://github.com/sveltejs/svelte/blob/main/assets/banner.png?raw=true">
</div>

SvelteKit, the official framework for building Svelte applications, offers a powerful and intuitive routing system. In this comprehensive guide, we'll explore SvelteKit routing with detailed examples to help you master navigation in your SvelteKit projects.


### Basic File-based Routing

SvelteKit uses a file-based routing system where the structure of your \`src/routes\` directory defines your application's routes.

### Basic Routes
\`\`\`
src/routes/
└── +page.svelte
\`\`\`
### Nested Routes
\`\`\`
src/routes/
├── dashboard/
│   ├── +page.svelte
│   └── +page.server.ts
└── +page.svelte
\`\`\`

### Dynamic Routes

\`\`\`
src/routes/
├── blog/
│   ├── [slug]/
│   │   ├── +page.js
│   │   └── +page.svelte
│   ├── category/
│   │   └── [[tag]]/
│   │       └── +page.svelte
│   └── +page.svelte
└── +page.svelte
\`\`\`

## Key takeaways:

- Use file structure for routes
- <code>[param]</code> for dynamic segments
- <code>[[param]]</code> for optional parameters
- <code>[...param]</code> for rest parameters
- <code>+page.js</code> for data loading
- <code>+page.server.ts</code> for loading server-side data
- <code>src/routes/index.svelte</code> for the root route
`;
</script>

<Container>
  <div class="grid border">
    <Demo attribute="markdown" vertical>
      <Prose>
        {@html marked(markdown)}
      </Prose>
    </Demo>
  </div>
</Container>
