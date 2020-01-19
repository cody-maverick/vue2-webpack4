<template>
  <div class="todo-app">
    <TodoInput :addTodoItem="addTodoItem"></TodoInput>
    <TodoList :TodoListItems="toDoses"></TodoList>
  </div>
</template>

<script>
    import TodoList from '../todo-list/list.vue'
    import TodoInput from '../todo-input/input.vue'

    export default {
        name: 'App',
        data() {
            return {
                toDoses: [
                    {
                        name: 'Помыть посуду',
                        done: false
                    },
                    {
                        name: 'Вытереть посуду',
                        done: false
                    }
                ],
                addTodoItem: (value) => {
                    this.toDoses.push({name: value, done: false})
                }
            }
        },
        components: {
            TodoList,
            TodoInput
        },
        created() {
        }
    }

</script>