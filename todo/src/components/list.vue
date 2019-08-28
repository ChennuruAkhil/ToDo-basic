<template>
<div>
<div>
    <ul id="ul">
        <li v-for="task in tasksarr" v-on:click="completedtask(task)">
            {{task}}
        </li>
    </ul>
</div>
 <div>
    <Completed v-bind:completearr="completearr" v-bind:completeflag="completeflag"></Completed>
</div>
</div>
</template>
<script>
import Completed from './Completed.vue'
export default {
    props:['tasksarr'],
    data(){
        return{
           completearr:[],
           completeflag:false
        }
    },
    components:{
        Completed
    },
    methods: {
        deletetask:function(todo){
            var index=this.tasksarr.indexOf(todo);
            this.tasksarr.splice(index,1);
        },
        completedtask:function(todo){
            var ctask1=todo;
            this.completearr.push(ctask1);
            this.deletetask(todo);
            this.completeflag=true;

        }
    },
}
</script>
<style>
#ul{
    left:310px; position: relative; list-style: none; margin: 0px
}
ul li{
    width: 703px;
    cursor: pointer;
    background-color: #eee;
    position: relative;
    text-align: left;
    padding: 12px 8px 12px 5px
}
ul li:nth-child(odd){
    background-color: #f9f9f9;
}
ul li:hover{
    background-color: #ddd;

}
ul span.close{
    position: absolute;
    right :0px;
    top:0px;
    padding: 12px 16px 12px 16px;
}
ul span.close:hover{
    background-color: #f44336;
    color: white;
}
</style>