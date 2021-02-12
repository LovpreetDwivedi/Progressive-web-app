<template>
<div>
    <h3>Add todo</h3>
  <div>
      <form @submit="onSubmit">
          <input
          type="text"
          v-model="title"
          placeholder="add todo...."
          >
          <input type="submit" value="Submit" >
      </form>

  </div>
</div>
</template>

<script>
import{mapActions} from 'vuex'
export default {
name:"AddTodos",
data(){
    return{
    title:""
    }
},
methods:{
    ...mapActions(['addTodos']),

    onSubmit(e){
      e.preventDefault();
      this.addTodos(this.title)
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
     padding: 10px;
     border:1px solid red;
    outline: 0;
 }
 input[type="submit"]{
     flex: 2;
     background: yellow;
     border: 1px solid red;
     cursor: pointer;
 }
</style>