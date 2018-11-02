<template>
  <div v-if = "getData" >
    <div class="card" style="width: 18rem;">
      <div class="card-body ">
          Weather in <span class="card-title country"><strong>{{dataValue.name}}</strong></span> , {{dataValue.sys.country}}
         <div>
           <strong class="country">
             <p style="margin-top = 5px;"> {{dataValue.main.temp - 273.15}}&degC </p>
           </strong>
           <p style="margin-top = 5px;">Description: {{dataValue.weather["0"].main}}</p>
           <p style="margin-top = 5px;">Pressure: {{dataValue.main.pressure}} hpa</p>
           <p style="margin-top = 5px;">Humidity: {{dataValue.main.humidity}} %</p>
           <p style="margin-top = 5px;">Wind Speed: {{dataValue.wind.speed}} m/s</p>
           <p style="margin-top = 5px;">Geolocation Coordinates: [{{dataValue.coord.lat}},{{dataValue.coord.lon}}]</p>
         </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'TempDetail',
  props: {
    dataValue: {
      type: Object,
      required: true
    },
    getData: {
      type: Boolean,
      required: true
    }
  }
}
</script>

<style scoped>
  .country {
    font-size: 23px;
  }
</style>
