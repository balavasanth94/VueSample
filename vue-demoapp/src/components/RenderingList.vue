<template>
    <div id="conditional-rendering" class="demo">
        <span v-if="seen">Now you see me</span>
    </div>
</template>

<script>

const ConditionalRenderingApp = {
  data() {
    return {
      seen: true
    }
  }
}

Vue.createApp(ConditionalRenderingApp).mount('#conditional-rendering')
</script>

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
</style>>