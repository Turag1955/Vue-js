<template>
  <div>
    <h1 v-if='show'>{{ data }}</h1>
    <h1 v-else>else is block</h1>
    {{ a+b }}
    <span> {{ ok ? 'yes':'no' }}</span>
    <p v-html="rowHtml"></p>
    <button v-bind:disabled="disabled" v-on:click="hello">click</button>
    <h2 class="heading_color">this is class</h2>
    <h2 v-bind:style="{color:'green'}">style add with vue</h2>
    <h2 v-bind:class="{display:showdisplay}">class add with object</h2>
    <h2 v-bind:class="[ ok ? acClass :'doubleclass','textcolor']">class add with array</h2>
    <!--data binding -->
    <p style="white-space: pre-line">message is: {{ message }}</p>
    <textarea type="text" v-model="message" placeholder="edit me" />
    <!-- multiple line -->
    <p>message is: {{ message }}</p>
    <input type="text" v-model="message" placeholder="edit me">
<!-- checkbox -->
    <input type="checkbox" id="checkbox" v-model="checkbox">
    <label for="checkbox">{{ checkbox }}</label>

<!-- multiple array in checkbox -->
   <div>Checked names: {{ checkedNames }}</div>
   <input type="checkbox"  id="jack" value="jack" v-model="checkedNames">
   <label for="jack">jack</label>
   <input type="checkbox" id="john" value="John" v-model="checkedNames">
   <label for="john">John</label>
   <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
   <label for="mike">Mike</label>

<!-- Radio Data bind -->
  <div>Picked: {{ picked }}</div>
  <input type="radio" id="one" value="one" v-model="picked">
  <label for="one">one</label>
  <input type="radio" id="two" value="two" v-model="picked">
  <label for="two">two</label>

<!-- Selecbox Data bind -->
  <div>Selected: {{ selected }}</div>
  <select v-model="selected">
    <option disabled  value="">Select pleace</option>
    <option value="a">a</option>
    <option value="b">b</option>
    <option value="c">c</option>
  </select>

<!-- props -->
 <h1 v-for="user in users " :key="user.name">{{ user.name }}</h1>

  <!-- table forloop -->
    <table>
      <thead>
        <th>name</th>
        <th>email</th>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.name }}</td>
          <td>{{ user.email }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'HomeTest',
    props: {
      data: String,
      msg:String
    },
    data(){
      return {
        show: true,
        users: [
          {id:1,name:'anil',email:'anil@gmail.com'},
          {id:2,name:'tanil',email:'anil@gmail.com'},
          {id:3,name:'kanil',email:'anil@gmail.com'},
          {id:4,name:'panil',email:'anil@gmail.com'},
        ],
        a:1,
        b:5,
        ok:false,
        rowHtml:'<span>hello i am row html</span>',
        disabled:false,
        showdisplay:true,
        acClass:'arrayclass',
        message: '',
        checkbox: true,
        checkedNames: [],
        picked: 'one',
        selected: ''
      }
    },
    methods: {
      hello(){
        this.ok = !this.ok
      }
    }
  }
</script>

<style scoped>
 .heading_color{
   color: red;
 }
 .display{
   background: orange;
 }
 .arrayclass{
   color: blue;
 }
 .doubleclass{
   background: red;
 }
 .textcolor{
   color: white;
 }
</style>