<template>
<div>
    <h2 v-if="completeflag">Completed Tasks</h2>
    <div>
        <ul id="ul">
            <li v-for="ctask in completearr">
                {{ctask}}
                <span class="close" v-on:click="deletetask(ctask)">x</span>
            </li>
        </ul>
    </div>
</div>
</template>
<script>
export default {
    props:['completearr','completeflag'],
    methods: {
        deletetask:function(todo){
            var index=this.completearr.indexOf(todo);
            this.completearr.splice(index,1);
        }
    },
}
</script>
<style>
h2{
    text-align: left;
    position: relative;
    left:350px;
    color:darkcyan;
}
</style>