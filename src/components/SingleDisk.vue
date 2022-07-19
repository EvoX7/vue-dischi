<template>
  <div>
    <div class="card">
      <img :src="disk.poster" class="card-img-top p-3" alt="" />
      <div class="card-body">
        <h5 class="card-title text-white fw-bold">{{disk.title}}</h5>
        <p class="card-text fw-bold">{{disk.author}}</p>
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

<style lang="scss" scoped>
.card {
    background-color: #3a9efd;
    height: 350px;
    cursor: pointer;

    &:hover{

    }
}
</style>