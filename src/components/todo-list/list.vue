<template>
  <ul class="todo-list">
    <TodoListItem
      v-for="(item, i) in listItems"
      :key="i"
      :TodoListItem="item"
      :DoneUndoneX="DoneUndone">
      {{item}}
    </TodoListItem>
  </ul>
</template>

<style lang="scss" src="./list.scss"></style>

<script>
    import TodoListItem from '../todo-list-item/list-item.vue';

    export default {
        name: 'TodoList',
        props: {
            TodoListItems: Array,
            DoneUndone: Function,
            DeleteItem: Function
        },
        data() {
            return {
                listItems: this.TodoListItems,
                DoneUndone: this.DoneUndone
            }

        },
        created() {
        },
        components: {
            TodoListItem
        }
    }
</script>