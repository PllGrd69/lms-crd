<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-10">
        <h1>Persons</h1>
        <hr />
        <br /><br />
        <alert :message="message" v-if="showMessage"></alert>
        <br /><br />
        <table class="table table-hover table-striped">
          <thead class="thead-dark">
            <tr>
              <th scope="col">#</th>
              <th scope="col">Name</th>
              <th scope="col">Age</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(d, index) in list" :key="index">
              <td>{{ d.ID }}</td>
              <td>{{ d.Name }}</td>
              <td>{{ d.Age }}</td>

              <td>
                <div class="btn-group" role="group">
                  <button
                    type="button"
                    class="btn btn-warning btn-sm"
                    @click="edit(d.ID)"
                  >
                    Update
                  </button>
                  <button
                    type="button"
                    class="btn btn-danger btn-sm"
                    @click="onDelete(d)"
                  >
                    Delete
                  </button>
                </div>
              </td>
            </tr>
          </tbody>
          <button type="button" class="btn btn-success btn-sm " v-on:click="add()">
          Add Person
        </button>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Alert from "./Alert.vue";

export default {
  name: "Person",
  data: function () {
    return {
      list: [],
      message: "",
      showMessage: false,
    };
  },
  components: {
    alert: Alert,
  },
  methods: {
    edit: function (id) {
      this.$router.push("/persons/form/" + id);
    },
    add: function () {
      this.$router.push("/persons/form");
    },
    getList: function () {
      const path = "http://localhost:8085/v1/persons";
      axios
        .get(path)
        .then((res) => {
          this.list = res.data.r;
        })
        .catch((error) => {
          console.error(error);
        });
    },
    onDelete: function (d) {
      this.delete(d.ID);
    },
    delete: function (id) {
      const path = `http://localhost:8085/v1/persons/${id}`;
      axios
        .delete(path)
        .then(() => {
          this.getList();
          this.message = "Eliminado!";
          this.showMessage = true;
        })
        .catch((error) => {
          console.error(error);
          this.getList();
        });
    },
  },

  created: function () {
    this.getList();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
  color: #42b983;
}
.hello {
  color: #42b983;
}
</style>