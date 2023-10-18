<script setup lang="ts">
const props = defineProps<{
  slug: String;
}>();
const pokemonSlugs = ["bulbasaur", "charmander", "squirtle"];

const pokemon = await $fetch(`https://pokeapi.co/api/v2/pokemon/${props.slug}`);
</script>
<template>
  <UCard>
    <img
      :src="`https://assets.pokemon.com/assets/cms2/img/pokedex/full/${addLeadingZeros(
        pokemon.id
      )}.png`"
      :alt="pokemon.name"
    />
    <template #footer>
      <h2 class="text-xl">{{ pokemon.name }}</h2>
    </template>
  </UCard>
</template>
