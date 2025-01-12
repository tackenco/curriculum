<script setup>
import {BIconFolderFill} from "bootstrap-icons-vue";
import TheJob from "@/components/content/TheJob.vue";
defineProps(['jobs'])
</script>

<template>
  <!-- work experience header -->
  <h2 class="d-flex align-items-center text-uppercase adjust-left-margin">
    <BIconFolderFill/>
    Work experience
  </h2>
  <!-- work experience -->
  <div class="content w-80"
       v-for="(onejob, index) in jobs"
       :id="index"
       :key="index">
    <TheJob
        :periode="onejob.periode"
        :job="onejob.job"
        :company="onejob.company"
        :experience="onejob.experience"
    />
  </div>
</template>

<style scoped lang="scss">
.adjust-left-margin {
  margin-left: -10px;

  svg {
    margin-right: 5px;
  }

}

.content {
  padding-left: 20px;
  border-left: 2px solid black;

}
</style>