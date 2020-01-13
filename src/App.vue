<template>
  <div id="app">
  <Header />
    <Lijsten v-bind:lijsten="lijsten" v-on:del-lijst="deleteLijst" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Lijsten from './components/Lijst';

export default {
  name: 'app',
  components: {
    Header,
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
          completed: false
        },
        {
          id: 3,
          name: "item 3",
          completed: false
        }

      ]
    }
  },
    methods: {
      deleteLijst(id) {
          this.lijsten = this.lijsten.filter(lijst => lijst.id !== id);
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
