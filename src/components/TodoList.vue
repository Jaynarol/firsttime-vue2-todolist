<template>
  <div>
    <ul class="list-unstyled">
      <todo-item v-for="item in items" :item="item" :key="item.id" @handleRemoveItem="handleRemoveItem" ></todo-item>
    </ul>
  </div>
</template>


<script>
  import TodoItem from './TodoItem'

  export default{
    props: ['items'],
    methods: {
      handleRemoveItem: function(itemid) {
        this.$emit('handleRemoveItem', itemid)
      }
    },
    components: {
      TodoItem
    }
  }

</script>

<style>
</style>