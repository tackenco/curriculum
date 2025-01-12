<script setup>
defineProps(['periode', 'job', 'company', 'experience'])
</script>

<template>
  <div class="job">
    <div class="content border-left pb-2">
      <div class="heading d-flex align-items-center">
        <div class="circle"></div>
        <!--<font-awesome-icon :icon="['far', 'circle']" />-->
        <div class="d-inline periode">{{ periode }}</div>
      </div>
      <h3 class="text-uppercase">{{ job }}</h3>
      <h3 class="fw-normal text-uppercase">{{ company }}</h3>
      <ul>
        <li v-for="(item, index) in experience" :key="index">
          {{ item }}
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped lang="scss">
.job {

  ul {
    padding-left: 1rem;
  }

  .heading {

    .circle {
      display: inline-block;
      width: 0.9rem;
      height: 0.9rem;
      border: 3px solid #000;
      border-radius: 50%;
      margin-left: -1.8rem;
      margin-right: 0.8rem;
      background-color: #fff;
    }

    svg {
      background-color: #fff;
      margin-left: -2rem;
    }
  }
}
</style>
