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

  <div class="container">
    <Header />
    
    <!-- Still being weird  v-bind:desc=weather[0].description -->
    <Display    />
    <Footer />


  </div>
</template>

<script>
  // Importing the various components that are used to render the page.
  import Display from './components/Display.vue';
  import Header from './components/Header.vue';
  import Footer from './components/Footer.vue';

  // Importing axios to use for the API call.
  //import axios from 'axios';

import {zipcode, format, url1, url2, url3} from './components/Display.vue';


  // Exporting the App data to main.js.
  export default {
    name: 'App',
    components: {
      Display,
      Header,
      Footer
    },
    // Data needed for the vue components.
    data() {

      // There has to be a return statement.
      return {
        results: [],
        error: 'The zip code you entered is not valid. A zip code is typically 5 numbers long. Please try again.',
      }
    },

  methods: {
     // Mounted function that holds the API call.
    // Imperial units for F and Metric units for C.
    /*mounted() {
      axios.get().then(res => {
        this.conditions = res.data.main;
        this.weather = res.data.weather;
        this.results = res.data;
      }).catch(error => {
        console.log(error);

      });
    }
  }
  }*/

   methods: {
    async getData() {
      try {
        const response = await this.$http.get(
          url1.concat(zipcode).concat(url2).concat(format).concat(url3)
        );
        // JSON responses are automatically parsed.
        this.results = response.data;
      } catch (error) {
        console.log(error);
     }
    },
  },
},
}

</script>

<style>
  /* Base styles for all components */
  * {
    margin: 0px;
    padding: 0px;
  }
</style>