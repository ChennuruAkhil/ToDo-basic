# ToDo-basic
# verification

<template>
<div>
    <h2 v-on:click="change()">{{title}}</h2>
    <ul>
        <li><router-link to="/home">Home</router-link></li>
    </ul>
<div id="bdiv">
<b-button class="button"  @click="task('OrderSystem:NC',$event)"  >Nordic Connect</b-button>
<b-button class="button"  @click="task('WS',$event)" >Whole Sale</b-button>
<b-button class="button"  @click="task('WN',$event)">WAN</b-button>
<b-button class="button"  @click="task('MB',$event)">Mobil</b-button>
</div>
<div id="bdiv">
<b-button class="button"  @click="task('AC',$event)"  >A</b-button>
<b-button class="button"  @click="task('BS',$event)" >B</b-button>
<b-button class="button"  @click="task('CN',$event)">C</b-button>
<b-button class="button"  @click="task('DB',$event)">D</b-button>
</div>
<li>
<ul v-for="task in taskarr">{{task}}</ul>
</li>

 <b-button-group size="sm">
      <b-button
        v-for="(btn, idx) in buttons"
        :key="idx"
        :pressed.sync="btn.state"
        variant="primary"
      >
        {{ btn.caption }}
      </b-button>
    </b-button-group>
    <p>Pressed States: <strong>{{ btnStates }}</strong></p>
    </div>
</template>
<style scoped>
h2{
    color: antiquewhite;
    background-color: blue;
    padding: 30px;
    text-align: center
}
.actives{
    background-color: brown;
}
</style>
<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import {bus} from '../main'
export default {
    //name:'Header',
    props:['title'],
    data(){
        return{
            isactive:false,
            isbctive:false,
            iscctive:false,
            isdctive:false,
            cos:'',
            boo:false,
            buttons: [
          { caption: 'Toggle 1', state: true },
          { caption: 'Toggle 2', state: false },
          { caption: 'Toggle 3', state: true },
          { caption: 'Toggle 4', state: false }
        ],
        taskarr:[]
        }
    },
    computed: {
      btnStates() {
        return this.buttons.map(btn => btn.caption)
      }
    },
    methods:{
        
      task: function(val,e){
          this.cos=val;
          this.boo=!this.boo;
      console.log('task'+val);
      console.log(e);  
      e.target.classList.toggle('actives');
     // this.isactive=!this.isactive; 
     if(!this.taskarr.includes(val)){
     this.taskarr.push(val);
     }
     else{
       var index=this.taskarr.indexOf(val);
            this.taskarr.splice(index,1);
     }
     //console.log(this.taskarr.includes('NC'));
      },
        change:function(){
            console.log("changed");
            //this.$emit('change','Vue Changed');
            this.title="Vue Changed";
            bus.$emit('change','fucking Vue');
        }
    }
}
</script>

