<script setup>
import {
  BIconEnvelopeFill,
  BIconLinkedin
} from "bootstrap-icons-vue";

defineProps({
  name: {
    type: String,
    required: true
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

  <nav class="container-fluid bg-dark py-1">
    <div class="d-flex align-items-center">
      <a href="/"
         class="text-uppercase text-light me-auto link-offset-2 link-offset-3-hover link-underline link-underline-opacity-0 link-underline-opacity-75-hover"
      >
        {{ name }}
      </a>
      <div>
        <a v-if="email" :href="'mailto:' + email"
           class="contact text-light"
           target="_blank">
          <BIconEnvelopeFill/>
        </a>
        <a v-if="linkedin" :href="linkedin"
           class="contact text-light"
           target="_blank">
          <BIconLinkedin/>
        </a>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
.contact {
  display: inline-block;
  padding: 1px;
  width: 25px;
  height: 25px;
  margin-left: 5px;
}
</style>