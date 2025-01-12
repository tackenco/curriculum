<script setup>
import {BIconPersonFill} from "bootstrap-icons-vue";
</script>

<template>
  <!-- profile header -->
  <h2 class="d-flex align-items-center text-uppercase adjust-left-margin">
    <BIconPersonFill/>
    About me
  </h2>
  <!-- about me -->
  <div class="content w-80 mb-5">
    <p>Hi, I'm Niels. I’m a Dutch web professional with over 30 years of working experience. At this moment I am
      managing the web- and CRM teams for Alpina Online (Alpinagroup)</p>
    <p>Throughout my career I’ve been developing solutions for all sorts of businesses, both as architect and developer
      on a wide variety of projects. I am used to work with all stakeholders within a project and I have excellent
      communication skills which makes me qualified to set up and lead development teams.</p>
    <p>My main focus as manager online is to let my teams perform better and increase the quality of our output. With my
      experience and trackrecord I contribute to my teams by providing knowledge and structure. I'm a sparring
      partner within the teams as wel as within the whole organization.</p>
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