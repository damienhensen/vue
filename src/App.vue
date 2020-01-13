<template>
  <div id="app">
    <Lijsten v-bind:lijsten="lijsten" />
  </div>
</template>

<script>
import Lijsten from './components/Lijst';

export default {
  name: 'app',
  components: {
    Lijsten
  },
  data() {
    return {
      lijsten: [
        {
          id: 1,
          name: "item 1",
          completed: false
        },
        {
          id: 2,
          name: "item 2",
          completed: true
        },
        {
          id: 3,
          name: "item 3",
          completed: false
        }

      ]
    }
  }
}
</script>

<style>
* {
  margin: 0;
}

  /*#app {*/
/*  font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
/*  -webkit-font-smoothing: antialiased;*/
/*  -moz-osx-font-smoothing: grayscale;*/
/*  text-align: center;*/
/*  color: #2c3e50;*/
/*  margin-top: 60px;*/
/*}*/
</style>
