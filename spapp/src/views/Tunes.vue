<template>
  <div class="tunes">
    <h1>This is an tunes page</h1>

    <TunesSearchForm />
    <TunesList />
  </div>
</template>

<script>
import TunesSearchForm from "@/components/tunes/TunesSearchForm.vue";
import TunesList from "@/components/tunes/TunesList.vue";


export default {
  components: {
    TunesSearchForm,
    TunesList,
  },
};
</script>

<style lang="scss" scoped></style>
