<template>
  <div class="add-book-div">
    <div class="add-book-btn-div">
      <button class="add-book" v-on:click="addBookForm">Add Book</button>
    </div>

    <div class="add-book-form">
      <form v-if="formStatus" class="add-book-form" @submit.prevent="readInput">
        <table class="form-table">
          <tbody>
            <tr>
              <td align="right">Author:</td>
              <td>
                <input
                  id="input-author"
                  type="text"
                  size="30"
                  autocomplete="off"
                  v-model="author"
                  required
                />
              </td>
            </tr>
            <tr>
              <td align="right">Title:</td>
              <td>
                <input
                  id="input-title"
                  type="text"
                  size="50"
                  autocomplete="off"
                  v-model="title"
                  required
                />
              </td>
            </tr>
            <tr>
              <td align="right">Number of Pages:</td>
              <td>
                <input id="input-pages" type="number" autocomplete="off" v-model="page" required />
              </td>
            </tr>
            <tr>
              <td align="right">Read?</td>
              <td>
                <label>Yes</label>
                <input id="input-read-true" type="radio" value="true" v-model="read" />
                <label>No</label>
                <input id="input-read-false" type="radio" value="false" v-model="read" />
              </td>
            </tr>
            <tr>
              <td></td>
              <input type="submit" id="submit-btn" value="Submit" />
            </tr>
          </tbody>
        </table>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "BookForm",
  data() {
    return {
      author: "",
      title: "",
      page: null,
      read: false,
      formStatus: false
    };
  },
  methods: {
    addBookForm() {
      // Resetting the form
      this.author = "";
      this.title = "";
      this.page = null;
      this.read = false;
      this.formStatus = !this.formStatus;
    },
    readInput() {
      // Collecting user input
      let book = {
        author: this.author,
        title: this.title,
        page: this.page,
        read: this.read
      };
      // Sending data to Library
      this.$emit("book", book);
      // Resetting the form
      this.author = "";
      this.title = "";
      this.page = null;
      this.read = false;
      this.formStatus = false;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-table {
  margin: 15px auto;
}

.form-table td,
.form-table th {
  padding: 5px;
}

input[type="number"] {
  width: 60px;
}

#submit-btn {
  height: 20px;
  width: 70px;
  color: #ffa71a;
  font-weight: bold;
  border: none;
  border-radius: 5px;
  background: rgba(0, 0, 0, 0.8);
  cursor: pointer;
}

.add-book-btn-div {
  text-align: center;
  margin-top: 20px;
  margin-bottom: 20px;
}

.add-book {
  height: 20px;
  width: 100px;
  color: #ffa71a;
  font-weight: bold;
  border: none;
  border-radius: 5px;
  background: rgba(0, 0, 0, 0.8);
  cursor: pointer;
}
</style>
