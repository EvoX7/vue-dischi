<template>
  <div>
    <div v-if="isLoaded">
      <Loader />
    </div>
    <div v-else>
      
      <div class="row p-5">
        <h1 class="text-white mb-5 fw-bold">Greatest Albums 1972 - 2018</h1>

    <div class="row">
        <div class="col-8 m-auto mb-5"><SelectByAuthor /></div>
      </div>

      <div class="row">
        <div class="col-8 m-auto mb-5"><SelectByAlbum /></div>
      </div>


        <SingleDisk
          class="col-2 mb-4"
          v-for="disk in releases"
          :key="disk"
          :disk="disk"
        />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SingleDisk from "./SingleDisk.vue";
import Loader from "./Loader.vue";
import SelectByAuthor from "./SelectByAuthor.vue";
import SelectByAlbum from "./SelectByAlbum.vue";

export default {
  name: "DisksDisplay",
  components: {
    SingleDisk,
    Loader,
    SelectByAuthor,
    SelectByAlbum,
  },
  data: function () {
    return {
      releases: [],
      isLoaded: true,
    };
  },

  methods: {
    getDiskInfo: function () {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          console.log(result.data.response);
          this.releases = result.data.response;
          setTimeout(() => {
            this.isLoaded = false;
          }, 1700);
        });
    },
  },

  created() {
    this.getDiskInfo();
  },
};
</script>

<style lang="scss" scoped>
</style>