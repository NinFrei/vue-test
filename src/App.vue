<template>
  <div id="app">
    <p :style="{ backgroundColor: primaryColor }">{{ firstName }}</p>
    <p :style="primaryStyling">{{ firstName }}</p>
    <p :style="{ color: 'red', backgroundColor: 'pink' }">{{ age }}</p>
    <label>
      What is your name ?
      <input v-model="name" />
    </label>
    <p>Hello {{ name }} !</p>

    <h1>Icecream store</h1>

    <label>Quantity: <input type="number" /></label>
    <br />
    <label
      >Size:
      <select>
        <option value="100">Small</option>
        <option value="150">Medium</option>
        <option value="200">Giant</option>
      </select>
    </label>
    <br />
    <label>Flavour:</label>
    <label><input type="radio" name="flavour" value="#F3E5AB" />Vanilla</label>
    <label
      ><input type="radio" name="flavour" value="#5B2F00" />Chocolate</label
    >
    <label
      ><input type="radio" name="flavour" value="#DE0934" />Strawberry</label
    >

    <label><input type="checkbox" /> Napkin</label>
    <br />
    ________________________________________________________________________
    <div>
      <input type="range" min="0" max="40" v-model="temp" />
      {{ temp }} °C
      <span v-if="temp > 30">🥵</span>
      <span v-else-if="temp < 10">🥶</span>
      <span v-else>😀</span>
    </div>
    <br />___________________________________________________________________

    <input v-model="number" type="text" />

    <select v-model="number">
      <option value="45">45</option>
      <option value="50">50</option>
      <option value="55">55</option>
    </select>
    _____________________________________________________________________
    <br />
    <br />
    <h2 v-if="number > 50">number is greater than 50</h2>
    <h2 v-else-if="number < 50">number is smaller than 50</h2>
    <h2 v-else>number is equal 50</h2>
    <br />

    <button @click="inStock = !inStock">Toggle</button>
    <p v-if="inStock">There is one grill left! Hurry up!</p>
    <p v-else>Oh no 😢 no BBQ for Opportunity</p>

    <!--methods-->
    <button @click="gruezi()">Begrüssen</button>

    <h3>Colourful World</h3>

    <img v-bind:src="" :width="logoWidth"/>
<br>
<br>
    <button @click="greet">Greet</button>
  </div>
</template>




<script>
export default {};
</script>


<script>
export default {
  name: "App",
  data() {
    return {
      lastName: "Freiman",
      firstName: "Nina",
      age: "12",
      imgLink: require("../src/assets/logo.png"),
      logoWidth: 100,
      primaryColor: "purple",
      primaryStyling: "white",
      color: "yellow",
      backgroundColor: "blue",
      quantity: 1,
      flavour: "#5B2F00",
      temp: 20,
      inStock: false,
      number: 55,
      name: "Mark"
    };
  },
  methods: {
    gruezi: function () {
      alert( 'Hallo' +' '+ this.firstName +' '+ this.lastName);
      }
    },


    greet: function(event) {
// 'this' refers to the view instance
this.say("Hi " + this.name);
    },
      say(message) {
        // if a method is independent of the instance (no reference to 'this')
        //then it could be relevant to move it to move it to a separate module
        alert(message + "!");
        
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
label {
  display: block;
}
</style>
