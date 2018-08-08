<template>
    <article class="card">
        <header class="card-header">
            <p class="card-header-title">
                {{title}}
            </p>
        </header>
        <div class="card-content">
            <div class="content">
                <div class="card-image">
                    <img onerror="this.onerror = null; this.src = 'https://tinyurl.com/ybloln78'" :src="cover" alt="book cover">
                </div>
                <h2 class="subtitle">{{author}}</h2>
            </div>
        </div>
        <footer class="card-footer">
            <slot/>
        </footer>
    </article>
</template>

<script>
export default {
  name: "Card",
  props: {
    title: {
      type: String,
      required: true
    },
    author: {
      type: String,
      required: true
    },
    cover: {
      type: String,
      required: true
    }
  }
};
</script>

<style scoped>
.card {
  max-width: 400px;
  max-height: 500px;
  margin: 30px;
  border-radius: 10px;
  overflow: hidden;
}

img {
  display: block;
  max-width: 100%;
  max-height: 300px;
  margin: 10px auto;
}

.card-content {
  background-color: #eee;
}

.card-footer-item {
  padding: 5px;
}
</style>
