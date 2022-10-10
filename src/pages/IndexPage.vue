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
      <div class="col flex flex-end">
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
      <q-card class="card-section q-pa-lg">
        <q-card-section class="row q-col-gutter-x-xl">
          <div class="col-6 flex-center">
            <CardCarousel 
             :active-card-idx="activeCard"
             :cards-list="cardsList"
            />
            <CardActions 
             :active-card-idx="activeCard"
             :cards-list="cardsList"
            />
          </div>
          <div class="col-6 flex flex-center">
            <!-- <q-list bordered class="rounded-borders">
              <q-expansion-item
                expand-separator
                icon="perm_identity"
                label="Account settings"
                caption="John Doe"
              >
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                    commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                    eveniet doloribus ullam aliquid.
                  </q-card-section>
                </q-card>
              </q-expansion-item>

              <q-expansion-item
                expand-separator
                icon="signal_wifi_off"
                label="Wifi settings"
              >
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                    commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                    eveniet doloribus ullam aliquid.
                  </q-card-section>
                </q-card>
              </q-expansion-item>

              <q-expansion-item
                expand-separator
                icon="drafts"
                label="Drafts"
                header-class="text-purple"
              >
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                    commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                    eveniet doloribus ullam aliquid.
                  </q-card-section>
                </q-card>
              </q-expansion-item>

              <q-expansion-item icon="assessment" label="Disabled" disable>
                <q-card>
                  <q-card-section>
                    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quidem, eius reprehenderit eos corrupti
                    commodi magni quaerat ex numquam, dolorum officiis modi facere maiores architecto suscipit iste
                    eveniet doloribus ullam aliquid.
                  </q-card-section>
                </q-card>
              </q-expansion-item>
            </q-list> -->
          </div>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import CardCarousel from 'components/CardCarousel.vue';
import CardActions from 'components/CardActions.vue';

export default {
  name: 'IndexPage',
  components: {
    CardCarousel,
    CardActions
  },
  data() {
    return {
      avlBalance: "3,000",
      selectedTab: "personal_cards",
      activeCard: 0,
      cardsList: [
        {
          name: "Mark Henry",
          number: "1234-5678-9001-2020",
          cvv: 534,
          expirationDate: "2/2027",
          isActive: true,
          spendLimit: 10000,
          cancelled: false
        },
        {
          name: "Sam Fischer",
          number: "4539-7335-4677-7960",
          cvv: 830,
          expirationDate: "12/2027",
          isActive: true,
          spendLimit: 15000,
          cancelled: false
        },
        {
          name: "Ezio Auditore",
          number: "4556-1944-5315-2697",
          cvv: 534,
          expirationDate: "9/2028",
          isActive: false,
          spendLimit: 5000,
          cancelled: true
        }
      ]
    }
  }
}
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
