<template>
  <div>
    <h1>{{ msg }}</h1>
    <p>
      Application Opening Timer: {{ timer }} in Sec
    </p>
    <div id="two-way-binding">
  <p> Hello {{ name }}!</p>
  <input id=user-name v-model="name" placeholder="User Name"/>
  </div>
<div id="conditional-rendering" class="dynamic">
<button v-on:click="userCheck($event)">Security Check</button>
<div id="rendering" v-if="securety" class="dynamic">
  <SecurityTag :name="name"/>
  </div>
</div>
  <span v-bind:title="message">
    Hover your mouse over me for a few seconds to see Date & Time
  </span>
  <button v-on:click="reverseMessage">Date & Time in Reverse</button>
</div>
 
</template>

<script>

import SecurityTag from './SecurityTag.vue'

export default {
  data() {
    return {
      securety:false,
      timer: 0,
       message: 'Current Date with Time ' + new Date().toLocaleString(),
       name:"Bala"       
    }
  },
  mounted() {
    setInterval(() => {
      this.timer++
    }, 1000)
  },
  methods: {
    reverseMessage() {
      this.message = this.message
        .split('')
        .reverse()
        .join('')
    },
    userCheck(e) {
      if(e.target.innerText==="Security Uncheck"){
        this.securety=false;
        e.target.innerText="Security Check"
      }else{
this.securety=true;
        e.target.innerText="Security Uncheck"
      }
    }
  },
  name: 'DemoHome',
  components: {
    SecurityTag
  },
  props: {
    msg: String
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.demo {
    font-family: sans-serif;
  border: 1px solid #eee;
  border-radius: 2px;
  padding: 20px 30px;
  margin-top: 1em;
  margin-bottom: 40px;
  user-select: none;
  overflow-x: auto;
}
.dynamic {
    font-family: sans-serif;
  border: 1px solid #eee;
  border-radius: 2px;
  padding: 20px 30px;
  margin-top: 1em;
  margin-bottom: 2px;
  user-select: none;
  overflow-x: auto;
}
</style>
