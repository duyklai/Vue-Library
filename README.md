# Library: with Vue

This is a basic "display" project using Vue. Goal is to create a "library" where user can add a book (author, title, number of pages, and read or not) to a list. The library will display said information and features a slider bar as a read/not read check for the user. User can also choose to delete books on the list. Below the list is the "Add Book" button which will create a form and allow user to enter information on new books to add to the list. The form features basic validation (required to be filled) with the expection of "read" property, which is false by default. Currently, it does not have any storage capability and will reset on refresh.

![alt text](https://github.com/duyklai/Vue-Library/blob/master/src/img/VueLibrary.png 'Demo Library')

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
