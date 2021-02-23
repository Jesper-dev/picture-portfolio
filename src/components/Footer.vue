<template>
  <footer>
      <div class="wrapper">
        <h2>Made by Jesper Pettersson</h2>
    
       <a href="https://github.com/JesperKYH" target="_blank"><i class="fab fa-github"></i></a> 
    </div>
  </footer>
</template>

<script>
export default {

}
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
        opacity: 50%;
    }

    .wrapper {
        width: 50%;
        display: flex;
        justify-content: space-between;
    }

    .wrapper > a {
        font-size: 4rem;
        cursor: pointer;
        color: black;
    }
</style>