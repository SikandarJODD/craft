<script lang="ts">
  import { articleTypographyStyles, styles, type BaseProps } from "./craft";

  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<article
  {id}
  class={[
    articleTypographyStyles,
    styles.layout.spacing,
    styles.layout.article,
    _class,
  ]}
  {style}
>
  {@render children?.()}
</article>
