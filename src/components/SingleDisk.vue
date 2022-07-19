<template>
  <div>
    <div class="card" style="width: 18rem">
      <img :src="disk.poster" class="card-img-top" alt="" />
      <div class="card-body">
        <h5 class="card-title">{{disk.title}}</h5>
        <p class="card-text">{{disk.author}}</p>
        <p class="card-text">{{disk.year}}</p>
      </div>
      <div class="card-body">
        <a href="#" class="card-link"></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'SingleDisk',
    props: ["disk"],
};
</script>

<style>
</style>