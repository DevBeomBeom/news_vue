<template>
  <div>
      <!-- <div v-for="item in fetchedAsk" v-bind:key ="item.title"> {{ item.title }}</div> -->
       <p v-for="item in fetchedAsk" v-bind:key ="item.id">
        <a :href="item.url">{{ item.title }}</a>
        <small> {{item.time_ago}} by {{item.user}}</small>
      </p>
  </div>
</template>

<script>
import {mapGetters} from 'vuex';
// import {mapGetters, mapState} from 'vuex';


export default {
  computed:{
     ...mapGetters([
       'fetchedAsk'
     ])
    // #3
    // ...mapGetters({
    //   askItems : 'fetchedAsk'
    // })
    
    // #2
    // ...mapState({
    //   fetchedAsk: state => state.ask
    // }),

    // #1
    // ask() {
    // retrun this.$store.state.ask
    // }

  },
  created() {
      this.$store.dispatch('FETCH_ASK');
    }
}
</script>

<style>

</style>