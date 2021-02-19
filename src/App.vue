<template>
  <div id="app" class="p-8">
    <div class="flex justify-between items-center mb-2">
      <h1 class="text-3xl">Instructions</h1>
      <button
        @click="showInstructions = !showInstructions"
        class="bg-purple-900 rounded text-white py-2 px-6"
      >
        Toggle Instructions
      </button>
    </div>
    <div v-if="showInstructions">
      <p>
        The goal of this technical challenge is to download some user data from
        a Rest API, and display the information in an appealing way.
      </p>
      <p>
        The API Endpoint you'll be pulling data from is
        <code
          ><a href="https://jsonplaceholder.typicode.com/users" target="_blank"
            >https://jsonplaceholder.typicode.com/users</a
          ></code
        >
      </p>
      <p class="font-bold my-3">Rules</p>
      <ul class="list-disc pl-12">
        <li>
          You can use any resources you want, and look up anything you'd like.
          If you do copy a snippet of code, document where you got it from.
        </li>
        <li>
          Make sure to create an account to save a fork (Button up above) of
          this project to work on. Send a link to your forked codesandbox upon
          completion.
        </li>
      </ul>
      <p class="font-bold my-3">Here's what you need to know</p>
      <ul class="list-disc pl-12">
        <li>
          You should get the JSON API data using either the built in
          <a
            href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API"
            target="_blank"
            >Fetch library</a
          >
          or
          <a href="https://www.npmjs.com/package/axios" target="_blank"
            >Axios</a
          >
          library (Not included by default).
        </li>
        <li>
          You should present the results in a grid format, that becomes a list
          on mobile. You just need to show the users name, city, email and
          company name. Make the email a clickable
          <a
            href="https://www.w3docs.com/snippets/html/how-to-create-mailto-links.html"
            target="_blank"
            >mailto link</a
          >.
        </li>
        <li>
          The
          <a href="https://tailwindcss.com" target="_blank">Tailwindcss</a>
          library is already included in this example. You should use Tailwind
          eclusively to style the app, adding no additional CSS if possible.
        </li>
        <li>
          Change the color of the city to be red if the user is located south of
          the equator (Use the geo object's latitude property).
        </li>
        <li>
          You shouldn't have to edit this file at all, all your work will take
          place in the <code>views/ListUsers.vue</code> file and any additional
          components you choose to create.
        </li>
        <li>
          The Rest API should be queried when the component is mounted, and
          display a <code>Loading...</code> message or spinner while waiting for
          the data to load.
        </li>
        <li>
          You should also show an error message if the data can not be loaded.
          You can similate an error by changing the api endpoint from https to
          http.
        </li>
        <li>The list of users should be sorted by the users name.</li>
      </ul>
    </div>

    <div class="w-full border-8 border-dashed rounded p-8 mt-8">
      <ListUsers />
    </div>
  </div>
</template>

<script>
import ListUsers from "./views/ListUsers";

export default {
  name: "App",
  components: { ListUsers },
  data() {
    return {
      showInstructions: true,
    };
  },
};
</script>

<style>
p {
  margin-bottom: 10px;
}
code {
  padding: 3px 6px;
  background: rgb(236, 236, 236);
  border-radius: 3px;
  font-family: monospace;
  font-size: 16px;
}
a {
  color: rgb(12, 117, 143);
  text-decoration: underline;
}
</style>
