<template>
  <div class="container">
    <div class="row mt-3">
    <div class="card col-md-4">
    <div class="card-header">
      Ping 1
    </div>
    <div class="card-body">
      <h5 class="card-title">{{ msg }}</h5>
    </div>
  </div>
    <div class="card col-md-4">
    <div class="card-header">
      Ping 2
    </div>
    <div class="card-body">
      <h5 class="card-title">{{ msg }}</h5>
    </div>
    </div>
  </div>
  </div>
</template>
<script>
import axios from 'axios';

export default {
  name: 'Ping',
  data: function() {
    return {
      msg: "ping"
    }
  },   
  methods: {
    getMessage: function() {
      const path = 'http://localhost:8085/v2/ping';
      axios.get(path)
        .then((res) => {
          this.msg = res.data;
        })
        .catch((error) => {
          // eslint-disable-next-line
          console.error(error);
        });
    },
  },
  created: function() {
    this.getMessage();
  }, 
}
</script>