<template>
  <div class="wrapper">
    <h1>J.P</h1>
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
</template>

<script>
export default {
    methods: {
        liClick (e) {
            if(e.target.id == "categoryList"){
                console.log("Ul was clicked!")
                return;
            } else {
                console.log(e.target.textContent)
            }          
        }
    }
};
</script>

<style scoped>
.wrapper {
  /* border: 1px solid black; */
  border-right: 1px solid black;
  height: 90vh;
  margin: 16px;
  margin-top: 32px;
  width: 20%;

  display: flex;
  flex-flow: column nowrap;
  align-items: center;

  font-family: 'Roboto', sans-serif;
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
    cursor: pointer;
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
    cursor: pointer;
}
</style>