<template>
    
<section>

    <h2>My Vue Playlist</h2>

    <form @submit="addNewSong" >

        <label for="new-song">
           Enter A Song Name 
           <br>
            <input type="text" name="new-song" v-model="newSong">
        </label>
            <br>
          <label for="new-artist">
            Enter The Name Of The Artisit
            <br>
            <input type="text" name="new-artisit" v-model="newArtist">
        </label>
            <br>
        <input type="submit" value="Submit">

    </form>

    <h3> Your Custom Playlist! </h3>

    <ul>
        <Song v-for="song in songs" :key="song.task" :task="song.task" :song="song" />
        <Artist v-for="artist in artists" :key="artist.task" :task="artist.task" :artist="artist" />
    </ul>

   

</section>

</template>



<script>
import Song from './Song.vue';
import Artist from './Artist.vue';

export default {
    name: 'VuePlaylist',
    components:  {
        Song,
        Artist
    },
    data () {
        return {
            newSong: '',
            newArtist: '',
            songs: [],
            artists: []
            
        }
    },
    methods:  {
        addNewSong ( event )  {
            event.preventDefault();
            const newSong = this.newSong;
            this.songs.push( {
                task: newSong,
                
            } );
            this.newSong = '';
            const newArtist = this.newArtist;
            this.artists.push( {
                task: newArtist,
                
            } );
            this.newArtist = '';
        }
    },
         addNewArtist ( event )  {
            event.preventDefault();
            const newArtist = this.newArtist;
            this.artists.push( {
                task: newArtist,
                
            } );
            this.newArtist = '';
        }
   
}
</script>



<style>

</style>