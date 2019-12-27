<template>
<div class="row">
  <div class="card col-4" v-for="item in todo" :key="item.id">
    <div class="card-body">
      <h5 class="card-title">
        <span v-if="item.user">{{ item.user.name.first }} {{ item.user.name.last }} </span>
      </h5>
      <p class="card-text" v-if="item.text">{{item.text}}</p>
      <h6 v-if="item.upvotes"><strong>Votos</strong> | {{item.upvotes}}</h6>
    </div>
  </div>
</div>
</template>

<script>
import Axios from 'axios';

export default {
  data() {
    return {
      todo: null,
      page: 1,
      perPage: 6,
      pages: [],
    };
  },
  mounted() {
    this.getInfo();
  },
  methods: {
    async getInfo() {
      const response = await Axios.get('https://cors-anywhere.herokuapp.com/https://cat-fact.herokuapp.com/facts');
      this.todo = await response.data.all;
    },
    setPages() {
      const numberOfPages = Math.ceil(this.todo.length / this.perPage);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
