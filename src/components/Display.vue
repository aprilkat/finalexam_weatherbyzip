<template>

<!-- 
    AuthorL April Bollinger
    Date: 12/16/2021
    Program: Weather By Zip (Display.vue Component)
    Purpose: Final Exam - Demonstrate understanding of what we have learned and used over the entire semester.

    Resources:
    https://v3.vuejs.org/guide/forms.html#basic-usage
    https://www.w3schools.com/js/js_validation.asp
    https://home.openweathermap.org/api_keys
    https://www.w3schools.com/html/html_form_input_types.asp
    https://openweathermap.org/current#format
    
-->

    <div class="Display" >

        <form name="weatherform">
            <label for="zip">Zip Code</label><br>
            <input v-model="zip" type="text" id="zip" name="zip" ><br>
            <input v-model="format" type="radio" id="Fahrenheit" name="format" value="imperial">
            <label for="Fahrenheit">Fahrenheit</label><br>
            <input v-model="format" type="radio" id="Celcius" name="format" value="metric">
            <label for="Celcius">Celcius</label><br>
            <button v-on:click="mounted">Search</button>
        </form>


        <!-- Zip Code will go here -->
        <div  v-bind:zip=zip v-bind:results=results v-bind:conditions=conditions v-bind:weather=weather v-bind:temp=conditions.temp v-bind:n=results.name v-bind:desc=weather.description >
            <img src="">
            <h2>{{zip}}</h2>
            <h2> {{n}} </h2>
            <h2>Current Temperature: {{temp}} </h2>
            <!-- Still can't reach the description of the weather -->
            <h2>Current Conditions: {{decs}} </h2>
        </div>
      
        


    </div>
</template>

<script>

// Importing axios to use for the API call.
import axios from 'axios';


// Exporting the Display Component
export default {
    name: 'Display',

    // Data needed for the vue components.
  data: function() {
    // There has to be a return statement.
    return {
      results: [],
      conditions: [],
      weather: [],
      decs: '',
      zip: '',
      format: '',
      temp: '',
      n: '',
      error: 'The zip code you entered is not valid. A zip code is typically 5 numbers long. Please try again.',
  }
  },

    methods: {
        // Mounted function that holds the API call.
        // Imperial units for F and Metric units for C.
            mounted(){
            axios.get('http://api.openweathermap.org/data/2.5/weather?zip=65674,us&units=imperial&appid=d14cf5912674ad7d02026132cefa7cb2').then(res => {this.conditions = res.data.main; this.weather = res.data.weather; this.results=res.data; 
            }).catch( error => {console.log(error);});
        }}

}
 



</script>

<style scoped>
/* Styles for the Display Component */
    .Display {
        background-color: lightgray;
        color: black;
        width: 100%;
        text-align: center;
    }

    button{
        padding: 10px;
    }
</style>