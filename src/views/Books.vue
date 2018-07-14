<template>
    <section id="books" class="has-text-centered">
        <h1 class="title">Books Section</h1>
        <button class="button is-success" @click="isActive = true"> + Add Book</button>

        <div class="modal" :class="{'is-active': isActive}">
          <div class="modal-background"></div>
          <div class="modal-content has-background-white">

            <div id="book-form">
              <div class="field">
                <label for="title" class="label">Title</label>
                <div class="control">
                  <input type="text" name="title" class="input" placeholder="title" required v-model="title" @keyup.enter="addBook">
                </div>
              </div>

              <div class="field">
                <label for="author" class="label">Author</label>
                <div class="control">
                  <input type="text" name="author" class="input" placeholder="author" required v-model="author" @keyup.enter="addBook">
                </div>
              </div>

              <div class="field">
                <label for="cover" class="label">Cover</label>
                <div class="control">
                  <input type="url" name="cover" class="input" placeholder="cover url" v-model="cover" @keyup.enter="addBook">
                </div>
              </div>

              <div class="field">
                <div class="control">
                   <button class="button is-primary" @click="addBook">Submit</button>
                </div>
              </div>
            </div>

          </div>
          <button class="modal-close is-large" @click="close"></button>
        </div>

        <div id="grid">
            <book-card v-for="book in books" :key="book._id"
            :title="book.title"
            :author="book.author"
            :cover="book.cover">
              <button class="button is-dark card-footer-item" @click="edit">
                  Edit
              </button>
              <button class="button is-danger card-footer-item" @click="deleteBook(book)">
                  Delete
              </button>
            </book-card>
        </div>
    </section>
</template>

<script>
import Card from "@/components/Card";
import apiURL from "../../api-config";
import axios from "axios";

export default {
  name: "Books",

  components: {
    "book-card": Card
  },

  data() {
    return {
      books: "",
      isActive: false,
      title: "",
      author: "",
      cover: ""
    };
  },

  methods: {
    getBooks() {
      axios
        .get(apiURL)
        .then(res => {
          this.books = res.data;
          console.log(this.books);
        })
        .catch(err => {
          console.log(err);
          alert("sorry something went wrong, try again");
        });
    },

    addBook() {
      if (
        this.title.trim().length !== 0 &&
        this.author.trim().length !== 0 &&
        this.cover.trim().length !== 0
      ) {
        axios
          .post(apiURL, {
            title: this.title,
            author: this.author,
            cover: this.cover
          })
          .then(res => {
            console.log(res);
            this.books.push(res.data);
          })
          .catch(err => {
            console.log(err);
            alert("sorry something went wrong, try again");
          });

        this.isActive = false;
        this.title = "";
        this.author = "";
        this.cover = "";
      } else {
        alert("please fill all the fields");
      }
    },

    edit() {
      console.log("edit");
    },

    deleteBook(book) {
      console.log(book._id);
      this.books.map(i => {
        if (i._id === book._id) {
          axios
            .delete(`${apiURL}/${i._id}`)
            .then(res => {
              console.log(res);
              this.books.splice(this.books.indexOf(i), 1);
            })
            .catch(err => {
              console.log(err);
              alert("sorry something went wrong, try again");
            });
        }
      });
    },

    close() {
      this.isActive = false;
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

.modal-content {
  padding: 35px;
}
</style>
