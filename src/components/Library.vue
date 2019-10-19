<template>
  <div class="main-container">
    <div class="table-container">
      <table class="library">
        <thead>
          <tr>
            <td>Author</td>
            <td>Title</td>
            <td>Page Count</td>
            <td>Read?</td>
            <td></td>
          </tr>
        </thead>
        <tr v-for="(data, index) in library" v-bind:key="index">
          <td>{{ data.author }}</td>
          <td>{{ data.title }}</td>
          <td align="center">{{ data.page }}</td>
          <td>
            <label class="switch">
              <input type="checkbox" v-bind:checked="data.read" />
              <span class="slider"></span>
            </label>
          </td>
          <td>
            <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
          </td>
        </tr>
      </table>
    </div>

    <BookForm @book="addBook" />
  </div>
</template>

<script>
import BookForm from "./BookForm.vue";
export default {
  name: "Library",
  components: {
    BookForm
  },
  data() {
    return {
      author: "",
      title: "",
      page: null,
      read: false,
      library: [
        {
          index: 1,
          author: "Charles Dickens",
          title: "Great Expectation",
          page: 544,
          read: true
        },
        {
          index: 2,
          author: "Harper Lee",
          title: "To Kill a Mockingbird",
          page: 296,
          read: true
        },
        {
          index: 3,
          author: "George Orwell",
          title: 1984,
          page: 328,
          read: false
        },
        {
          index: 4,
          author: "F. Scott Fitzgerald",
          title: "The Great Gatsby",
          page: 218,
          read: true
        }
      ]
    };
  },
  methods: {
    addBook(variable) {
      this.library.push(variable);
    },
    remove(id) {
      this.library.splice(id, 1);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css";

.table-container table {
  margin-left: auto;
  margin-right: auto;
  background-color: white;
  border: 3px solid black;
}

.table-container table,
.library td,
.library th {
  border-collapse: collapse;
  padding: 15px;
}

.library thead {
  text-align: center;
  font-weight: bold;
  background-color: black;
  color: #ffa71a;
}

.library tr:nth-child(even) {
  background-color: #585858;
}

/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 50px;
  height: 22px;
  padding-top: 3px;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider background*/
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgb(182, 182, 182);
  -webkit-transition: 0.2s;
  transition: 0.2s;
  border-radius: 15px;
}

/* The slider button */
.slider:before {
  position: absolute;
  content: "";
  height: 19px;
  width: 19px;
  left: 4px;
  bottom: 3px;
  background-color: black;
  -webkit-transition: 0.2s;
  transition: 0.2s;
  border-radius: 15px;
}

input:checked + .slider {
  background-color: #ffa71a;
}

input:checked + .slider:before {
  -webkit-transform: translateX(23px);
  -ms-transform: translateX(23x);
  transform: translateX(23px);
}

i {
  font-size: 20px;
  cursor: pointer;
}
</style>
