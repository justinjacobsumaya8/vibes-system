<template>
  <div class="p-6">
    <v-card>
      <v-card-title> Cashier </v-card-title>
      <section>
        <div class="cards">
          <label v-bind:class="{ isActive: booking === 'Walk-in' }" v-for="(booking, index) in bookings" :key="index">
            <input type="radio" v-model="form.booking" :value="booking" checked />
            <span class="text">{{ booking }}</span>
          </label>
        </div>
      </section>
    </v-card>
  </div>
</template>

<script>
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
}
</script>

<style lang="scss" scoped>
.p-6 {
  padding: 6em;
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
  color: #ae2b26;
  font-family: 'roboto', arial, sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 200px;
  height: 120px;
  margin: 0 16px;
  border: 1px solid #f2f2f2;
  background: #f8f8f8;
  padding: 16px;
  text-align: center;
  font-size: 16px;
}
.cards label.isActive {
  font-size: 30px;
}
.cards label:hover .text {
  border-color: #ae2b26;
  box-shadow: 0 0 8px #ccc;
}
.cards label input:checked + .text {
  color: green;
  border-color: green;
}
</style>