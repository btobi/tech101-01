<template>
  <div class="hello" v-bind:style="{ backgroundColor: backgroundColor }">
    <h1>{{ msg }}</h1>
    <button @click="clickButton">
      Click me
    </button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      backgroundColor: "green",
      colors: ["green", "red", "yellow", "blue"],
      currentColor: 0
    };
  },
  methods: {
    clickButton() {
      this.$emit('changeMessage', 'Hello from Child Component');
      this.backgroundColor = this.colors[
        this.currentColor++ % this.colors.length
      ];
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hello {
  background: lightgreen;
  padding: 50px;
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
  color: #42b983;
}
</style>
