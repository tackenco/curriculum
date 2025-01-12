<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  items: {
    type: Array,
    required: false
  }
})
</script>

<template>
  <div class="bullet-list">
    <h3 v-if="title" class="text-uppercase">{{ title }}</h3>
    <ul v-if="items && items.length > 0" class="list-unstyled mb-5">
      <li v-for="(item, index) in items" :key="index">
        <span>{{ item.key }}</span>
        <div class="float-end text-right mr-4">
          <span v-for="(bullet, i) in item.value" :key="i" class="ml-1">&#8226;</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped lang="scss">
li {
  line-height: 1;
  margin-bottom: 0.5rem;
  padding-right: 1.5rem;
}
</style>