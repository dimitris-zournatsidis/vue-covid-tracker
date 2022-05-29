<template>
  <header class="header-container">
    <div class="header-title">
      <i class="fa fa-viruses"></i> Covid-19 Tracker
    </div>

    <p>
      API by
      <a href="https://covid19api.com/" target="_blank" class="api-link"
        >covid19api.com</a
      >
    </p>
  </header>
</template>

<script>
export default {
  // eslint-disable-next-line
  name: 'Header',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header-container {
  text-align: center;
  background-color: blue;
  color: white;
  padding: 2rem;
  margin-bottom: 3rem;
}

.header-title {
  font-size: 2rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.api-link {
  color: white;
}

/* for tablet resolutions and bigger */
@media (min-width: 961px) {
  .header-title {
    font-size: 3rem;
  }
}
</style>
