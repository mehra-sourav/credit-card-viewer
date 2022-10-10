<template>
  <q-page class="">
    <!-- Available balance text row -->
    <div class="row">
      Available Balance
    </div>

    <!-- Available balance and add new card button row -->
    <div class="row">
      <S1>S$</S1>
      3,000
      <q-btn no-caps class="new_card_btn">
        <q-icon name="add_circle" size="sm" ></q-icon>
        <div class="new_card_btn__text">New Card</div>
      </q-btn>
    </div>

    <!-- Personal and company tab switcher row -->
    <div class="row">
    </div>

    <!-- Card and card details container row -->
    <div class="row">
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
<style lang="scss">

.new_card_btn {
  color: var(--white);
  background-color: var(--navy-blue);

  &__text {
    color: var(--white);
  }

}

</style>
