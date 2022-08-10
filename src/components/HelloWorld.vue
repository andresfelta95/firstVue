
<template>
  <h2>Movies</h2>
  <form v-for="movie in movies" :key="movie.name">
    <h3>{{movie.name}}</h3>

    <picture>
      <img :src="movie.source" :alt="movie.name">
    </picture>

    <p> Lenght : {{movie.length}}</p>

    <div>
      <button type="button" v-on:click="movie.quantity -=1" :disabled="movie.quantity <= 0">-</button>
      {{movie.quantity}}
      <button type="button" v-on:click="movie.quantity +=1" :disabled="movie.quantity >= movie.available">+</button>
    </div>
    
    <a :href="movie.trailer" target="_blank">▶️ Trailer</a>
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
          source: require('../assets/ThorLT.png'),
          length: "1h 59min",
          trailer: 'https://youtu.be/Go8nTmfrQd8'
        },
        {
          name: "Minions",
          available: 5,
          quantity: 0,
          source: require('../assets/MinionsTheRiseofGru.png'),
          length: "1h 27min",
          trailer: 'https://youtu.be/6DxjJzmYsXo'
        },
        {
          name: "DC League of Super-Pets",
          available: 8,
          quantity: 0,
          source: require('../assets/DCLeague.png'),
          length: "1h 45min",
          trailer: 'https://youtu.be/1jkw2JPCl18'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

h3{
    color: brown;
}

form{
    background-color: black;
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
    font-size: large;
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
