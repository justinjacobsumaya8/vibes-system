<template>
  <div class="">
    <v-card>
      <v-card-title>
        
        <v-simple-table dense class="w-100">
          <template v-slot:default>
            <thead>
              <tr>
                <th class="text-uppercase">
                  Subject
                </th>
                <th class="text-center text-uppercase">
                  Quantity
                </th>
                <th class="text-center text-uppercase">
                  Price
                </th>
                
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="item in desserts"
                :key="item.dessert"
              >
                <td>{{ item.dessert }}</td>
                <td class="text-center">
                  {{ item.calories }}
                </td>
                <td class="text-center">
                  {{ item.fat }}
                </td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>

      </v-card-title>

      <v-card-text class="my-7">
        <div class="cards">
          <v-btn small color="primary"> Checkout </v-btn>
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import { mdiDotsVertical, mdiMenuUp } from '@mdi/js'

export default {
  data() {
    return {
      isActive: 1,
      bookings: ['Walk-in', 'Exclusive'],
      form: {
        booking: '',
      },
    }
  },
  setup() {
    return {
      icons: { mdiDotsVertical, mdiMenuUp },
    }
  },
}
</script>

<style lang="scss">
.w-100{
  width: 100%;
}
.cards {
  display: flex;
}
.cards label {
  cursor: pointer;
}
.cards label input {
  display: none;
}
.cards label .text {
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
  padding: 16px;
  text-align: center;
  font-size: 16px;
  border-radius: 10px;
}
.cards label.isActive {
  font-size: 30px;
}
.cards label:hover .text {
  border-color: var(--v-primary-base);
  box-shadow: 0 0 8px #ccc;
}
.cards label input:checked + .text {
  color: #ffffff;
  border-color: var(--v-primary-base);
  background:var(--v-primary-base);
}

</style>