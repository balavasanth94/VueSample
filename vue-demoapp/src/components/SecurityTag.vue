<template>
<div v-if="userCheck()" class="pass">
<span>{{ name }} is valid user name  </span>
<button v-on:click="userList($event)">Show User List</button>
<div id="list-rendering" v-if="list">
    <ol>
  <li v-for="user in userlist" v-bind:key="user">
      {{ user.name }}
    </li>
    </ol>
</div>

</div>
<div v-else>
<div v-if="emptyCheck()" class="need">
<span>User Name is Empty. Please enter the valid user name</span>
</div>
<div v-else class="fail">
<span>{{ name }} is invalid user name. Security Alert!!! 
Please enter the valid user name
</span>
</div>
</div>
</template>

<script>
export default {
    data() {
    return {
        list:false,
      userlist: [
        { name: 'Bala' },
        { name: 'Vasanth' },
        { name: 'Dinsh' }
      ]
    }
  },
    methods: {
    userCheck() {
        return this.name==="Bala"
    },
    emptyCheck() {
        return this.name===""
    },
    userList(e){
      if(e.target.innerText==="Show User List"){
        this.list=true;
        e.target.innerText="Hide User List"
      }else{
        this.list=false;
        e.target.innerText="Show User List"
      }
    }
  },
name: 'SecurityTag',
props: {
    name: String
  }
}
</script>


<style scoped>
.pass{
    color:green;
}
.fail{
    color:red;
}
.need{
    color:blue;
}
</style>