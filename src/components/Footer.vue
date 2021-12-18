<template>

<!-- 
    AuthorL April Bollinger
    Date: 12/16/2021
    Program: Weather By Zip (Footer.vue Component)
    Purpose: Final Exam - Demonstrate understanding of what we have learned and used over the entire semester.

    Resources:
    https://v3.vuejs.org/guide/forms.html#basic-usage
    https://www.w3schools.com/js/js_validation.asp
    https://home.openweathermap.org/api_keys
    https://www.w3schools.com/html/html_form_input_types.asp
    https://openweathermap.org/current#format
    https://www.section.io/engineering-education/how-to-interact-with-an-api-from-a-vuejs-application/
    
-->


    <div class="Footer">
        <p>&copy; April Bollinger</p>
    </div>
</template>

<script>
// Exporting the Footer Component
    export default {
        name: 'Footer',
        }
</script>

<style scoped>
/* Style intended for the footer element and only that element. */
    .Footer {
        background-color: rgb(2, 168, 2);
        color: white;
        text-align: center;
        position: fixed;
        bottom: 0;
        width: 100%;
        padding: 15px;
    }
</style>