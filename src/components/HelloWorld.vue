
<template>
  <h1>Movies</h1>
  <form v-for="movie in movies" :key="movie.name">
    <h3>{{movie.name}}</h3>
    <picture>
      <img :src="movie.source" :alt="movie.name">
    </picture>
    <div>
      <button type="button" v-on:click="movie.quantity -=1" :disabled="movie.quantity <= 0">-</button>
      {{movie.quantity}}
      <button type="button" v-on:click="movie.quantity +=1" :disabled="movie.quantity >= movie.available">+</button>
    </div>
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
          available: 10,
          quantity: 0,
          source: require('../assets/ThorLT.png')
        },
        {
          name: "Minions",
          available: 50,
          quantity: 0,
          source: require('../assets/MinionsTheRiseofGru.png')
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2{
    border-bottom: 1px solid white;
    color: white;
    padding-bottom: 10px;
}
h3{
    color: brown;
}

form{
    background-color: gray;
    border: 1px solid white;
    border-radius: 10px;
    margin: 0 50px 25px;
    padding: 10px 25px 25px;
    text-align: center;
    transform: scale(1);
    transition: .3s transfrom;
}

form:hover{
    transform: scale(1.02);
}

button{
    background-color: rgb(103, 83, 83);
    border: 1px solid transparent;
    border-radius: 8px;
    margin: 5px;
    padding: 5px 10px;
    cursor: pointer;
    transition: border-color 0.1s;
}

button:hover{
    border-color: brown
}

button[disabled]{
    opacity: 0.5;
}

img{
    margin: 0;
    width: 200px;
    height: 200px;
    align-self: flex-start;
}
</style>
