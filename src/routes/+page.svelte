<script lang="ts">
  import { match, resolve } from "$app/paths";
  import { goto } from "$app/navigation";

  const returnPage = "/params/foo" as string; // set from a different page

  async function onclick() {
    const matched = await match(returnPage);
    if (matched) {
      await goto(resolve(matched.id, matched.params));
    }
  }
</script>

<h1>Example Without Route Parameters</h1>

<button {onclick}>Go to return page</button>
