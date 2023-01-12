<template>
    <div class="container lista1">
    <h1>Listado de personas segun UTC</h1>
    <h2>  {{ utc }}</h2>
    <div class="mb-3 selector">
      <label for="customRange2" class="form-label" >Rango Horario</label>
      <h3>{{ `UTC ${value}` }}</h3>
      <input type="range" class="form-range" min="-10" max="10" step="1" id="customRange2" v-model="value">
    </div>
    <div id="tabla-personas" >
      <table class="table table-striped table-hover">
        <thead>
          <tr >
            <th>Nombre</th>
            <th>Apellido</th>
            <th>Edad</th>
            <th>Altura</th>
            <th>Peso</th>
            <th>Ciudad</th>
            <th>Estudios</th>
            <th>Genero</th>
            <th>Sangre</th>
            <th>Pais</th>
            <th>Hora Local</th>
          </tr>
        </thead>
        <tbody v-for="persona in personas" :key="persona.persona_id">
          <tr v-if="value > 0 ? `UTC+${value}` == getIdUtc(persona.city_id) :
                    value < 0 ? `UTC${value}` ==  getIdUtc(persona.city_id) : 
                    value == 0 ? 'UTC' ==getIdUtc(persona.city_id) :
                    'Error' ">
              <td>
                  {{ persona.name }}
              </td>
              <td >
                  {{ persona.surname1}}
              </td>
              <td>
                  {{ persona.age}}
              </td>
              <td>
                  {{ persona.height}}
              </td>
              <td>
                  {{ persona.weight}}
              </td>
              
              <td>
                {{ getCity(persona.city_id) }}
              </td>
              
              <td>
                {{ getStudies(persona.study_id) }}
              </td>

              <td >
                {{ getGender(persona.gender_id) }}
              </td>

              <td>
                {{ getBloodType(persona.bloodtype_id) }}
              </td>
              <td>
                <a :href="`${url}/${getCountry(persona.city_id)}`" target="_blank" class="link-success">{{ getCountry(persona.city_id) }}</a>
              </td>
              <td>
                {{ getUtc(persona.city_id) }}
              </td>
          </tr>
      </tbody>
      </table>
    </div>
    </div>
</template>
<script >
import { DateTime } from "luxon";

    export default {
      name: 'TablaUtc',
      data() {
        return {
          utc:DateTime.utc().toFormat("ttt "),
          value: 0,
          continente: 'Europa',
          url:"https://www.google.es/maps/place"
      }
    },
      props: {
        personas: Array,
        cities: Array,
        countries: Array,
        studies:Array,
        gender:Array,
        bloodType:Array,
        continent:Array
    },
    methods: {
     getCity(id){
      return this.cities.find(el => el.city_id == id).cityName
     },
     getStudies(id){
      if(id == undefined){
        return "Sin estudios"
      } else{
        return this.studies.find(el => el.study_id == id).level
      }
     },
     getGender(id){
      return this.gender.find(el => el.gender_id == id).type
     },
     getBloodType(id){
      return this.bloodType.find(el => el.bloodType_id == id).bloodName
     },
     getIdCountry(id){
      return this.cities.find(el => el.city_id == id).country_id
     },
     getCountry(id){
      const IdCountry = this.getIdCountry(id)
      const Country =  this.countries.find(el => el.country_id == IdCountry).countryName
      return Country
     },
     getIdUtc(id){
      return this.cities.find(el => el.city_id == id).utc
     },
     getUtc(id){
      const Utc = this.getIdUtc(id)
      const hora =  (DateTime.utc().setZone(Utc)).toFormat("HH : mm ")
      return hora
     },
     getContinent(id){
      const IdCountry = this.getIdCountry(id)
      const IdContinent =  this.countries.find(el => el.country_id == IdCountry).continent_id
      const Continente = this.continent.find(el => el.continent_id == IdContinent).continentName
      return Continente;
     }
  },
}
  </script>
  
<style scoped>
.form-range{
    max-width: 300px;
  }
.lista1{
    font-size: 1vw;
    height: 400px;
    margin-bottom: 50px;
  }
  
  ::-webkit-slider-thumb{margin-top: -9px;
    color: green}
    input[type='range']:focus {
  outline: none;
}

input[type='range'],
input[type='range']::-webkit-slider-runnable-track,
input[type='range']::-webkit-slider-thumb {
  -webkit-appearance: none;
}

input[type=range]::-webkit-slider-thumb {
  border:3px solid rgb(209, 64, 64);
  width: 20px;
  height: 20px;
  background-color:  rgb(243, 8, 8);
  border-radius: 50%;
  margin-top: -9px;
}
input[type=range]::-webkit-slider-runnable-track {
  background-color: #777;
  height: 5px;
}
.container{
  font-size: 1vw;
}
</style>
