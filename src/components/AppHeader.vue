<template>
    <nav class="navbar is-primary">
        <div class="navbar-brand">
            <a href="#" class="navbar-item" aria-label="menu" aria-expanded="false">
                <strong>BookApp</strong>
                <i class="fas fa-book logo"></i>
            </a>
            <a class="navbar-burger" role="button" @click="isActive = !isActive">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>
        <div class="navbar-menu navbar-end" :class="{'is-active': isActive}">
            <router-link class="navbar-item" to="/" >Home</router-link>
            <router-link class="navbar-item" to="/books" >Books</router-link>
            <router-link class="navbar-item" to="/about" >About</router-link>
        </div>
    </nav>
</template>

<script>
export default {
  name: "AppHeader",
  data() {
    return {
      isActive: false
    };
  }
};
</script>

<style scoped>
.navbar-brand {
  font-family: "Lobster", sans-serif, cursive;
  font-size: 25px;
}

.logo {
  padding: 0 10px;
}
</style>
