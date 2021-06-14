<template>
  <form action="#" @submit.prevent="getMusic()">
    <input v-model="query" type="text" />
  </form>

  <p>
    {{ query }}
  </p>
</template>

<script>
import axios from "axios";



export default {
  data() {
    return {
      query: "",
    };
  },

//   emits: ["add-new-songs"],

  methods: {
    getMusic() {
      axios
        .get(
          `https://itunes.apple.com/search?term=${encodeURI(
            this.query
          )}&entity=musicTrack&limit=15`
        )
        .then((response) => {
          // handle success
    
          let iTunes = response.data.results
            .filter((song) => song.kind === "song")
            .map((song) => this.extractData(song));

					window.eventBus.emit('new-songs-arrived', iTunes)

        });
    },

    extractData({
      trackId: id,
      artistName: artist,
      previewUrl: audioFile,
      artworkUrl100: cover,
      trackName: name,
      collectionName: album,
    }) {
      return { id, artist, audioFile, cover, name, album };
    },
  },
};
</script>

<style lang="scss" scoped></style>
