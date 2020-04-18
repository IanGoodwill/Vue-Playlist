
<template>

  <li>
   <strong> {{song.title}} </strong> by <strong> {{song.artist}} </strong>
    <button class="unliked-button" v-if="!song.favorite" @click="likeSong( song )">FAVORITE</button>
    <button class="liked-button" v-else @click="likeSong( song )">FAVORITE</button>
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
          likeSong(song) {
      this.$emit("like-song", song);
    },
    }
};
</script>

<style>
.liked-button {
 color: blue;
}
</style>