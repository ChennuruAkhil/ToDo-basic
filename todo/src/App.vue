<template>
  <div id="app">
    <div id="header">
      <h2>My ToDo List</h2>
      <input type="text" id="task" ref="task" placeholder="Title...">
      <span v-on:click="newElement()" class="addBtn">Add</span>
    </div>
   <p>Lets Rock</p>
   <List v-bind:task="task"></List>
  </div>
</template>

<script>
import List from './components/list.vue'
export default {
  name: 'app',
  components:{
    List :List
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      task:''
    }
  },
  methods:{
    newElement : function(){
      console.log("added");
      var task[];
      = this.$refs.task.value;
      console.log(task[0]);
      this.task=task[0];
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
body {
  position: relative;
  margin: 0;
  min-width: 150px;
  width: 800px;
  left: 300px
}
#header {
  background-color: darkcyan;
  padding: 30px 40px;
  color: white;
  text-align: center;
  padding-top: 10px

}
#task{
  width: 650px;
}
.addBtn {
  padding: 5px;
  width: 5%;
  background: #d9d9d9;
  color: #555;
  float: right;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
  border-radius: 0;
}

.addBtn:hover {
  background-color: #bbb;
}
</style>
