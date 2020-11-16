<template>
  <div>
    <button type="button" class="btn btn-primary">{{ msg }}</button>
    <p>borrate pe</p>
  </div>
  
</template>
<script>
export default {
  name: 'Tablita',
  data: function() {
    return {
      msg: "Tablita"
    }
  },   
  methods: {
    getMessage: function() {
      const path = 'tabli';
      console.log(path);
    },
  },
  created: function() {
    this.getMessage();
  }, 
}
</script>
<style>
</style>