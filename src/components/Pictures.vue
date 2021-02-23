<template>
  <div class="container">
    <p @click="prev">{{ arrowLeft }}</p>
    <div
      class="imageContainer"
      v-for="(i, index) in [currentIndex]"
      :key="index"
    >
      <img :src="currentImage.image" />
    </div>
    <p @click="next">{{ arrowRight }}</p>
  </div>
</template>

<script>
export default {
  props: ["array"],
  data() {
    return {
      typeVar: "Space",

      arrowLeft: "<",
      arrowRight: ">",
      timer: null,
      currentIndex: 0
    };
  },
  mounted() {
    console.log(this.array);
  },

  methods: {
    startSlide() {
      this.timer = setInterval(this.next, 4000);
    },
    next() {
      this.currentIndex += 1;
    },
    prev() {
      this.currentIndex -= 1;
    }
  },
  computed: {
    currentImage() {
      return this.array[Math.abs(this.currentIndex) % this.array.length];
    }
  }
};
</script>

<style scoped>
.container {
  width: 75%;
  min-height: 90vh;
  margin: 32px 16px;

  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  align-items: center;
}

p {
  font-size: 4rem;
  cursor: pointer;
  margin: 24px;
  font-weight: bold;
}

.imageContainer {
  width: 70%;
  height: 75%;

  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  justify-content: center;
}

.imageContainer > img {
  border: 3px solid #000;
  max-width: 100%;
  max-height: 100%;
}

@media screen and (max-width: 400px) {
  .container {
    width: 100vw;
    min-height: 10vh;
  }

  .imageContainer {
    min-width: 75%;
    margin-bottom: 48px;
  }

  p {
    font-size: 3rem;
    margin: 24px;
    margin-bottom: 48px;
    font-weight: bold;
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
