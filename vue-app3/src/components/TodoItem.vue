<template>
    <li>
        <span :class="{done: todo.completed}">
            <input type="checkbox" @change="todo.completed = !todo.completed">
            <strong>{{idx+1}}</strong>
            {{todo.title}}
        </span>
        <button class="rm" @click="$emit('remove-todo', todo.id)">&times;</button>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true 
        },
        idx: Number
    }
}
</script>

<style scoped>
 li {
     border: 1px solid #ccc;
     display: flex;
     justify-content: space-between;
     padding: .5rem 2rem;
     margin-bottom: 1rem;
 }
 .rm {
     background-color: red;
     border-radius: 50%;
     font-weight: bold;
     color: #fff;
 }
 input {
     margin-right: 1rem;
 }
 .done {
     text-decoration: line-through;
 }
</style>