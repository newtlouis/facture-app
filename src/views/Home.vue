<template>
  <div class="container">
    <div class="header">
      <div class="left">
        <h1>Factures</h1>
        <span>Il y a 4 factures</span>
      </div>
      <div class="right">
        <div class="filter" @click="filter">
          <span>Filtres:</span>
          <ul v-show="showFilter" class="filter__list">
            <li>Brouillons</li>
            <li>En cours</li>
            <li>Payées</li>
            <li>Supprimer</li>
          </ul>
        </div>
        <div @click="newInvoice" class="button">Nouvelle facture</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data(){
    return{
      showFilter : false,
    }
  },
  methods:{
    filter(){
      if (this.showFilter == false){this.showFilter = true}
      else {this.showFilter = false}
      
    }
  }
  
}
</script>

<style lang="scss" scoped>
.header{
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 900px;
  margin: 0 auto;
}
.left{
  display: flex;
  flex-direction: column;
  justify-content: end;
}
.right{
  display: flex;
  justify-content: space-between;
  width: 250px;
}
.filter{
  cursor: pointer;
}
.fliter__list{
  width: 120px;
  position: absolute;
  top: 25px;
  list-style: none;

  li{
    cursor: pointer;
    font-size: 12px;
  }
}

</style>
