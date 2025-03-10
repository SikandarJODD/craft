<script lang="ts">
  import { baseTypographyStyles, type BaseProps } from "./craft";

  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<div {id} class={[baseTypographyStyles, _class]} {style}>
  {@render children?.()}
</div>
