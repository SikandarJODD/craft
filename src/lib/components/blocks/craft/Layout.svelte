<script lang="ts">
  import {
    all_layout_style,
    articleTypographyStyles,
    type BaseProps,
  } from "./craft";

  let { children }: BaseProps = $props();
</script>

<div class={[all_layout_style, articleTypographyStyles]}>
  {@render children?.()}
</div>
