<script lang="ts">
  import { styles, type BaseProps } from "./craft";

  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<div {id} class={[styles.layout.container, _class]} {style}>
  {@render children?.()}
</div>
