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
        <Display  />
        <Footer />


      </div>
</template>

<script>

// Importing the various components that are used to render the page.
import Display from './components/Display.vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';



// Exporting the App data to main.js.
export default {
  name: 'App',
  components: {
    Display,
    Header,
    Footer
  }}


</script>

<style>
 /* Base styles for all components */
 * {
  margin: 0px;
  padding: 0px;
}
</style>
