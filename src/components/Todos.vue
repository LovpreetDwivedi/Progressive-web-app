<template>
  <div class="container">
      <h3>todos</h3>
      <div class="box">
<div v-for="todo in allTodos" :key="todo.id" class="todo-box">
         {{ todo.title}}
         <span @click="deleteTodos(todo.id)">X</span>
      </div>
      </div>
  </div>
</template>

<script>
import{ mapGetters ,mapActions} from 'vuex';
export default {
name:"Todos",
methods: {
    ...mapActions(['fetchTodos','deleteTodos']),
},
computed: mapGetters(['allTodos']),
created(){
    this.fetchTodos();

}

}
</script>

<style  scoped>
.box{
    display: grid;
    grid-template-rows: repeat(3,1fr);
    grid-gap:1rem;
}

.todo-box{
    border: 1px solid red;
    background: yellow;
    padding: 10px;
    border-radius: 5px;
    text-align: center;
    position: relative;
    cursor: pointer;
}
span{
    position: absolute;
    bottom: 10px;
    right: 10px;
    cursor: pointer;
}
</style>