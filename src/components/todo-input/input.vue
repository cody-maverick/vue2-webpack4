<template>
  <div class="todo-list__input">
    <input v-model.trim="todoItem" @keypress.enter="addTodoItem(todoItem), clearInput()" placeholder="Введите занятие...">
    <button @click="addTodoItem(todoItem), clearInput()">добавить</button>
  </div>
</template>

<script>
    export default {
        name: 'TodoInput',
        props: {
            addTodoItem: Function,

        },
        data() {
            return {
                todoItem: '',
            }
        },
        methods: {
            clearInput() {
                this.todoItem = '';
            }
        }
    }
</script>