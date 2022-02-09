<script>
  import { habitats } from './data';
  import Output from './Output.svelte';

  let selectedHabitat = 'All';
</script>

<select bind:value={selectedHabitat}>
  {#each habitats as habitat}
    <option value={habitat}>{habitat}</option>
  {/each}
</select>

<Output {selectedHabitat} />
