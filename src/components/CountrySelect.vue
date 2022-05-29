<template>
  <select v-model="selected" @change="onChange()">
    <option value="0">Select Country</option>
    <!-- <option :v-for="country in countries" :value="country.ID">
        {{country.Country}}    
    </option> -->
  </select>
</template>

<script>
export default {
  name: 'CountrySelect',
  props: ['countries'],

  data() {
    return {
      selected: 0,
    };
  },
  methods: {
    onChange() {
      const country = this.country.find((item) => item.ID === this.selected);
      console.log('country!!', country);
      this.$emit('get-country');
    },
  },
};
</script>

<style>
select {
  /* border: 1px solid red; */
  margin-top: 2rem;
  padding: 0.5rem;
  width: 100%;
  outline: none;
}

@media (min-width: 961px) {
  select {
    width: 50%;
  }
}
</style>
