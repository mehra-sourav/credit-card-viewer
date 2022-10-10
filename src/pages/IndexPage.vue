<template>
  <q-page class="main-page">
    <!-- Available balance text row -->
    <div class="row q-mb-sm">
      Available balance
    </div>

    <!-- Available balance and add new card button row -->
    <div class="row">
      <!-- Available balance col -->
      <div class="col-10 avl-blnce">
        <q-badge
         class="flex-center avl-blnce__badge"
         color="badge--green"
         text-color="white"
         label="S$"
         />
        <div 
         class="q-mx-sm avl-blnce__text"
        > 
         {{ avlBalance}}
        </div>
      </div>

      <!-- New card button col -->
      <div class="col">
        <q-btn no-caps class="new_card_btn">
          <q-icon name="add_circle" size="xs" class="q-mr-sm"></q-icon>
          <div class="new_card_btn__text text-right">New card</div>
        </q-btn>
      </div>
    </div>

    <!-- Personal and company tab switcher row -->
    <div class="row q-mt-lg">
      <q-tabs
        v-model="selectedTab"
        no-caps
        dense
        narrow-indicator
        indicator-color="indicator-blue"
        class="text-grey"
        active-color="black"
        active-class="text-weight-bold"
      >
        <q-tab class="q-pl-none" name="personal_cards" label="My debit cards" />
        <q-tab disabled name="all_cards" label="All company cards" />
      </q-tabs>
    </div>

    <!-- Card and card details container row -->
    <div class="row q-mt-md">
      <q-card class="card-section">
        <q-card-section class="row">
          <div class="col-6 flex flex-center">
            CC Card
            buttons
          </div>
          <div class="col-6 flex flex-center">
            transcations
          </div>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data() {
    return {
      avlBalance: "3,000",
      selectedTab: "personal_cards"
    }
  }
})
</script>
<style lang="scss">

.main-page {
  padding: 60px;

  .avl-blnce {
    display: flex;
    align-items: center;
    
    &__badge {
      height:24px; width:40px;
    }
    .text-badge--green {
      color: var(--green) !important;
    }
    .bg-badge--green {
      background: var(--green) !important;
    }
    &__text {
      font-size: 26px;
      font-weight: bold;
    }
  }

  .new_card_btn {
    color: var(--white);
    background-color: var(--navy-blue);

    &__text {
      font-size: 13px;
      font-weight: bold;
    }
  }

  .text-indicator-blue {
    color: var(--blue) !important;
  }
  .bg-indicator-blue {
    color: var(--blue) !important;
  }

  .card-section {
    width: 100%;
    box-shadow: 0px 0px 15px rgb(0 0 0 / 15%);
  }
}

</style>
