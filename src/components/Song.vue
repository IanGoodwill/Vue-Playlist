
<template>
  <li>
   <strong> {{song.title}} </strong> by <strong> {{song.artist}} </strong>
    <button v-on:click="deleteSong( song )">Remove Song</button>
  </li>
</template>

<script>
export default {
  name: "Song",
  props: ["song"],
  methods: {
        deleteSong (song) {
            this.$emit('delete-song', song);
        }
    }
};
</script>

<style>

</style>