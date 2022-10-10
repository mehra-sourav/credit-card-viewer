<template>
    <div>
        <q-card flat class="payment-card q-pa-sm">
            <q-card-section>
                <!-- Aspire logo -->
                <div class="row">
                    <q-img class="q-ml-auto" :src="aspireIconPath" width="20%" />
                </div>
                
                <!-- Card Owner Name -->
                <div class="row q-mt-lg payment-card__name">
                    {{ activeCard.name }}
                </div>

                <!-- Card Number -->
                <div class="row q-mt-lg payment-card__number">
                    {{ activeCard.number }}
                </div>

                <!-- Expiration Date and CVV -->
                <div class="row q-mt-lg payment-card__details">
                    {{ activeCard.expirationDate }} {{ activeCard.cvv }}
                </div>
            </q-card-section>
        </q-card>
    </div>
</template>
<script>
export default {
  name: 'CardCarousel',
  props: {
    activeCardIdx: {
      type: Number,
      required: true
    },
    cardsList: {
      type: Array,
      default: []
    },
  },
  data() {
    return {
        as: 'svguse:icons.svg#icon-1',
        aspireIconPath: require("../assets/payment-card/aspire-icon.svg")
    }
  },
  computed: {
    imgPath() {
      return require(`../assets/sidenav/${this.icon}.svg`);
    },
    activeCard() {
        return this.cardsList?.[this.activeCardIdx] ?? {};
    }
  }
}
</script>
<style lang="scss">

.payment-card {
  background-color: var(--green);
  max-width: 400px;
  color: var(--white);
  border-radius: 10px;

  &__name {
    font-weight: bold;
    font-size: 22px;
    letter-spacing: 2px;
  }
}


</style>