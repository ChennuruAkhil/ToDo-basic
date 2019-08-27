<template>
    <p>Hello {{tasks}}</p>
</template>
<script>

export default {
    props:['task'],
    data(){
        return{
           tasks:this.$refs.task.value
        }
    }
}
</script>