<template>
  <div class="wrapper">
    <h1
      class="animate__animated"
      @mouseover="hover = true"
      @mouseleave="hover = false"
      :class="{ animate__rotateIn: hover }"
    >
      J.P
    </h1>

    <div class="btnWrapper">
      <ul id="categoryList" @click="liClick">
        <li>Space</li>
        <li>Ocean</li>
        <li>Nature</li>
      </ul>
    </div>
    <div class="iconWrapper">
      <i class="fab fa-instagram"></i>
      <i class="far fa-envelope"></i>
    </div>
  </div>
  <Pictures :array="filterPicsArr" />
</template>

<script>
import Pictures from "./Pictures";

import ocean1 from "../assets/ocean1.jpg";
import space1 from "../assets/space1.jpg";
import nature1 from "../assets/nature1.jpg";

export default {
  components: {
    Pictures
  },

  data() {
    return {
      show: true,
      hover: false,
      typeVar: "Space",

      pictures: [
        {
          image: ocean1,
          type: "Ocean",
          alt: "Picture of Ocean"
        },
        {
          image: space1,
          type: "Space",
          alt: "Picture of Space"
        },
        {
          image: nature1,
          type: "Nature",
          alt: "Picture of Nature"
        }
      ],

      filterPicsArr: [
        {
          image: space1,
          type: "Space"
        }
      ]
    };
  },
  methods: {
    liClick(e) {
      if (e.target.id == "categoryList") {
        console.log("Ul was clicked!");
        return;
      } else {
        this.typeVar = e.target.textContent;
        this.filterPicsArr = this.pictures.filter(
          picture => picture.type == this.typeVar
        );
      }
    },

    hoverFunc(e) {
      console.log("Mouse Enter");
      e.target.classList.add("animate__rotateIn");
      console.log(e.target.classList);
    }
  }
};
</script>

<style scoped>
.wrapper {
  /* border: 1px solid black; */
  border-right: 1px solid black;
  height: 90vh;
  margin: 32px 16px;
  width: 20%;

  display: flex;
  flex-flow: column nowrap;
  align-items: center;

  font-family: "Roboto", sans-serif;

  cursor: pointer;
}

.wrapper > h1 {
  border: 2px solid black;
  padding: 24px;
  margin: 16px;
  font-size: 2.2rem;
  border-radius: 10px;
}

.btnWrapper {
  height: 50%;
  width: 80%;
  /* border: 1px solid black; */
  margin: 16px;
}

#categoryList {
  margin: 0%;
  padding: 0%;
  list-style: none;
  height: 90%;

  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: space-around;
}

#categoryList > li {
  font-size: 1.2rem;
  padding: 8px;
  margin: 16px;
  border-bottom: 2px solid black;
  width: 40%;
  text-align: center;
}

#categoryList > li:hover {
  transition: all 1s;
  width: 60%;
}

.iconWrapper {
  /* border: 1px solid black; */
  width: 80%;
  height: 25%;
  display: flex;
  align-items: flex-end;
}

.iconWrapper > i {
  font-size: 1.5rem;
  margin: 16px;
}

.active {
  background-color: green;
}
</style>
