<template>

  <div>
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :book="book" :key="book.id"></book-item>
    </ul>

    <book-form @addBook='appendBook'></book-form>
  </div>

</template>

<script>

  import BookItem from './BookItem';
  import BookForm from './BookForm';

  export default {
    name: "BookList",
    components: {BookItem, BookForm},
    methods:{
      appendBook(bookTitle, bookAuthor){
        this.books.push({title: bookTitle, author: bookAuthor});
      }
    },
    data() {
      return {
        title: "All Books",
        books: [
          {id:0, title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
          {id:1, title: 'American Gods', author: 'Neil Gaiman'},
          {id:2, title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
        ]
      }
    }
  }
</script>

<style scoped>

  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

</style>
