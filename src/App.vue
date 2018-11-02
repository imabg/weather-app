<template>
  <div id="app">
    <div class="container">
      <p class="display-3">Weather-App</p>
      <SearchBar @retieve = "getValue"/>
      <TempDetail
        :dataValue = "dataValue"
        :getData = "getData"
        class="alignment"
      />
    </div>
      <Myfooter />
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
import TempDetail from './components/TempDetail.vue';
import Myfooter from './components/footer.vue';

export default {
  name: 'app',
  components: {
    SearchBar,
    TempDetail,
    Myfooter
  },
  data() {
    return {
      dataValue: {},
      getData: false,
    };
  },
  methods: {
    getValue(value) {
      axios
      .get(`https://api.openweathermap.org/data/2.5/weather?q=${value}&appid=439452958cde2bf996ff4137d7f1353d`)
      .then(response => {
        this.dataValue = response.data;
      })
      .catch(err => alert('Error'));
      this.getData = true;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.alignment  {
  align-items: center;
}
</style>
