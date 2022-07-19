<template>
  <div>
    <div class="row p-5">
      <h1 class="text-white mb-5 fw-bold">Greatest Albums 1972 - 2018</h1>
  
        <SingleDisk
          class="col-2 mb-4"
          v-for="disk in releases"
          :key="disk"
          :disk="disk"
        />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SingleDisk from "./SingleDisk.vue";

export default {
  name: "DisksDisplay",
  components: {
    SingleDisk,
  },
  data: function () {
    return {
      releases: [],
    };
  },

  methods: {
    getDiskInfo: function () {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          console.log(result.data.response);
          this.releases = result.data.response;
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