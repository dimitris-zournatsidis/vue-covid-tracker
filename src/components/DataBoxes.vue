<template>
  <div class="data-boxes-container">
    <!-- Cases Container -->
    <div class="wrapper-div">
      <h3 class="title">Cases</h3>
      <div><span>New:</span> {{ prettifyNumbers(stats.NewConfirmed) }}</div>
      <div><span>Total:</span> {{ prettifyNumbers(stats.TotalConfirmed) }}</div>
    </div>

    <!-- Mortalities Container -->
    <div class="wrapper-div">
      <h3 class="title">Deaths</h3>
      <div><span>New:</span> {{ prettifyNumbers(stats.NewDeaths) }}</div>
      <div><span>Total:</span> {{ prettifyNumbers(stats.TotalDeaths) }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  methods: {
    // function that adds commas to numbers
    prettifyNumbers(num) {
      return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
    },
  },
};
</script>

<style>
.data-boxes-container {
  display: grid;
  gap: 3rem;
}

.wrapper-div {
  box-shadow: 2px 1px 1px;
  background-color: lightblue;
  text-align: center;
  border-radius: 1rem;
  /* margin-bottom: 2rem; */
  padding: 1rem;
}

.title {
  font-size: 1.5rem;
  color: blue;
  font-weight: bold;
}

.wrapper-div span {
  /* border: 1px solid red; */
  font-weight: bold;
}

@media (min-width: 961px) {
  .data-boxes-container {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
