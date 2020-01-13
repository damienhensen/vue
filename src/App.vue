<template>
  <div id="app">
    <Header />
      <AddLijsten v-on:addLijst="addLijst" />
      <Lijsten v-bind:lijsten="lijsten" v-on:del-lijst="deleteLijst" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Lijsten from './components/Lijst';
import AddLijsten from './components/layout/AddLijst';

export default {
  name: 'app',
  components: {
      Header,
      Lijsten,
      AddLijsten
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
      },
        addLijst(newLijst) {
          this.lijsten = [...this.lijsten, newLijst];
        }
    }
}
</script>

<style>
    * {
        margin: 0;
        box-sizing: border-box;
        padding: 0;
    }

    body {
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.4;
    }

    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
    }
</style>
