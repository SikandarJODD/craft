<script lang="ts">
  import type { Snippet } from "svelte";

  let {
    children,
    attribute,
    vertical,
    class: _class = "",
  }: {
    children: Snippet;
    attribute: string;
    vertical?: boolean;
    class?: string;
  } = $props();
</script>

<section
  class={["grid", vertical ? "divide-y" : "sm:divide-x sm:grid-cols-[8rem_3fr]", _class]}
>
  <div class="p-2 sm:p-4 bg-accent/50 border-b sm:border-b-0">
    <p class="sr-only">HTML Attribute</p>
    <p class="text-sm!">{attribute}</p>
  </div>

  <div class="p-6 relative bg-background">
    <p
      class="text-muted-foreground hidden sm:block text-xs! absolute top-2 right-2"
    >
      Preview
    </p>
    {@render children()}
  </div>
</section>
