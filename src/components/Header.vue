<template>

    <!-- 
    AuthorL April Bollinger
    Date: 12/16/2021
    Program: Weather By Zip (Header.vue Component)
    Purpose: Final Exam - Demonstrate understanding of what we have learned and used over the entire semester.

    Resources:
    https://v3.vuejs.org/guide/forms.html#basic-usage
    https://www.w3schools.com/js/js_validation.asp
    https://home.openweathermap.org/api_keys
    https://www.w3schools.com/html/html_form_input_types.asp
    https://openweathermap.org/current#format
    https://www.section.io/engineering-education/how-to-interact-with-an-api-from-a-vuejs-application/
    
-->


    <!-- Title -->
    <div class="Header">
        <h1>Weather By Zip</h1>
    </div>

</template>

<script>
    // Exporting the Header Component
    export default {
        name: 'Header',

    }
</script>

<style scoped>
    /* Styles meant for the Header Component only */
    .Header {
        background-color: rgb(39, 39, 39);
        color: white;
        text-align: center;
        padding: 50px;

    }
</style>