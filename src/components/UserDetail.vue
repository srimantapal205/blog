<template>
    <div class="bBlock">
        <h4>
            {{userData.userName}},</h4>
           <p> {{userData.email}}</p>
        <button v-on:click="getName(userData.userName)">Get Name</button>
    </div>
</template>

<script>
    export default {
        name:"UserDeatils",
        props: {
            userData:Object,
            getName:Function
        },  
        data() {
            return {
                
            }
        },
        methods: {
          
        },
    }
</script>

<style lang="scss">
.bBlock{
    border: 1px solid #f3f3f3;
       padding: 5px;
        background-color: #f5f5f5;
        margin-bottom: 10px;
}
</style>