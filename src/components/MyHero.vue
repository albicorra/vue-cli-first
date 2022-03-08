<template>
  <main class="ms_main">
    <div class="container-main">
            
      <!-- aggiungi articoli -->
      <section>       
        <div class="row ms_add-todo">
          <button type="button" class="ms_button" @click="addTodo">+</button>
          <input type="text" v-model="newTodo" placeholder="Aggiungi articoli..." @keyup.enter="addTodo" class="col-11 ms_input-add">
        </div>

      </section>

      <!-- articoli -->
      <section>
        <div class="ms_todo-list row" v-for="(el, i) in todo" :key="i">
          <button type="button" @click="checkTodo(i)" class="btn btn-light col-1 ms_button-check text-success fs-4">&#10003;</button>
          <div class="col-10 ms_todo" :class="el.done ? 'check' : '' ">{{el.text}}</div>
          <button type="button" @click="removeTodo(i)" class="btn btn-light col-1 ms_button-remove text-danger fs-4">&#10005;</button>
        </div>
      </section>

    </div>
  </main>
</template>

<script>
export default {
  name: 'MyHero',

  data () {
    return {
      newTodo: '',
      todo: [],
    }
  },
  
  methods: {

    addTodo: function() {
            
      if (this.newTodo.length !== 0) {
        this.todo.push({ text: this.newTodo, done: false,});
      }
      console.log(this.newTodo.length)    
      this.newTodo = '';
            
      console.log(this.todo);
    },

    removeTodo: function(index) {

    this.todo.splice(index, 1)

    },

    checkTodo: function(index){
      this.todo[index].done = !this.todo[index].done

      console.log(this.todo[index].done, index,)
            

    }

  }

}
</script>


<style scoped lang="scss">

/* main */
.ms_main{
  background-color: #FAFAFA;
  height: 88vh;
  padding: 100px 0px;
}

.container-main{
  max-width: 1320px;
  margin: 0 auto ;
}

/* add */
.ms_add-todo{
  height: 10vh;
  border: 2px solid #EAEAEA;
  background-color: #fff;
  margin-bottom: 40px;
  display: flex;
}

.ms_button{    
  color: #8b8b8b;
  z-index: 4;
  font-size: 32px;
  background-color: #f8f9fa;
  border-color: #f8f9fa;
  border: 1px transparent;
  border-radius: 4px;
  flex: 0 0 auto;
  width: 8.3%;
}

.ms_input-add{
  border: none;
  flex: 0 0 auto;
  width: 91.6%;
  padding: 20px;
  font-size: 18px;
}

.ms_input-add:focus-visible{
  outline: none;
}

/* todo */
.ms_todo-list{
  height: 6vh;
  border-bottom: 2px solid #EAEAEA;
  background-color: #fff;
  margin-bottom: 4px;
  display: flex;
}

.ms_todo{
  display: flex;
  align-items: center;
  padding: 0 30px;
  flex: 0 0 auto;
  width: 83.3%;
}

.ms_button-check{    
  color: #1A8753;
  z-index: 4;
  font-size: 32px;
  background-color: #f8f9fa;
  border-color: #f8f9fa;
  border: 1px transparent;
  border-radius: 4px;
  flex: 0 0 auto;
  width: 8.3%;
}

.ms_button-check:focus{
  box-shadow: 0 0 0 0.25rem rgba(1, 121, 1, 0.384);
}

.ms_button-remove{    
  color: #DC3550;
  z-index: 4;
  font-size: 32px;
  background-color: #f8f9fa;
  border-color: #f8f9fa;
  border: 1px transparent;
  border-radius: 4px;
  flex: 0 0 auto;
  width: 8.3%;
}

.ms_button-remove:focus{
  box-shadow: 0 0 0 0.25rem rgba(207, 0, 0, 0.384);
}

.ms_todo.check{
  text-decoration: line-through;
  text-decoration-color: green;
  color: green;
  background-color: #92ce9279;
}
</style>
