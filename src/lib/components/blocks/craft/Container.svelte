<script lang="ts">
	import { cn } from './craft.ts';
  import { styles, type BaseProps } from "./craft";

  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<div {id} class={cn(styles.layout.container, _class)} {style}>
  {@render children?.()}
</div>
