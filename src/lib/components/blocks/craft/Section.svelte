<script lang="ts">
	import { cn } from './craft.ts';
  import { styles, type BaseProps } from "./craft";
  let { children, id, style, class: _class }: BaseProps = $props();
</script>

<section {id} class={cn(styles.layout.section, _class)} {style}>
  {@render children?.()}
</section>
