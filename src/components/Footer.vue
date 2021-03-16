<template>
  <footer>
    <div class="wrapper">
      <h2>Made by Jesper Pettersson</h2>

      <a href="https://github.com/Jesper-dev" target="_blank"
        ><i class="fab fa-github"></i
      ></a>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style scoped>
footer {
  background-color: #6b696b;
  height: 15vh;
  display: flex;
  align-items: center;
}

.wrapper > h2 {
  margin: 16px;
  color: white;
}

.wrapper {
  width: 50%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.wrapper > a {
  font-size: 4rem;
  cursor: pointer;
  color: black;
}

@media screen and (max-width: 400px) {
  .wrapper {
    width: 80%;
    justify-content: space-between;
  }

  .wrapper > h2 {
    margin: 16px;
    color: white;
    font-size: 1rem;
  }

  .wrapper > a {
    font-size: 3rem;
    cursor: none;
    color: black;
  }
}
</style>
