<template>
  <div class="calculator is-flex-center mt-2">
    <div class="field-5 pb-5" ref="calculator">
      <div class="control">
        <div class="columns is-mobile is-justify-content-center is-align--center mt-2">
          <div class="column is-6 is-result-columns">
            <label for="price" class="is-size-4">
              Distance (Km):
            </label>
          </div>
          <div class="column is-6 is-result-columns">
            <input
                id="km"
                v-model="km"
                class="input mt-1 is-input"
                type="number"
                placeholder="0"
            >
          </div>
        </div>
      </div>
      <div class="control mt-4">
        <div class="columns is-mobile is-justify-content-center is-align-items-center">
          <div class="column is-6">
            <label for="shipping" class="is-size-4">
              Price Per Liter:
            </label>
          </div>
          <div class="column is-6">
            <input
                id="price"
                v-model="price"
                class="input mt-1 is-input"
                type="number"
                placeholder="0"
            >
          </div>
        </div>
      </div>
      <div class="control mt-4">
        <div class="columns is-mobile is-justify-content-center is-align-items-center">
          <div class="column is-6">
            <label for="shipping" class="is-size-4">
              Consumption (l/100km):
            </label>
          </div>
          <div class="column is-6">
            <input
                id="consumption"
                v-model="consumption"
                class="input mt-1 is-input"
                type="number"
                placeholder="0"
            >
          </div>
        </div>
      </div>
      <div class="control mt-4">
        <div class="columns is-mobile is-justify-content-center is-align-items-center">
          <div class="column is-6">
            <label for="shipping" class="is-size-4">
              People Per Car:
            </label>
          </div>
          <div class="column is-6">
            <input
                id="people"
                v-model="people"
                class="input mt-1 is-input"
                type="number"
                placeholder="0"
            >
          </div>
        </div>
      </div>
      <div class="hr mt-6 mb-6" />
      <h1 class="is-size-3">
        Total Cost: {{ total }}
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  name: "Calculator-bmi",
  data () {
    return {
      km: 100,
      price: 2,
      people: 2,
      consumption: 10
    }
  },
  computed: {
    total () {
      const value = ((this.km/100) * this.consumption * this.price) / this.people
      return (Math.round(value * 100)/100).toFixed(2)
    }
  }
}
</script>