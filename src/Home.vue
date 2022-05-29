<template>
  <main v-if="!isLoading">
    <DataTitle :text="title" :dataDate="dataDate" />
    <DataBoxes :stats="stats" />
    <!-- <CountrySelect :countries="countries" /> -->
  </main>

  <main v-else class="loading-container">
    <div class="loading-title">Loading...</div>
    <img :src="loadingImage" alt="" class="loading-image" />
  </main>
</template>

<script>
import DataTitle from '@/components/DataTitle';
import DataBoxes from '@/components/DataBoxes';
// import CountrySelect from '@/components/CountrySelect';

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Home',
  // in components below, we register the components we use
  components: {
    DataTitle,
    DataBoxes,
    // CountrySelect,
  },

  // in data, we are setting our states
  data() {
    return {
      isLoading: true,
      title: 'Global Data',
      dataDate: '',
      stats: {},
      countries: [],
      loadingImage: require('./assets/hourglass.gif'),
    };
  },

  methods: {
    async fetchCovidData() {
      const res = await fetch('https://api.covid19api.com/summary');
      const data = await res.json();
      return data;
    },
  },

  async created() {
    const data = await this.fetchCovidData();
    console.log('data!!!', data);

    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.isLoading = false;
  },
};
</script>

<style>
.loading-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.loading-title {
  font-size: 1.5rem;
  margin: 3rem auto 2rem;
}

.loading-image {
  width: 5rem;
}
</style>
