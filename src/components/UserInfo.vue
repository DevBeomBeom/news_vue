<template>
    <div>
        <template v-if="this.$route.name === 'my'">
            <p>name : 전찬범 </p>
            <p>karma : 0 </p>
            <p>created : 2022.03.15 </p>
        </template>
        <template v-else>
            <p>name : {{userInfo.id }} </p>
            <p>karma : {{userInfo.karma  }} </p>
            <p>created : {{userInfo.created }} </p>
        </template>
    </div>
</template>
<script>

export default{
    computed: {
        userInfo() {
            return this.$store.state.user;
        }
        
    },
    created() {

    const path = this.$route.name;
    // console.log(this.$route.path);
    let userName = "";

    if(path === 'my'){
       userName = '';
       this.$store.dispatch('FETCH_MY', userName);
    }else{
       userName = this.$route.params.id;
       this.$store.dispatch('FETCH_USER', userName);
    }
    }
   
}
</script>
