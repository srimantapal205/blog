<template>
  <div class="hello">
    <p>{{cname}}</p> 
    <h5>{{data.cename}}</h5>
    <button @click="$emit('someEvent')">Event Click</button>
    <button v-on:click="getData">Props Click</button>
     </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    cname: String,
    data: Object,
    getData: Function,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
