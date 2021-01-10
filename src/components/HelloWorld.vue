<template>
  <div class="hello">
    <h1>{{ title }}</h1>

    <button @click=addName>Click me</button>
    <h2 >{{name}}</h2>

  </div>

</template>

<script>

  export default {
    name: 'HelloWorld',
    data() {
      return {
        title: 'Simple Vue.js App',
        message: "Hello",
        name: "",
        accessToken: localStorage.getItem('accessToken'),
      }
    },
    methods: {
      addName() {
     this.name = "Hello my name is Cynthia"
        return this.name;
      }
    },
    beforeCreate() {
      alert('beforCreate hook has been called');
      console.log('beforCreate hook has been called');
    },
    created() {
      console.log(this.message, 'I have just been created!')
    },
    beforeMount() {
      console.log(this.message, 'I am about to be mounted to the DOM!')
    },
    mounted() {
      this.title = "I am mounted to the DOM"
      console.log(this.message, 'I am mounted to the DOM!')
    },
    beforeUpdate() {
      console.log(this.message, 'beforeUpdate hook has been called')
    },
    updated() {
      this.title = "UPDATED"
      console.log(this.message, 'Update hook has been called')
    },
    // beforeUnmount() {
    //   console.log('beforeUnmount: ')
    // },
    // onUnmounted() {
    //   console.log('unmounted')
    // }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
