<template>
    <section id="books" class="has-text-centered">
        <h1 class="title">Books Section</h1>
        <div id="grid">
            <book-card v-for="book in books" :key="book.id"
            :title="book.title"
            :author="book.author"
            :cover="book.cover">
              <button class="button is-success card-footer-item" @click="edit">
                  Edit
              </button>
              <button class="button is-danger card-footer-item" @click="del">
                  Delete
              </button>
            </book-card>
        </div>
    </section>
</template>

<script>
import Card from "@/components/Card";
import apiURL from "../../api-config";

export default {
  name: "Books",
  components: {
    "book-card": Card
  },
  data() {
    return {
      books: ""
    };
  },
  methods: {
    getBooks() {
      fetch(apiURL)
        .then(res => res.json())
        .then(data => {
          this.books = data;
          console.log(this.books);
        })
        .catch(err => {
          console.log(err);
          alert("sorry something went wrong, try again");
        });
    },
    edit() {
      console.log("edit");
    },
    del() {
      console.log("delete");
    }
  },
  mounted() {
    this.getBooks();
  }
};
</script>

<style scoped>
#grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
</style>
