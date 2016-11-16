<template>
  <div>
    <input v-model="newitem" @keyup.enter="handleNewItem" type="text" placeholder="Your Task" />
    <button type="button" @click="handleNewItem" >Add</button>
  </div>
</template>

<script>
  export default{
    data(){
      return{
        newitem: ''
      }
    },
    methods: {
      handleNewItem: function(event) {
        this.$emit('handleNewItem', this.newitem)
        this.newitem = ''
      }
    }
  }
</script>

<style>
</style>
