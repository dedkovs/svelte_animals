<script>
  import { animals1, animals2, animals3 } from './data';

  export let selectedHabitat;

  const allAnimals = [...animals1, ...animals2, ...animals3];

  $: animalsByHabitat = allAnimals.filter(
    (habitat) => habitat.life_habitat === selectedHabitat.toLowerCase()
  );

  $: resultArray = selectedHabitat === 'All' ? allAnimals : animalsByHabitat;
</script>

<ul>
  {#each resultArray as animal (animal.animal)}
    <li>{animal.animal}</li>
  {/each}
</ul>
