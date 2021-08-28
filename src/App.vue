<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <FactureModel/>
  <router-view/>
</template>

<script>
import FactureModel from "./components/FactureModel.vue"
export default {
  components:{
    FactureModel
  }
}
</script>

<style lang="scss">


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  margin: 0;
  padding: 0;
  box-sizing: border-box;

}

button{
  cursor: pointer;
  padding: 16px 24px;
  border-radius: 30px;
  border: none;
  font-size: 12px;
  color: #FFF;
}

// COULEUR
.dark-purple{
  background-color: #252945;
}
.purple{
  background-color: #7c5dfa;
}

.green{
  background-color: #33d69f;
}

.orange{
  background-color:#ff8f00;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
