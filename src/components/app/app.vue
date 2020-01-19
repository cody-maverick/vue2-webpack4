<template>
  <div class="todo-app">
    <h3>Задания: {{toDoses.length}}</h3>
    <TodoInput :addTodoItem="addTodoItem"></TodoInput>
    <TodoList
      v-if="toDoses.length > 0"
      :TodoListItems="toDoses"
      :DoneUndone="doneUndoneItem">
    </TodoList>
    <p v-else>Добавьте первое задание</p>
  </div>
</template>

<style lang="scss" src="./app.scss"></style>

<script>
    import TodoList from '../todo-list/list.vue'
    import TodoInput from '../todo-input/input.vue'

    export default {
        name: 'App',
        data() {
            return {
                toDoses: [],
                addTodoItem: (value) => {
                    if (value.length > 0) {
                        let data = new Date();
                        this.toDoses.push({
                            id: data.getTime(),
                            name: value,
                            done: false,
                        })
                    }
                },
                doneUndoneItem: (idx, donex) => {
                    const el = this.toDoses.findIndex((el) => el.id === idx);

                    this.toDoses = this.toDoses.map(({id, name, done}) => {
                        if (idx === id) {
                            return {
                                id,
                                name,
                                done: donex
                            }
                        } else {
                            return {
                                id,
                                name,
                                done

                            }
                        }
                    });
                },

            }
        },
        watch: {
            toDoses: (val, oldVal) => {
                console.log(val, oldVal);
                window.localStorage.setItem('localToDoses', JSON.stringify(val))
            }
        },
        mounted: function () {
            let local = window.localStorage.getItem('localToDoses');
            console.log(this.toDoses);
            if (JSON.parse(local)) {
                this.toDoses = JSON.parse(local)
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