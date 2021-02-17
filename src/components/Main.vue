<template>
  <main>
    <Sidebar />
    <!-- <div class="linksWrapper">
      <div >
        <button @click="handleClick">Ocean</button>
        <button @click="handleClick">Space</button>
        <button @click="handleClick">Nature</button>
      </div>
    </div> -->


    <!-- <div class="imageWrapper">
      <img v-for="(pic, index) in filterPicsArr" :key="index" :src="pic.image"  />
    </div> -->
  </main>
</template>

<script>
import ocean1 from "../assets/ocean1.jpg";
import space1 from "../assets/space1.jpg";
import nature1 from "../assets/nature1.jpg";

import Sidebar from "./Sidebar"


export default {
  components: {
    Sidebar
  },
  data() {
    return {
      pictures: [
        {
          image: ocean1,
          type: "Ocean"
        },
        {
          image: space1,
          type: "Space"
        },
        {
          image: nature1,
          type: "Nature"
        }
      ],

      typeVar: "Space",

      filterPicsArr: [{
          image: space1,
          type: "Space"
        },]
    };
  },

  methods: {
    handleClick(e) {
        this.typeVar = e.target.textContent
        this.filterPicsArr = this.pictures.filter((picture) => picture.type == this.typeVar)
    }
  },
};
</script>

<style scoped>

main {
  height: 100vh;
  /* display: flex;
  flex-flow: column wrap; */
}

.imageWrapper {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  width: 100%;
  margin-top: 5%;
}

img {
  max-width: 400px;
  border: 2px solid #a20a0a;
}


/* .linksWrapper {
  width: 100%;
  height: 10%;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: center;
}

.linksWrapper > div {
  width: 30%;
  height: 30%;
  margin-top: 2%;

  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: space-around;
}

.linksWrapper > div > button {
  text-decoration: none;
  border: 2px solid #a20a0a;
  background: none;
  cursor: pointer;
  outline: none;
  border-radius: 10px;
  padding: 10px 12px;
  color: #a20a0a;
  font-size: 1.2rem;
  font-family: "Roboto Slab", serif;
} */

</style>
