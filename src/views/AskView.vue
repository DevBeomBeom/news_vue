
<template>
  <div>
   <list-item></list-item>
  </div>
</template>

<script>
import ListItem from '../components/ListItem.vue';
import {mapGetters} from 'vuex';
// import {mapGetters, mapState} from 'vuex';


export default {
  components:{
    ListItem,
  },
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
