<script lang="ts">
  import { isAnExternalLink } from "../../utils/helpers";

  import type { ContactAction } from "../../types/contact-action.type";

  export let width: string = "";
  let clazz = "";
  export { clazz as class };
  export let btnClass: "btn-primary" | "btn-cta" = "btn-primary";
  export let action: ContactAction;
  export let isTextSmall: boolean = false;
  const { icon, title, text, link } = action;
  const target = isAnExternalLink(link.href) ? "_blank" : undefined;
</script>

<div
  class="flex flex-col justify-between items-center bg-off-white rounded-4xl px-xx-small py-xx-small md:py-small mb-micro md:mb-small shadow-normal {clazz}"
  style="width: {width}"
>
  <div>
    {#if icon}
      <img src="/svg/contact/{icon}" alt={title} class="mx-auto h-28" />
    {/if}
    <h2 class="h4">{title}</h2>
    <p class="mt-micro mb-x-small" class:text-small={isTextSmall}>{text}</p>
  </div>
  <a href={link.href} {target} class={btnClass}>{link.text}</a>
</div>
