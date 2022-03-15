<template>
  <div >
     <!-- 질문 상세정보 -->
     <section>
        <div class="user-container">
            <div>
                <i class="fas fa-user"></i>
            </div>
            <div class="user-description">
                <router-link :to="`/user/${fetchedItem.user}`">
                    {{ fetchedItem.user }}
                </router-link>
                <div class="time">
                    {{ fetchedItem.time_ago}}
                </div>
            </div>
        </div>
        <h2> {{fetchedItem.title}} </h2>
     </section>
     <!-- 질문 댓글 -->
     <section v-html="fetchedItem.content">
     </section>
  </div>
</template>

<script>
import {mapGetters} from 'vuex';
export default {
    computed:{
        ...mapGetters(['fetchedItem'])
    },
    created() {
    // this.$emit('on:progress');
    const itemId = this.$route.params.id;
    this.$store.dispatch('FETCH_ITEM', itemId);
    //   .then(() => this.$emit('off:progress'))
    //   .catch(error => console.log('user fetch error', error));
  },
//   computed: {
//     ...mapGetters([
//       'fetchedItem', 'userName', 'userTimeAgo', 
//       'userQuestion', 'userContent', 'contentPoints']),
//   },
}
</script>

<style scoped>

.user-container {
  display: flex;
  align-items: center;
}
.fa-user {
  font-size: 2.5rem;
}
.user-description {
  padding-left: 8px;
}
.time {
  font-size: 0.7rem;
}

</style>