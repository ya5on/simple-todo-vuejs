<template>
    <div>
        <ul>
            <TodoItem
                    v-for="(todo, i) in todos"
                    v-bind:todo="todo"
                    v-bind:index="i"
                    v-on:remove-todo="removeTodo"/>
        </ul>
    </div>
</template>

<script>
    import TodoItem from '@/components/TodoItem'

    export default {
        components: {
            TodoItem
        },
        props: ['todos'],
        methods: {
            removeTodo(id) {
                this.$emit('remove-todo', id)
            }
        }
    }
</script>

<style lang="sass" scoped>
    ul
        list-style: none
        margin: 0
        padding: 0


</style>
