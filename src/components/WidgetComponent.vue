<template>
    <div>
        <button @click="toggleFold">{{ isFolded ? 'Spread' : 'Fold' }}</button>
        <div class="cards-container" :class="{ folded: isFolded }">
          <div class="card" v-for="(card, index) in cards" :key="index" v-show="!isFolded || currentCard === index">
           <h3>{{ card.title }}</h3>
           <p>{{ card.content }}</p>
          </div>
        </div>

        <div v-if="isFolded" class="arrows">
          <button @click="prevCard">&#8592;</button>
          <button @click="nextCard">&#8594;</button>
        </div>
    </div>
</template>

<script>
  export default {
    data() {
        return {
            isFolded: false,
            currentCard: 0,
            cards: [
                { title: 'Card 1', content: 'Content for card 1' },
                { title: 'Card 2', content: 'Content for card 2' },
                { title: 'Card 3', content: 'Content for card 3' },
            ],
        };
     },
     methods: {
        toggleFold() {
            this.isFolded = !this.isFolded;
        },
        prevCard() {
            this.currentCard = this.currentCard > 0 ? this.currentCard - 1 : this.cards.length - 1;
        },

        nextCard() {
            this.currentCard = this.currentCard < this.cards.length - 1 ? this.currentCard + 1 : 0;
        }


     }
  }
</script>

<style scoped>
.cards-container {
   display: flex;
   justify-content: space-between;
   transition: all 0.5s ease; 
}

.cards-container.folded {
  flex-direction: column;
  align-items: center;
}

.card {
    width: 30%;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.arrows{
    margin: 0 10px;
}
</style>
