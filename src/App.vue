<template>

  <!-- 
    AuthorL April Bollinger
    Date: 12/16/2021
    Program: Weather By Zip (App.vue Component)
    Purpose: Final Exam - Demonstrate understanding of what we have learned and used over the entire semester.

    Resources:
      https://v3.vuejs.org/guide/forms.html#basic-usage
      https://www.w3schools.com/js/js_validation.asp
      https://home.openweathermap.org/api_keys
      https://www.w3schools.com/html/html_form_input_types.asp
      https://openweathermap.org/current#format
      


    Example API call provided:
      api.openweathermap.org/data/2.5/weather?zip={zip code},{country code}&appid={API key}
-->

  <div class="container" v-bind:results=results v-bind:conditions=conditions v-bind:outside=outside >
    <Header />

    <!-- Still being weird  v-bind:desc= -->

    <h2><input v-model="zip" type="text" id="zip" name="zip"> <br> {{zip}} </h2>
    <input v-on:click='changeFormatF' type="radio" id="F" name="format" value="imperial">
    <label for="Fahrenheit">Fahrenheit</label><br>
    <input v-on:click='changeFormatC' type="radio" id="C" name="format" value="metric">
    <label for="Celcius">Celcius</label><br>
    <button v-on:click="changeZip">Search</button>

    <h2> {{results.name}} </h2>
    <h2>Current Temperature: {{conditions.temp}} </h2>
    <!-- Still can't reach the description of the weather -->
    <h2>Current Conditions: {{outside[0].description}} </h2>

    <Footer />


  </div>
</template>

<script>
  // Importing the various components that are used to render the page.
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';

  import axios from 'axios';

// Declaring the other variables
  var url1 = 'http://api.openweathermap.org/data/2.5/weather?zip=';
  var url2 = ',us&units=';
  var url3 = '&appid=d14cf5912674ad7d02026132cefa7cb2';
  var format = 'imperial';
  var zipcode = ''



  // Exporting the App data to main.js.
  export default {
    name: 'App',
    components: {
      // Display,
      Header,
      Footer
    },
    // Data needed for the vue components.
    data() {

      // There has to be a return statement.
      return {
        results: [],
        conditions: [],
        outside: [],
        zip: '65674',
        error: 'The zip code you entered is not valid. A zip code is typically 5 numbers long. Please try again.',
      }
    },

    methods: {
      getData() {
      
          axios.get(url1.concat(zipcode).concat(url2).concat(format).concat(url3)).then(
        (response) => {
            this.results = response.data;
            this.conditions = response.data.main;
            this.outside = response.data.weather;

            console.log(this.results);
        },
        (error) => {
            console.log(error);
        }
    );
},


    created() {
      this.getData();
    },
  

    changeFormatF() {
      format = 'imperial';
    },
    changeFormatC() {
      format = 'metric';
    },

    changeZip() {
      zipcode = document.getElementById('zip').value;
      this.getData();

    },
    }}

</script>

<style>
  /* Base styles for all components */
  * {
    margin: 0px;
    padding: 0px;
    text-align: center;

  }

  
</style>