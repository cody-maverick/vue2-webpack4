<template>
  <li class="todo-list__item">
    {{message.name}}
  </li>
</template>


<script>
    export default {
        name: 'TodoListItem',
        props: {
            TodoListItemName: String,
            a: String
        },
        data() {
            return {
                message: this.TodoListItemName
            }
        }
    }
</script>