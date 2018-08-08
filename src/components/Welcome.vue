<template>
  <section id="welcome">
     <div class="logo">
       <i class="fas fa-book fa-5x"></i>
     </div>
     <h1 class="heading">
       Book App
     </h1>
     <div class="book-link">
       <router-link to="/books">
         <button class="button is-primary is-large">
           Books
         </button>
       </router-link>
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
#welcome {
  background-color: #383737;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  width: 100%;
  height: 95vh;
}

.logo {
  color: #00d1b2;
}

.heading {
  font-size: 3rem;
  font-family: "Lobster", Arial, Helvetica, sans-serif;
  margin: 2rem 0.5rem;
}
</style>
