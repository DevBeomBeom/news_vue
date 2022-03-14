<template>
  <div>
    <list-item></list-item>
  </div>
</template>

<script>
import ListItem from '../components/ListItem.vue'
import {mapGetters} from 'vuex';

export default {
  computed:{
   ...mapGetters([
     'fetchedJobs'
   ])
 },
 components : {
   ListItem
 }
    // created() {
    //   this.$store.dispatch('FETCH_JOBS');
    // }
}
</script>
