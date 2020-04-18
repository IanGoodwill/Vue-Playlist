
<template>

  <li>
   <strong> {{song.title}} </strong> by <strong> {{song.artist}} </strong>
    <button class="unliked-button" v-if="!song.favorite" @click="favoriteSong( song )">favorite</button>
    <button class="liked-button" v-else @click="favoriteSong( song )">favorite</button>
    <button v-on:click="deleteSong( song )">Delete Song</button>
  </li>

</template>

<script>
export default {
  name: "Song",
  props: ["song"],
  methods: {
        deleteSong (song) {
            this.$emit('delete-song', song);
        },
          favoriteSong(song) {
      this.$emit("like-song", song);
    },
    }
};
</script>

<style>
.liked-button {
 color: blue;
 font-family: fantasy;
  text-transform: uppercase;
}
</style>