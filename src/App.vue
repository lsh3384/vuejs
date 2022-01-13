<template>
  <div id="app">
    <Header />
    <!-- <div id="content" class="content">
      <router-view :vind="sensor_data"></router-view>
    </div> -->
    <Home :sensor_data="sensor_data"/>
  </div>
</template>

<script>
import Header from './components/layout/Header.vue'
import Home from './views/Home.vue'
export default {
  name: 'App',
  components: {
    Header,
    Home,
  },
  data() {
    return {
      sensor_data: {
        temp: 30,
        humi: 40,
      },
    }
  }

}
</script>