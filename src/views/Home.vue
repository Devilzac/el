<template>
  <div class="home">
    <item msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import item from '@/components/item.vue';

export default {
  name: 'home',
  components: {
    item,
  },
};
</script>
