<template>
  <div class="aboutContainer">
    <h1>About this page</h1>
    <div class="textContainer">
        <p class="subtitle">
            I made this page mainly for learning Vue 3.
        </p>
        <p class="text">
            This page also shows how a photo portfolio can look. You can change the footer and this page can be a about page.
            You can change the themes to whatever you want and change the photos. You can do a lot more! You can see my github
            for more projects i made. Also, have you tried hover over the J.P Logo up top left?
        </p>
    </div>
  </div>
  
</template>

<script>
export default {
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');

    .aboutContainer {
        min-height: 100vh;
        display: flex;
        flex-flow: column wrap;
        align-items: center;
    }

    .aboutContainer > h1 {
        margin: 38px;
        font-size: 4rem;
        font-family: 'Nunito', sans-serif;
    }

    .textContainer {
        height: 60vh;
        display: flex;
        flex-flow: column wrap;
        justify-content: center;
        align-items: center;
    }

    .textContainer > p{
        font-size: 2rem;
        width: 37%;
        margin: 16px;
        text-align: left;
    }

    @media screen and (max-width: 400px) {
        .aboutContainer {
            min-height: 100vh;
            display: flex;
            flex-flow: column wrap;
            align-items: center;
        }

        .aboutContainer > h1 {
            margin: 38px;
            font-size: 2.4rem;
            font-family: 'Nunito', sans-serif;
        }

        .textContainer > p{
            font-size: 1.2rem;
            width: 80%;
            margin: 24px;
            text-align: left;
        }
    }
</style>