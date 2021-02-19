<template>
  <main>
    <Sidebar/>
    
  </main>
</template>

<script>
import Sidebar from "./Sidebar";


export default {
  data() {
    return {
      array: []
    }
  },
  components: {
    Sidebar
  },
  
};
</script>

<style scoped>
main {
  display: flex;
  flex-flow: row wrap;
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
</style>
