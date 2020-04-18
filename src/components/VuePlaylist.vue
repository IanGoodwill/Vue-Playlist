<template>

  <section>

    <h2>My Vue Playlist</h2>

    <h3>Add a New Song:</h3>

    <form @submit="addSong">
      <label for="new-song">
        Song:  
        <input type="text" name="title" v-model="newSong" />
        <br>
        <br>
        Artist:  
        <input type="text" name="artist" v-model="newArtist" />
        <br>
      </label>
      <input type="submit" value="Submit" />
    </form>

    <br>
    <br>

    <ul class="my-list">
      <Song v-for="song in songs" :key="song.title" :song="song" v-on:delete-song="deleteSong"  v-on:like-song="likeSong"
          :class="{'liked-song' : song.favorite}"/>
    </ul>

  </section>

</template>

<script>
import Song from "./Song.vue";
export default {
  name: "Playlist",
  components: {
    Song
  },
  data() {
    return {
      newSong: "",
      newArtist: "",
      songs: [
        {
          title: 'Moonshine',
          artist: 'Caravan Palace',
          favorite: true
        },
          {
          title: 'Trapped',
          artist: 'Underworld & Iggy Pop',
          favorite: true
        },
          {
          title: 'Folkvangr',
          artist: 'Danheim',
          favorite: true
        },
      ]
    };
  },
  methods: {
    addSong(event) {
      event.preventDefault();
      const newSong = this.newSong;
      const newArtist = this.newArtist;
      this.songs.push({
        title: newSong,
        artist: newArtist,
        favorite: false
      
      });
      this.newSong = ""; 
      this.newArtist = "";
    },
    likeSong(song) {
      const faveIndex = this.songs.indexOf(song);
      this.songs[faveIndex].favorite = !this.songs[faveIndex].favorite;
    },
    deleteSong(song) {
      const songIndex = this.songs.indexOf(song);
      this.songs.splice(songIndex, 1);
    }
  }
};
</script>

<style>

.my-list li  {
    list-style-type:none;
}


</style>