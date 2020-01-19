<template>
  <li
    class="todo-list__item"
  >
    <div :class="{'todo-list__item--cross': done}">
      {{message}}
    </div>
    <button @click="doneUndoneItem(), DoneUndoneX(id, done)">
      {{done === true ? "&#10005;" : "&#10004"}}
    </button>
  </li>
</template>

<style lang="scss" src="./list-item.scss"></style>

<script>
    export default {
        name: 'TodoListItem',
        props: {
            TodoListItem: Object,
            DoneUndoneX: Function,
            DeleteItemX: Function
        },
        data() {
            return {
                message: this.TodoListItem.name,
                done: this.TodoListItem.done,
                id: this.TodoListItem.id,
                doneUndoneItem: () => {
                    this.done = !this.done
                }
            }
        },
        methods: {},
        created() {
            console.log(this.DoneUndoneX)
        }
    }
</script>