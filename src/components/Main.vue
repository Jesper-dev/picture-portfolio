<template>
    <div class="linksWrapper">
        <div>
            <a href="#">Link1</a>
            <a href="#">Link2</a>
            <a href="#">Link3</a>
        </div>
        
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .linksWrapper{
        width: 100%;
        height: 30%;
        display: flex;
        flex-flow: row wrap;
        align-items: center;
        justify-content: center;
    }

    .linksWrapper > div{
        width: 30%;
        height: 30%;
        margin-top: 2%;

        display: flex;
        flex-flow: row wrap;
        align-items: center;
        justify-content: space-around;
    }

    .linksWrapper > div > a{
        text-decoration: none;
        border: 2px solid #a20a0a;
        border-radius: 10px;
        padding: 10px 12px;
        color: #a20a0a;
        font-size: 1.2rem;
        font-family: 'Roboto Slab', serif;
    }
</style>