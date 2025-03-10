<script lang="ts">
  import { baseTypographyStyles, styles, type BaseProps } from "./craft";

  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<div {id} class={[baseTypographyStyles, styles.layout.spacing, _class]} {style}>
  {@render children?.()}
</div>
