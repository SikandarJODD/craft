<script>
  import { Article, Container, Section } from "$lib/components/blocks/craft";
  import Demo from "$lib/landing/Demo.svelte";
  import Img from "$lib/images/img.png";
  import { marked } from "marked";
  let code = `
  \`\`\`bash
  npx sv create folder_name
cd folder_name
npm run dev
  \`\`\`
  `;
  let pagesveltecode =
    `\`\`\`bash
<` +
    `script lang="ts">
  let count = $state(0); // Svelte 5 rune for reactive state

  function increment() {
    count += 1;
  }
<` +
    `/script>

<h1>Welcome to SvelteKit</h1>
<p>Count: {count}</p>
<button on:click={increment}>Click Me!</button>

<` +
    `style>
  h1 { color: #ff3e00; }
  button {
    padding: 0.5rem 1rem;
    background: #ff3e00;
    color: white;
    border: none;
  }
</` +
    `style>
\`\`\``;

  let projects = [
    {
      name: "Shadcn-Svelte",
      url: "https://next.shadcn-svelte.com",
      img: "https://github.com/huntabyte/shadcn-svelte/blob/main/sites/docs/static/og.png?raw=true",
    },
    {
      name: "Runed",
      url: "https://runed.dev/docs",
      img: "https://github.com/svecosystem/runed/blob/main/sites/docs/static/og.png?raw=true",
    },
    {
      name: "Formsnap",
      url: "https://formsnap.dev/docs",
      img: "https://github.com/svecosystem/formsnap/blob/main/docs/static/og.png?raw=true",
    },
  ];
</script>

<Section>
  <Container>
    <div class="grid border">
      <Demo attribute="Example Blog" vertical>
        <Article class="min-w-full">
          <h2>Sveltekit Blog</h2>
          <blockquote>
            Frameworks are not tools for organizing your code, they are tools
            for organizing your mind.
            <cite>- Rich Harris</cite>
          </blockquote>
          <p class="text-muted-foreground">
            SvelteKit is a framework for rapidly developing robust, performant
            web applications using Svelte. If you’re coming from React,
            SvelteKit is similar to Next. If you’re coming from Vue, SvelteKit
            is similar to Nuxt.
          </p>
          <figure>
            <img src={Img} alt="Sveltekit Website" />
            <figcaption>sveltekit website image</figcaption>
          </figure>

          <h2>Features</h2>
          <ol>
            <li>
              <strong>File-Based Routing:</strong> Drop a file in
              <code>src/routes/</code>
              (e.g., <code>+page.svelte</code>), and boom—you've got a route. No
              config headaches.
            </li>
            <li>
              <strong>Server-Side Rendering (SSR):</strong>
              Renders pages on the server to enhance performance and SEO, delivering
              faster initial page loads.
            </li>
            <li>
              <strong>Static Site Generation (SSG):</strong>
              Supports prerendering of pages at build time, enabling the creation
              of static sites for improved performance and scalability.
            </li>
            <li>
              <strong>Adaptable Rendering:</strong>
              Allows configurable rendering strategies, including SSR, CSR, and SSG,
              to suit various project requirements.
            </li>
            <li>
              <strong>Built-in Adapters:</strong>
              <p>
                Facilitates deployment on platforms like Netlify, Vercel, and
                Cloudflare Pages.
              </p>
            </li>
          </ol>

          <h3>Getting Started</h3>
          <p>To create a new SvelteKit project, run the following command:</p>
          {@html marked(code)}
          <p>
            Open <code>src/routes/+page.svelte</code> and replace its contents with
            this:
          </p>
          {@html marked(pagesveltecode)}

          <h3>Useful Projects</h3>
          <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
            {#each projects as project}
              <div class="border rounded-lg px-4">
                <a href={project.url} target="_blank" class="!no-underline">
                  <figure>
                    <img
                      class="h-fit w-full object-cover object-center"
                      src={project.img}
                      alt={project.name}
                    />
                    <figcaption>{project.name}</figcaption>
                  </figure>
                </a>
              </div>
            {/each}
          </div>
        </Article>
      </Demo>
    </div>
  </Container>
</Section>
