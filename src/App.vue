<template>
<!-- <h1>{{count}}</h1>
 <button v-on:click="addNumber(1)">Increase</button>
 <button v-on:click="minusNumber">Increase</button>
 <button v-on:mouseover="addNumber(10)">Increase10 over mouse</button> -->
 <h2>{{message}}</h2>
 <!-- <button @click="greeting">Greet</button>
  <button @click="goodbye">Bye</button> -->
  <div @click="getMousePosition" class="box"></div>
  <button @click="addNumber($event,10)">add10</button><button @click="addNumber($event,100)">add100</button>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      count:0,
      message:""
    }
  },
  methods:{
    getMousePosition(event){
      console.log(event);
      this.message=`Mouse Position:${event.pageX},${event.pageY}`;
    },
    greeting(){
     this.message="Hello";
    },
    goodbye(){
      this.message="Goodbye";
    },
    addNumber(e,value){
      this.message=`mouse pos ${e.pageX} add ${value}=${e.pageX+value}`;
    },
    minusNumber(){
      this.count=this.count-1;
    }
  }
  
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  width:100px;
  height:100px;
  font-size: 24px;
}
.box{
  width:300px;
  height:300px;
  background: salmon;
}
</style>
