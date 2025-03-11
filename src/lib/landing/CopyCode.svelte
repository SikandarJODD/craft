<script lang="ts">
  import Button from "$lib/components/ui/button/button.svelte";
  import {
    Tooltip,
    TooltipContent,
    TooltipProvider,
    TooltipTrigger,
  } from "$lib/components/ui/tooltip/index.js";
  import { cn } from "$lib/utils.js";
  import { toast } from "svelte-sonner";
  let { text = "npx jsrepo add --repo github/sikandarjodd/craft" } = $props();
  let copied = $state(false);

  function handleCopy() {
    copied = true;
    navigator.clipboard.writeText(text);
    toast.success("Copied to clipboard");
    setTimeout(() => (copied = false), 1500);
  }
</script>

<button
  class="group py-2 pl-2 pr-4 font-mono bg-accent/50 hover:bg-accent/100 border mt-6 flex gap-4 items-center"
  onclick={handleCopy}
>
  {text}
  {@render copy()}
</button>

{#snippet copy()}
  <TooltipProvider>
    <Tooltip>
      <TooltipTrigger
        class="disabled:opacity-100"
        aria-label={copied ? "Copied" : "Copy component source"}
        disabled={copied}
      >
        {#snippet child({ props })}
          <Button variant='secondary' size="icon" {...props}>
            <div
              class={cn(
                "transition-all",
                copied ? "scale-100 opacity-100" : "scale-0 opacity-0"
              )}
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="none"
                aria-hidden="true"
              >
                <path
                  fill="#10B981"
                  d="M14.548 3.488a.75.75 0 0 1-.036 1.06l-8.572 8a.75.75 0 0 1-1.023 0l-3.429-3.2a.75.75 0 0 1 1.024-1.096l2.917 2.722 8.06-7.522a.75.75 0 0 1 1.06.036Z"
                />
              </svg>
            </div>
            <div
              class={cn(
                "absolute transition-all",
                copied ? "scale-0 opacity-0" : "scale-100 opacity-100"
              )}
            >
              <svg
                class="fill-current"
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="none"
                aria-hidden="true"
              >
                <path
                  d="M3 2.5h7a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-.5.5H3a.5.5 0 0 1-.5-.5V3a.5.5 0 0 1 .5-.5ZM10 1H3a2 2 0 0 0-2 2v7a2 2 0 0 0 2 2h7a2 2 0 0 0 2-2V3a2 2 0 0 0-2-2Zm3 5.5h1a.5.5 0 0 1 .5.5v7a.5.5 0 0 1-.5.5H7a.5.5 0 0 1-.5-.5v-1H5v1a2 2 0 0 0 2 2h7a2 2 0 0 0 2-2V7a2 2 0 0 0-2-2h-1v1.5Z"
                />
              </svg>
            </div>
          </Button>
        {/snippet}
      </TooltipTrigger>
      <TooltipContent
        class="border border-input bg-popover px-2 py-1 text-xs text-muted-foreground"
      >
        Click to copy
      </TooltipContent>
    </Tooltip>
  </TooltipProvider>
{/snippet}
