<template>
  
  <!-- <h1>Hello {{animal}}</h1>
  <h2>{{food}}</h2>
  <input type="text" v-model="food"/>
  <div v-html="alertMessage"></div>

  <a :href="food">{{food}}</a>
  <hr/>
  <h2 v-bind:class="{red:food==='apple','not-good':food==='rice'}"> I like {{food}}.</h2> -->
  <h2>You age is {{age}}. </h2>
  <h3 v-if="age>18">You are a adult.</h3>
  <h3 v-else-if="age>13 && age<=18">You are a Youth.</h3>
  <h3 v-else>You are a child</h3>
   <input type="text" v-model="age"/>
   <!-- <h2 v-if="display">Showed</h2>
   <h2 v-show="display">Showed</h2>
   <h2 v-for="(animal,index) in animals" :key="index">{{animal}}::{{index}}</h2>
   <ul>
     <li v-for="(user,index) in users" :key="index">{{user.name}}
       <p v-for="item in user.skill" :key="item">{{item}}</p>
     </li>
   </ul> -->
   <!-- <h2 v-for="(animal,index) in animals" :key="index">
     <span v-if="animal !=='monkey'">{{animal}}::{{index}}</span>
   </h2> -->
   <template v-for="(animal,index) in animals" :key="index">
    <h2 v-if="animal !=='monkey'">{{animal}}::{{index}} </h2>
   </template>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      // animal:"Monkey",
      // food:"banana",
      // alertMessage:"<h2>ALERT</h2>",
      // imageSource:"https://placeimg.com/100/100/any",
      // naverUrl:"https://www.naver.com"
      age:30,
      display:true,
      animals:["monkey","rat","dog","lion"],
      users:[
        {name:'scalper',job:'developer',gender:'male',skill:["html","css","javascript"]},
        {name:'john',job:'designer',gender:'male',skill:["html","css","javascript"]},
        {name:'mac',job:'developer',gender:'male',skill:["html","css","javascript"]}
      ]
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

input{
  font-size: 20px;
}

.orange{
  color:orange;
}
.salmon{
  color:salmon;
}
.red{
  color:red;

}

.not-good{
  text-decoration: line-through;
}
</style>
