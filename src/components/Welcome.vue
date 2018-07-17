<template>
  <section id="welcome" class="hero is-dark is-bold is-large">
     <div class="hero-body">
       <div class="container has-text-centered">
         <h1 class="title">Book App</h1>
         <h2 class="subtitle">
           <router-link to="/books">
             <button class="button">Books</button>
           </router-link>
         </h2>
       </div>
     </div>
  </section>
</template>

<script>
export default {
  name: "Welcome",
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.title {
  font-size: 3rem;
  font-family: "Lobster", cursive;
  margin-bottom: 50px;
}
</style>
