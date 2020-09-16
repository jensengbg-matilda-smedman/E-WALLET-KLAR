<template>
  <div id="app">
    <router-view 
    :cards="cards"
    :cardInfo="cardInfo" 
    @cardInfo="listenCard"
    @addCards="addCards"/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      cardInfo: {
        cardNumber: '',
        cardholderName: '',
        valid: '',
        ccv: '',
        vendor: '',
      },
      cards: []
    }
  }, 
  methods: {
    listenCard(value) {
      return (this.cardInfo = value), this.addCards();
    },
    addCards(){
      this.cards.push(this.cardInfo);
      localStorage.setItem('cards',JSON.stringify(this.addCards))
    }
  },
}
</script>


<style lang="scss">

</style>
