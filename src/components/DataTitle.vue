<template>
  <div class="data-title-container">
    <h2>{{ text }}</h2>
    <div>{{ timestamp }}</div>
  </div>
</template>

<script>
import dayjs from 'dayjs';

export default {
  name: 'DataTitle',
  props: ['text', 'dataDate'],

  computed: {
    timestamp: function () {
      return dayjs(this.dataDate).format('DD-MM-YYYY, h:mm:ss a');
    },
  },
};
</script>

<style>
.data-title-container {
    margin-bottom: 2rem;
}

.data-title-container h2 {
    /* border: 1px solid red; */
}

.data-title-container div {
    /* border: 1px solid blue; */
}
</style>
