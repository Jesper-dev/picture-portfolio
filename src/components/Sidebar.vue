<template>
  <div class="wrapper" >
    <h1
      class="animate__animated"
      @mouseover="hover = true"
      @mouseleave="hover = false"
      :class="{ animate__rotateIn: hover, 'open':showNav }"
    >
      J.P
    </h1>

    <div id="navIcon" v-if="mobileView" @click="showNav = !showNav" :class="{'navIconOpen':showNav}">
        <i class="fas fa-bars"></i>
    </div>
    <!-- For Mobile -->
    <div class="btnWrapper" v-if="showNav" :class="{'navOpen':showNav}">
      <ul id="categoryList" @click="liClick" >
        <li>Space</li>
        <li>Ocean</li>
        <li>Nature</li>
      </ul>
    </div>
    <!-- For Desktop -->
    <div class="btnWrapper" v-if="!mobileView">
      <ul id="categoryList" @click="liClick" >
        <li>Space</li>
        <li>Ocean</li>
        <li>Nature</li>
      </ul>
    </div>

    <div class="iconWrapper" :class="{'open':showNav}">
      <i class="fab fa-instagram"></i>
      <i class="far fa-envelope"></i>
    </div>
  </div>
  <Pictures :array="filterPicsArr" />
</template>

<script>
import { PhotosArray } from "./Mock.js"
import Pictures from "./Pictures";

export default {
  components: {
    Pictures
  },

  data() {
    return {
      show: true,
      hover: false,
      typeVar: "Space",

      photos: PhotosArray,

      filterPicsArr: [
        PhotosArray[2],
        PhotosArray[3]
      ],
      mobileView: false,
      showNav: false
    };
  },
  methods: {
    liClick(e) {
      if (e.target.id == "categoryList") {
        return;
      } else {
        this.typeVar = e.target.textContent;
        this.filterPicsArr = this.photos.filter(
          photo => photo.type == this.typeVar
        );

        if(this.mobileView) {
          this.showNav = !this.showNav
        }
        
      }
    },
    handleView() {
      this.mobileView = window.innerWidth <= 500;
    },
    
  },
  created() {
    this.handleView()
  }
};
</script>

<style scoped>
.wrapper {
  /* border: 1px solid black; */
  border-right: 1px solid black;
  min-height: 90vh;
  margin: 32px 16px;
  width: 20%;

  display: flex;
  flex-flow: column nowrap;
  align-items: center;

  font-family: "Roboto", sans-serif;

  cursor: pointer;
}

#navIcon {
  margin: 12px;
  font-size: 2rem;
  width: 90%;
  z-index: 100;
  display: flex;
  justify-content: flex-end;
}

.navIconOpen {
  color: white;
  margin: 16px;
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

#categoryList > li.active {
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

.open {
  opacity: 30%;
}

.navOpen {
  position: absolute;
  margin-top: 24px;
  background-color: black;
  color: white;
  z-index: 50;
}

.navOpen > #categoryList > li {
  font-size: 1.4rem;
  padding: 8px;
  margin: 16px;
  border-bottom: 2px solid white;
  width: 50%;
  text-align: center;
}

@media screen and (max-width: 400px) {
  .wrapper {
    width: 100vw;
    border: none;
    min-height: 50vh;
  }

  #categoryList > li {
    font-size: 1.4rem;
    padding: 8px;
    margin: 16px;
    border-bottom: 2px solid black;
    width: 50%;
    text-align: center;
  }

  #categoryList > li:hover {
    width: 50%;
  }

  .iconWrapper > i {
    font-size: 2rem;
    margin: 16px;
  }
}


</style>
