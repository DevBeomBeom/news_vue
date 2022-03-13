<template>
  <div>
      <!-- <div v-for="user in this.$store.state.news" v-bind:key ="user.id"> {{ user.title }}</div> -->
      <p v-for="item in fetchedNews" v-bind:key ="item.id">
        <a :href="item.url">{{ item.title }}</a>
        <small> {{item.time_ago}} by {{item.user}}</small>
      </p>
  </div>
</template>

<script>
// import axios from 'axios';
// import { fetchNewsList } from '../api/index.js'
import {mapGetters} from 'vuex';


export default {
 computed:{
   ...mapGetters([
     'fetchedNews'
   ])
 },
  created() {
    this.$store.dispatch('FETCH_NEWS');
  }
}
</script>

<style>

</style>