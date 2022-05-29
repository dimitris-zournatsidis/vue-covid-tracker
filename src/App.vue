<template>
  <Header />
  <Home />
</template>

<script>
import Header from '@/components/Header';
import Home from '@/Home';

export default {
  name: 'App',
  components: {
    Header,
    Home,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  text-align: center;
  color: black;
  /* margin-top: 3rem; */
  height: 100vh;
}
</style>
