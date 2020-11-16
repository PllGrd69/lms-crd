<template>
  <div class="hello">
    <div class="main">
      <h1>{{ msg }}</h1>
    <p> 
      {{ msg2 }}
      {{ message }}
  <input v-model="message">
    </p>
    <button
      type="button"
      class="btn btn-warning btn-sm"                  
      @click="editBook('hola')">
      Update
    </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function() {
    return {
      message: "Holis", num2: ""
    }
  },   
  props: {
    msg: String,
    msg2: String,
    
  },
  methods: {
    getBooks: function() {
      const path = 'Hola has create con func';
      console.log(path);
        
    },
    addBook: function(payload) {
      const path = 'http://localhost:5001/books';
      console.log(path+payload);
    },
    editBook: function(cad) {
      console.log("edit "+cad+": "+this.message);

    },
  },

  created: function() {
    this.getBooks();
  }, 

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main{
  margin: 0 auto;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #0c0c0c;
}
.hello {
color: #000000;
}
</style>