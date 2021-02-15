<template>
  <div class="character-block">
    <div class="character-block__image">
        <img :src="character.image" :alt="character.name">
    </div>
    <div class="character-block__info">
        <span>{{ character.name }}</span>
        <span>{{ character.status }} - {{ character.species }}</span>
        <span>Last known location: {{ character.location.name }}</span>
    </div>
  </div>
</template>

<script>
export default {
    name: 'character-block',
    props: {
        character: {
            type: Object,
            required: true
        }
    }
}
</script>

<style lang="scss">

.character-block {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  width: 22%;
  margin: 10px;

  &__image img {
    width: 150px;
    height: auto;
  }

  &__info {
    display: flex;
    flex-direction: column;
  }
}

</style>