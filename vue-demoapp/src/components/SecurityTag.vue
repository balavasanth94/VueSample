<template>
<div v-if="userCheck()" class="pass">
<span>{{ name }} is valid user name</span>
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
    methods: {
    userCheck() {
        return this.name==="Bala"
    },
    emptyCheck() {
        return this.name===""
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
    font-color:green;
}
.fail{
    font-color:red;
}
.need{
    font-color:blue;
}
</style>