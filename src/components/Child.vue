<template>
<h1>hoiiiiiiiiiiiiiiiiiiiiiiiiiii</h1>
<h2>{{email}}</h2>
<button type='button' v-on:click="test()" > Child buttton</button>

<h1>login and sign up page <br> raead routing in vue 3<br></h1>

</template>
<script>
 /* eslint-disable */
  export default {
    name : 'Child',
    props: {
      email: String,
      test: Function,
    }
  }
</script>

