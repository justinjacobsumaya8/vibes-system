<template>
  <div class="">
    <v-card class="payment-card">
      <v-card-title class="align-start">
        <span class="subtitle-2 font-weight-bold">Payment</span>
      </v-card-title>

      <v-card-text>
        
        <div class="mt-2">
          <div class="box-option mb-4">
            <label v-bind:class="{ isActive: booking === 'Walk-in' }" v-for="(booking, index) in bookings" :key="index">
              <input type="radio" v-model="form.booking" :value="booking" checked />
              <span class="text ml-0">{{ booking }}</span>
            </label>
          

          </div>

          <!-- <v-row class="m-0">
            <v-col cols="12" md="3" sm="6">
              <v-text-field
                v-model="number_people"
                label="Number of people"  
                type="number"
              >
                <template v-slot:prepend>
                    <v-avatar rounded size="38" color="#5e56690a" class="me-4">
                        <v-icon size="22" 
                        @click="decrement()">
                          {{ icons.mdiMinus}}
                        </v-icon>
                    </v-avatar>
                   
                </template>
                <template v-slot:append-outer>
                   <v-icon size="22"
                    @click="increment()">
                      {{ icons.mdiPlus}}
                  </v-icon>
                </template>
              </v-text-field>
            </v-col>
          </v-row> -->
          
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import { mdiDotsVertical, mdiMenuUp, mdiPlus, mdiMinus } from '@mdi/js'

export default {


  data() {
    
    return {
      isActive: 1,
      bookings: ['Walk-in', 'Exclusive'],
      form: {
        booking: '',
      },
      number_people:1,
      min: 1,
     
    }
  },
  setup() {
    return {
      icons: { mdiDotsVertical, mdiMenuUp, mdiPlus, mdiMinus},
    }
  },
  methods: {
    decrement () {
      this.number_people--
    },
    increment () {
      this.number_people++
    },
  },
}
</script>

<style lang="scss">
.m-0 {
  margin: 0;
}
.payment-card {
  padding: 0 20px;
}
.box-option {
  display: flex;
  label {
    cursor: pointer;
    input {
      display: none;
    }
    .text {
      color: #555;
      font-family: 'roboto', arial, sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      width: 150px;
      height: auto;
      margin: 0 16px;
      border: 1px solid #f8f8f8;
      background: #f8f8f8;
      padding: 12px 10px;
      text-align: center;
      font-size: 13px;
      border-radius: 10px;
      text-transform: uppercase;
    }
    &.isActive {
      font-size: 30px;
    }
    &:hover .text {
      border-color: var(--v-primary-base);
      box-shadow: 0 0 8px #ccc;
    }
    input:checked + .text {
      color: #ffffff;
      border-color: var(--v-primary-base);
      background:var(--v-primary-base);
    }
  }
}
.v-input__slot {
  margin-bottom: 0 !important;
}
.v-input {
  .v-text-field{
    input {
      text-align: center !important;
    }
  }
}

.v-input input {
  text-align: center;
}
</style>