<script lang="ts">
  import { styles, type BaseProps } from "./craft";

  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<section {id} class={[styles.layout.section, _class]} {style}>
  {@render children?.()}
</section>
