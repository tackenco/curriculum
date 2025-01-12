<script setup>
defineProps({
  title: {
    type: String,
    required: false
  },
  name: {
    type: String,
    required: false
  },
  dateOfBirth: {
    type: String,
    required: false
  },
  domicile: {
    type: String,
    required: false
  },
  country: {
    type: String,
    required: false
  },
  email: {
    type: String,
    required: false
  },
  linkedin: {
    type: String,
    required: false
  }
})
</script>

<template>
  <div itemscope="" itemtype="http://schema.org/Person">
    <h3 v-if="title" class="text-uppercase">Personal</h3>
    <ul class="list-unstyled mb-5">
      <li v-if="name">{{ name }}<br/><span class="small">({{ dateOfBirth }})</span></li>
      <li v-if="domicile">{{ domicile }} {{ country }}</li>
      <li>
        <a v-if="email" class="link-dark link-underline link-underline-opacity-0 link-underline-opacity-75-hover"
           :href="'mailto:' + email">Email me</a><br/>
        <a v-if="linkedin" class="link-dark link-underline link-underline-opacity-0 link-underline-opacity-75-hover"
           :href="linkedin"
           target="_blank">LinkedIn</a></li>
    </ul>
  </div>
</template>

<style scoped lang="scss">
li {
  line-height: 1;
  margin-bottom: 0.5rem;
}
</style>