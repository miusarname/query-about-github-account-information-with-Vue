<script setup></script>

<template>
  <div class="content">
    <h1>Hello World</h1>
    <p>
      I will tell you about how this idea of creating a github account
      "consultant" came about!
    </p>
    <h2>While I was learning js?</h2>
    <p>
      I was remembering how to apply a request to an API when I was told in the
      video that I was watching that any API can be consumed with the fetch
      method (Method used to make requests to the Github API). And immediately
      it shows me the url of the Github API and at that moment I get to the
      idea. Why not create a "consultant" for github accounts?
    </p>
    <p>And so this adventure began...</p>
    <h3>As I did?</h3>
    <p>
        As you can infer after knowing the fetch method "completely" I proceeded to investigate the github api to test it with other github accounts to verify that it would work with all accounts and immediately create a project in Vue and I will show you below the step by step you do...
    </p>
    <ol>
      <li>Create a fetch with the github api base url</li>
      <li>Try it with concatenation</li>
      <li>Make the form with which you will fill a variable which will concatenate with the URL of the API</li>
      <li>Create a button (that is not send type because it reloads the page)</li>
      <li>Introduce the @click method and send it to a function </li>
      <li>The function mentioned above must have a check which will ensure that if we click on it and the input is empty, it will not send the request.</li>
      <li>The next thing is to configure the fetch in which we concatenate the basic URL of the Github API with the variable.</li>
      <li>Then we do another conditional to make sure that the query returns a user (since there will always be a "positive" or "negative" answer).</li>
      <li>And last but not least we will create the table in which we will show the information of the consulted user</li>
    </ol>
    <blockquote>
        It is worth noting that you must know something about Javascript, Html, Css and Vue to carry out this project
    </blockquote>
    <h4>How does it work?</h4>
  <p>If you read the "story" of how I got to build this page you will know otherwise I will explain...</p>
  <p>Simplemente realizo peticiones a la <strong> <a styl href="https://api.github.com/users/">API de Github</a></strong></p>
  <code>
    <h1></h1>
  </code>
  <p>Maecenas eleifend sollicitudin dui, faucibus sollicitudin augue cursus non. Ut finibus eleifend arcu ut vehicula. Mauris eu est maximus est porta condimentum in eu justo. Nulla id iaculis sapien.</p>
  </div>
</template>

<style scoped></style>
