<script>
  import { reportAction, thanksAction } from "../../contents/security";
  import Section from "../section.svelte";
  import Action from "./action.svelte";
</script>

<Section>
  <div
    class="flex flex-col md:flex-row items-center md:items-start justify-between max-w-3xl mx-auto space-y-medium md:space-y-0"
  >
    {#each [thanksAction, reportAction] as action}
      <Action {action} />
    {/each}
  </div>
</Section>
