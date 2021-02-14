<template>
  <div class="home">
    RickAndMortyList
    <!-- {{ characters }} -->
    <character-block/>
    {{ firstCharacter }}
  </div>
</template>

<script>
import CharacterBlock from '@/components/CharacterBlock.vue';

export default {
  name: 'rick-and-morty-list',
  components: {
    CharacterBlock
  },
  created() {
    this.$store.dispatch('fetchCharacters', 1);
  },
  computed: {
    characters() {
      return this.$store.state.characters;
    },
    firstCharacter() {
      return this.$store.getters['getCharacterById']({id: 1, page: 1});
    }
  }
}
</script>
