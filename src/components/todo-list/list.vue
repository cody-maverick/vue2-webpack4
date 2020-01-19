<template>
  <div>
    <TodoListItem v-for="(item, i) in listItems" :key="i" :TodoListItemName="item">{{item}}</TodoListItem>
  </div>
</template>

<script>
    import TodoListItem from '../todo-list-item/list-item.vue';

    export default {
        name: 'TodoList',
        props: {
            TodoListItems: Array,
            a: String,
        },
        data() {
            return {
                listItems: this.TodoListItems
            }

        },
        created() {
        },
        components: {
            TodoListItem
        }
    }
</script>