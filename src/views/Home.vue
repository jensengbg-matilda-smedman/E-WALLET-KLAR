<template>
  <div class="home">
    <Top />
    <h4>ACTIVE CARD</h4>
    <Card 
    :cardData="showCard" 
    />
    <CardStack 
    :cards="cards" 
    :cardInfo="cardInfo" 
    @activatecard="activateCard"/>
  </div>
</template>

<script>
import Card from '@/components/Card';
import Top from '@/components/Top';
import CardStack from '@/components/CardStack';
export default {
  name: 'Home',
  components: {
    Top,
    Card,
    CardStack
  },
data() {
    return {
      showCard: 
        {
          cardNumber: "",
          cardholderName: "",
          valid: "",
          ccv: "",
          vendor: "",
        }
    }
  },
    props: {
    cardInfo: Object,
    cards: Array
  },
  methods: {
    activateCard(card) {
      this.showCard = card
    }
  }
}

</script>

<style scoped lang="scss">

.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

  h4{
    display: flex;
    justify-content: center;
    color: gray;
  }
</style>