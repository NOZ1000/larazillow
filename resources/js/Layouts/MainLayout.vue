<template>
  <Link href="/">Main Page</Link>&nbsp;
  <Link href="/hello">Show Page</Link>
  <!-- <div>The page with time {{ timer }}</div> -->
  <div v-if="flashSuccess" class="success">
    {{ flashSuccess }}
  </div>
  <div>
    {{ y }}
  </div>
  <slot />
</template>


<script setup>
import { computed } from 'vue';
import { Link, usePage } from '@inertiajs/inertia-vue3'

//  page.props.value.flash.success
const page = usePage();
const flashSuccess = computed(
  () => page.props.value.flash.success,
);

</script>

<style scoped>
  .success {
    background-color: green;
    color: white;
  }
</style>