<template>
  <div class="about">
    <h1 class="heading">About</h1>
    <p class="info">
      <em> "Book App" </em> is a simple app for storing books information. Its like your personal collection of books.
    </p>
    <footer>
      Copyright &copy; 2018 Vaibhav Yadav
    </footer>
  </div>
</template>

<style scoped>
.about {
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

.heading {
  font-size: 3rem;
  font-family: "Lobster", Arial, Helvetica, sans-serif;
  padding: 1rem;
}

.info,
footer {
  font-size: 1.1rem;
  font-family: Arial, Helvetica, sans-serif;
  padding: 1rem;
}
</style>
