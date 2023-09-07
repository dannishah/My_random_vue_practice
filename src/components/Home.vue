<template>


<h1>Email: {{email}} Mobile {{mobile=8888}}</h1>
<button v-on:click='test()'>Click me</button> <br>

<input type="text" v-model="count">
<h2>{{count}}</h2>

<input type="text" placeholder="Enter email" v-model="email1"><br>
<input type="password" placeholder="Enter password" v-model="password"><br>
<button type="button" v-on:click="getBtn()"> Get button</button>

<br><br>

<label for="java">Java</label>
<input type='checkbox' value='Java' v-model="technology" id='java'>
<label for="php">Php</label>
<input type='checkbox' value='php' v-model="technology" id='php'> 
<label for="node">Node</label>
<input type='checkbox' value='node' v-model="technology" id='node'> 
<h2>Selected Technology : {{technology}}</h2>

<h3>Who I am</h3>

<label for='student'>Student</label>
<input type='radio' value='student' v-model="who" id='student' name='who'>

<label for='developer'>Developer</label>
<input type='radio' value='developer' v-model="who" id='developer' name='who'>

<label for='engineer'>Engineer</label>
<input type='radio' value='engineer' v-model="who" id='engineer' name='who'>
<h3>You are :{{who}}</h3> 

<h3 v-if="show"> If condition is true</h3>
<h3 v-else> Else condition</h3>
<button type="button" v-on:click="show=!show">Show</button>

<h3>For loops in VUE</h3>
<ul>
<li v-for="item in technology1" :key="item">{{item}}</li>
</ul><br><br>

<ul>
    <li v-for="item in user" :key="item">Name : {{item.name1}} , Email : {{item.code1}}</li>
</ul>

<h1>HTML Binding</h1>
<div v-html='tag'></div>
<div v-html='tag2'></div>

<h1>CSS Binding</h1>
<h3 :class="{green:colorfull}">this is style check line</h3>
<button type="button" v-on:click="colorfull=!colorfull">Change Style</button>

<h1>Ref in VUE</h1>
<input type="text" ref="input"><br><br>
<button type="button" v-on:click="ref()">Use ref</button>

<h1>Simple from</h1>
<form>
    <label for="email">Email: </label>
    <input type="email"  id='email' v-model="femail">
     <br><br>
    <label for="password">Password:</label>
    <input type="password"  id='password' v-model="fpassword">
         <br><br>
    <button type="button" v-on:click='login()'>Log in</button>

</form>

<Child :email='email' :test="test" />
</template>









<script>
/* eslint-disable */

import Child from './Child.vue';
export default {
    name:'Home',
    components : {
        Child
    },
    data(){
        return{
            email:'dani@gmail.com',
            mobile:"0033003",
            email1:null,
            password:null,
            count:0,
            technology:[],
            who:[],
            show:false,
            technology1:["Apple","Mango", "Banana"],
             tag:'<h1>Binding 1</h1>',
             tag2:'<h1>Binding 2</h1>',
             colorfull:true,
             form : {
                femail :" ",
                fpassword:" "
             },
        
            user:[
                {
                    name1:'ahmed',
                    code1:'ahmed@123'
                },
                {
                    name1:'Ali',
                    code1:'ali@123'
                },
                    
                
            ]
        }            
    },

    
    methods: {
        test(){
            alert('Welcome')
        },

         getBtn(){
               console.log(this.email1, this.password)
        },
        ref(){
              this.$refs.input.focus();
              let val = this.$refs.input.value;
              console.warn(val);
         
        },

        login(){
            console.warn(this.femail,this.fpassword)
        } 

    },
  

}
</script>











<style scoped>
.green{
    background-color:green;
    color:white;
    text-align:center;
}
    h1{
        color:red;
    }
    h3 ul li{
        display:block;
    }

    button{
        background:black;
        color:white;
        padding:5px;
        margin :5px;
    }
</style>