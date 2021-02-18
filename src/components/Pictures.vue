<template>
  <div class="container">
    <p>{{ arrowLeft }}</p>
    <div class="imageContainer">
      <img v-for="(pic, index) in array" :key="index" :src="pic.image" :alt="pic.alt"
      />
    </div>
    <p>{{ arrowRight }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      typeVar: "Space",

      arrowLeft: "<",
      arrowRight: ">"
    };
  },
  props: ["array"]
};
</script>

<style scoped>
.container {
  width: 75%;
  height: 90vh;
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
</style>
