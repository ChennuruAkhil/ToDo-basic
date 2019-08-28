<template>
  <div id="app">
    <div id="head">
      <h3 style="text-align:center;color:white">My ToDo List</h3>
      <input type="text" id="data" ref="task" placeholder="    Enter the task">
      <button v-on:click="newElement()" style="padding=:5px">Add</button><br><br>
    </div>
   <List v-bind:tasksarr="tasksarr"></List>
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
      tasksarr:[]
    }
  },
  methods:{
    newElement : function(){
      var task1=this.$refs.task.value;
      this.tasksarr.push(task1);
      this.$refs.task.value='';
    
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
body{
  width: 703px;
}
#head {
  background-color: darkcyan;
  padding: 5px;
  color: white;
  text-align: center;
  width:703px;
  left:350px;
  position: relative;

}
#data{
  width: 500px;
  position:relative;
}
button{
  cursor: pointer;
  padding: 5px;
  background-color: #eee;
  border: 0px;
  width: 80px
}

</style>
