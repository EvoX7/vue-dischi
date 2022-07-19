<template>
    <div class="container d-flex flex-wrap">
      <div class="row">
        <div class="col-12">
          <h1 class="mt-5">Greatest Hits 1972 - 2018</h1>
        </div>
      </div>
        
        <SingleDisk class="col-5" v-for="disk in releases" :key="disk" :disk="disk"/>
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

<style>
</style>