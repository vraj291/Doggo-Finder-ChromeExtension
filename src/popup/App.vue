<template>  
  <div>
    <Title />
    <Dog />
  </div>
</template>

<script>
import Title from '@/components/Title.vue'
import Dog from '../components/Dog.vue'

export default {
  name: 'App',
  components: {
    Title,
    Dog
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Titillium+Web&display=swap');

html {
  width: 470px;
  height: 400px;
  background-color: rgb(61, 63, 60);
  color: rgb(241, 86, 13);
}

body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
