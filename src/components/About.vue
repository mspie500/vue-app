<template>
  <div id="about" class="card px-3 mt-5 bg-dark text-white shadow">
    <h2 class="text-center my-4 border-bottom pb-3">About</h2>
    <div class="row">
      <div class="col-md-6 p-3">
        <h3 class="border-bottom text-center mb-3 pb-3">This Page</h3>
        <p class="px-3">This page is a simple employee database Vue application. To build this i followed this example:</p>
        <p><a href="https://www.taniarascia.com/getting-started-with-vue/" title="link to tutorial" class="px-3">Getting Started with Vue - An Overview and Walkthrough Tutorial</a></p>
        <p class="px-3">This tutorial helped me learn how to work with data, methods, conditional statements, and events in Vue to create, update, view and delete employees from an external server.</p>
      </div>
      <div class="col-md-6 p-3">
        <h3 class="border-bottom text-center mb-3 pb-3">Vue.js</h3>
        <p class="px-3">Vue (pronounced /vjuː/, like view) is a progressive framework for building user interfaces. It is designed from the ground up to be incrementally adoptable, and can easily scale between a library and a framework depending on different use cases. It consists of an approachable core library that focuses on the view layer only, and an ecosystem of supporting libraries that helps you tackle complexity in large Single-Page Applications.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'about'
}
</script>

<style scoped>

</style>