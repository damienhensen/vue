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
// import axios from 'axios';

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
          title: "Love Beam",
          author: "Agrume",
          duration: 389,
          uploadDate: "09-09-2017",
          link: "https://www.youtube.com/watch?v=Xo6IEkEy0CE&list=PLOqRcjUsSErY0OBK9QqfFhJ5GHyuiKBWS&index=1",
          thumbnail: "https://i.ytimg.com/vi/Xo6IEkEy0CE/hqdefault.jpg"
        },
        {
          id: 2,
          title: "dancing all night",
          author: "android52",
          duration: 239,
          uploadDate: "10-21-2015",
          link: "https://www.youtube.com/watch?v=zJtGnnhYZOo&list=PLOqRcjUsSErY0OBK9QqfFhJ5GHyuiKBWS&index=2",
          thumbnail: "https://i.ytimg.com/vi/zJtGnnhYZOo/hqdefault.jpg"
        },
        {
          id: 3,
          title: "Big Yoshi's Lounge",
          author: "KryptoDigital",
          duration: 194,
          uploadDate: "02-17-2019",
          link: "https://www.youtube.com/watch?v=zbc2LUAP6G4&list=PLOqRcjUsSErY0OBK9QqfFhJ5GHyuiKBWS&index=3",
          thumbnail: "https://i.ytimg.com/vi/zbc2LUAP6G4/hqdefault.jpg"
        },
        {
          id: 4,
          title: "crystal dolphin",
          author: "engelwood",
          duration: 113,
          uploadDate: "02-23-2018",
          link: "https://www.youtube.com/watch?v=4hdKXr8wGrk&list=PLOqRcjUsSErY0OBK9QqfFhJ5GHyuiKBWS&index=4",
          thumbnail: "https://i.ytimg.com/vi/4hdKXr8wGrk/hqdefault.jpg"
        },
        {
          id: 5,
          title: "Fodlan Winds (Rain)",
          author: "Takeru Kanazaki, Rei Kondoh and Hiroki Morishita",
          duration: 165,
          uploadDate: "12-21-2019",
          link: "https://www.youtube.com/watch?v=YA2P8o07SKQ&list=PLOqRcjUsSErY0OBK9QqfFhJ5GHyuiKBWS&index=5",
          thumbnail: "https://i.ytimg.com/vi/YA2P8o07SKQ/hqdefault.jpg"
        },
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
  },
  // created() {
  //   axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
  //           .then(res => this.lijsten = res.data);
  // }
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
