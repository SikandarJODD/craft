<script lang="ts">
  import { cn } from "$lib/utils";
  import { getResponsiveClass, styles, type BoxProps } from "./craft";

  let {
    children,
    id,
    style,
    class: _class,
    direction = "row",
    wrap = "nowrap",
    gap = 0,
    cols,
    rows,
  }: BoxProps = $props();

  const directionClasses = {
    row: "flex-row",
    col: "flex-col",
  };

  const wrapClasses = {
    wrap: "flex-wrap",
    nowrap: "flex-nowrap",
  };

  const gapClasses = {
    0: "gap-0",
    1: "gap-1",
    2: "gap-2",
    3: "gap-3",
    4: "gap-4",
    5: "gap-5",
    6: "gap-6",
    8: "gap-8",
    10: "gap-10",
    12: "gap-12",
  };

  const colsClasses = {
    1: "grid-cols-1",
    2: "grid-cols-2",
    3: "grid-cols-3",
    4: "grid-cols-4",
    5: "grid-cols-5",
    6: "grid-cols-6",
    7: "grid-cols-7",
    8: "grid-cols-8",
    9: "grid-cols-9",
    10: "grid-cols-10",
    11: "grid-cols-11",
    12: "grid-cols-12",
  };
</script>

<div
  class={cn([
    cols || rows ? "grid" : "flex",
    cols && getResponsiveClass(cols, colsClasses),
    rows && getResponsiveClass(rows, colsClasses),
    getResponsiveClass(direction, directionClasses),
    getResponsiveClass(wrap, wrapClasses),
    getResponsiveClass(gap, gapClasses),
    _class,
  ])}
  {id}
  {style}
>
  {@render children?.()}
</div>
