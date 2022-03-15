<template>
    <div>
        <user-info></user-info>
        <!-- <p>name : {{userInfo.id}} </p>
        <p>karma : {{userInfo.karma}} </p>
        <p>created : {{userInfo.created}} </p> -->
    </div>
</template>
<script>
import UserInfo from '../components/UserInfo.vue'

export default{
    components:{
        UserInfo
    }
   
}
</script>
