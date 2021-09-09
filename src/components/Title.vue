<template>
  <div>
    <p>Lets get you A GOOD BOY</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  mounted () {
    browser.runtime.sendMessage({})
  }
}
</script>

<style scoped>
p {
  font-size: 1.5rem;
  text-align: center;
  letter-spacing: 1px;
  font-family: 'Titillium Web', sans-serif;
}
</style>
