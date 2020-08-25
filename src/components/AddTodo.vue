<template>
    <div>
        <form  @submit="addTodo">
        <input type="text" v-model="title" name="Titulo" placeholder="Add Todo...">
        <input type="submit" value="Submit" class="btn">
        </form>
    </div>    
</template>

<script>
// import Vue from "vue";
// import UUID from "vue-uuid";


export default {
    name:"AddTodo",
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e){
           e.preventDefault();
            const newTodo = {      
                title: this.title,
                completed: false
            }
            // Send this up to the parent component
            this.$emit('add-todo',newTodo);

            this.title = '';
        }
    }
}
</script>

<style scoped>
form{
    display: flex;
}

input[type="text"]{
    flex: 10;
    padding: 5px;
}

input[type="submit"]{
    flex:2;
}

</style>