<template>
    <div>
    <h2>{{name}}</h2>
        <ul>
            <!-- <ListItem v-for="todo in todos" :content="index"/>-->
            <!-- <ListItem v-if="name === 'Domestico'"/> tipado (3 === 3): true -->
            <!-- <ListItem v-if="name === 'Domestico'"/> sin tipado (3 == '3'): true -->
            <!-- <ListItem v-show="name === 'Domestico'"/> Está en el html pero no se muestra, el if no está en el html -->
            <ListItem v-for="(todo, index) in mytodos" :key="index" :content="index + ' ' + todo"/>
        </ul>
        <input type="text" ref="todoInput">
        <input type="button" value="Añadir" @click="addTodo">
    </div>
</template>

<script>
    import ListItem from "./ListItem.vue";
    export default {
        name: "category",
        props: ["name", "todos"],
        data(){
            return {
                mytodos:[]
            }
        },
        components: {
            ListItem
        },
        methods: {
            addTodo(){
                this.mytodos.push(this.$refs.todoInput.value);
                this.$refs.todoInput.value = "";
            }
        },
        created(){
            this.mytodos=this.todos;
        }
    }

</script>

<style scoped>

</style>