<template>
  <ul class="tunes-list">
    <li>
        <TunesSong v-for="song in songs" :key="song.id" :song="song" />
    </li>  
  </ul>
</template>

<script>
import TunesSong from "@/components/tunes/TunesSong.vue";

export default {
  components: {
    TunesSong,
  },

  data() {
      return {
          songs: [],
      }
  },
	mounted() {
		window.eventBus.on('new-songs-arrived', data => (this.songs = data))
	}
};
</script>

<style lang="scss" scoped>
  .tunes-list {
    list-style: none;
    padding: 0;
    margin: 0;
    margin-bottom: 3em;
  }

</style>
