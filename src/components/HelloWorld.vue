
<template>
  <h1>{{ msg }}</h1>
  <form v-for="movie in movies" :key="movie.name">
    <h3>{{movie.name}}</h3>
    <button type="button" v-on:click="movie.quantity -=1" :disabled="movie.quantity <= 0">-</button>
    {{movie.quantity}}
    <button type="button" v-on:click="movie.quantity +=1" :disabled="movie.quantity >= movie.available">+</button>
  </form>
</template>

<script>
export default {
  name: 'HelloWorld',
  data (){
    return {
      movies: [
        {
          name: "Thor Love & Thunder",
          available: 8,
          quantity: 0
        },
        {
          name: "Minions",
          available: 9,
          quantity: 0
        }
      ]
    }
  },
  props: {
    msg: String    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
