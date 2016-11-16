<template>
  <li>
    <span :class="{item, completed: item.completed}" @click="toggleComplete">{{item.name}}</span>
     - <button @click="handleRemoveItem">X</button>
  </li>
</template>

<script>
  export default{
    props: ['item'],
    methods: {
      toggleComplete: function() {
        this.item.completed = !this.item.completed
      },
      handleRemoveItem: function() {
        this.$emit('handleRemoveItem', this.item.id)
      }
    }
  }
</script>

<style>
  .item {
    color: gray;
  }

  .item:hover {
    cursor: pointer;
    color: black;
  }

  .completed {
    text-decoration: line-through;
  }
</style>