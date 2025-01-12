<script setup>
defineProps({
  name: {
    type: String,
    required: false
  },
  title: {
    type: String,
    required: false
  },
  photo: {
    type: String,
    required: false
  }
})
</script>

<template>
  <div class="col-12 col-lg-8 offset-lg-4 mb-5">
    <div v-if="photo" class="d-block">
      <img class="img-fluid mb-2" :src="photo"/>
    </div>
    <h1 v-if="name" class="text-uppercase mb-0">{{ name }}</h1>
    <div v-if="title" class="subtitle fw-bold text-uppercase fs-5">
      {{ title }}
    </div>
  </div>
</template>

<style lang="scss" scoped>
.subtitle {
  line-height: 1.1rem;
}
</style>