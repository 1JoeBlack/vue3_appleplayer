<template>
  <transition name="fade">
    <article v-cloak>
      {{ songify(song) }}

      <div>
        <img v-if="song.cover" :src="song.cover" alt="image not found" />
      </div>

      <figure>
        <figcaption>{{ song.album }}</figcaption>
        <audio controls :src="song.audioFile">
          Your browser does not support the
          <code>audio</code> element.
        </audio>
      </figure>
    </article>
  </transition>
</template>

<script>
export default {

  props: {
		song: {
			type: Object
		}
	},
  methods: {
    songify(song) {
      return song.artist + " - " + song.name;
    },
  },
};
</script>

<style lang="scss" scoped>

[v-cloak] {
	display: none;
}

.fade-enter-active {
  transition: all 2.5s ease;
}

.fade-enter {
  opacity: 0;
}

</style>

