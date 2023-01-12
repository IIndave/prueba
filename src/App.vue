<template>
  <div>
    <TablaPersonas :personas="personas" :cities="cities" :countries="countries" :studies="studies" :gender="gender" :bloodType="bloodType" :continent="continent"/>
    <TablaUtc :personas="personas" :cities="cities" :countries="countries" :studies="studies" :gender="gender" :bloodType="bloodType" :continent="continent"/>
    <TablaContinente :personas="personas" :cities="cities" :countries="countries" :studies="studies" :gender="gender" :bloodType="bloodType" :continent="continent"/>
  </div>
</template>

<script>
import TablaPersonas from './components/TablaPersonas.vue'
import TablaUtc from "./components/TablaUtc.vue";
import TablaContinente from "./components/TablaContinente.vue";



export default {
  name: 'App',
  components: {
    TablaPersonas,
    TablaUtc,
    TablaContinente
  },
  data() {
        return {
    personas: [
      {
      "person_id": "1",
      "name": "Laurie",
      "surname1": "Moreau",
      "age": 10,
      "height": 130,
      "weight": 32,
      "city_id": "5",
      "study_id": "1",
      "gender_id": "2",
      "bloodtype_id": "1",
      },
      {
      "person_id": "2",
      "name": "María",
      "surname1": "Martínez",
      "age": 40,
      "height": 165,
      "weight": 55,
      "city_id": "2",
      "study_id": null,
      "gender_id": "2",
      "bloodtype_id": "4",
      },
      {
      "person_id": "3",
      "name": "Akita",
      "surname1": "Yamaguchi",
      "age": 85,
      "height": 160,
      "weight": 63,
      "city_id": "3",
      "study_id": "1",
      "gender_id": "1",
      "bloodtype_id": "2",
      },
      {
      "person_id": "4",
      "name": "Javiera",
      "surname1": "García",
      "age": 25,
      "height": 150,
      "weight": 70,
      "city_id": "1",
      "study_id": "2",
      "gender_id": "2",
      "bloodtype_id": "3",
      },
      {
      "person_id": "5",
      "name": "Fausta",
      "surname1": "Sanz",
      "age": 55,
      "height": 155,
      "weight": 65,
      "city_id": "4",
      "study_id": null,
      "gender_id": "2",
      "bloodtype_id": "1",
      },
      {
      "person_id": "6",
      "name": "Iñigo",
      "surname1": "Indave",
      "age": 31,
      "height": 174,
      "weight": 65,
      "city_id": "1",
      "study_id": "1",
      "gender_id": "1",
      "bloodtype_id": "3",
      },
      {
      "person_id": "7",
      "name": "Yi",
      "surname1": "Yuan",
      "age": 25,
      "height": 192,
      "weight": 89,
      "city_id": "7",
      "study_id": "2",
      "gender_id": "1",
      "bloodtype_id": "4",
      },
      {
      "person_id": "8",
      "name": "Leyre",
      "surname1": "Perez",
      "age": 18,
      "height": 160,
      "weight": 55,
      "city_id": "9",
      "study_id": "2",
      "gender_id": "2",
      "bloodtype_id": "1",
      },
      {
      "person_id": "9",
      "name": "Eva",
      "surname1": "Pochenko",
      "age": 54,
      "height": 182,
      "weight": 95,
      "city_id": "10",
      "study_id": "1",
      "gender_id": "2",
      "bloodtype_id": "3",
      },
      {
      "person_id": "10",
      "name": "Maria",
      "surname1": "Torres",
      "age": 26,
      "height": 153,
      "weight": 50,
      "city_id": "16",
      "study_id": "1",
      "gender_id": "2",
      "bloodtype_id": "2",
      },
      {
      "person_id": "11",
      "name": "Roberta",
      "surname1": "Fernandes",
      "age": 87,
      "height": 145,
      "weight": 50,
      "city_id": "6",
      "study_id": null,
      "gender_id": "2",
      "bloodtype_id": "2",
      },
      {
      "person_id": "12",
      "name": "Pedro",
      "surname1": "Lopez",
      "age": 36,
      "height": 178,
      "weight": 75,
      "city_id": "11",
      "study_id": "2",
      "gender_id": "1",
      "bloodtype_id": "3",
      },
      {
      "person_id": "13",
      "name": "Carla",
      "surname1": "Martin",
      "age": 22,
      "height": 172,
      "weight": 68,
      "city_id": "12",
      "study_id": "1",
      "gender_id": "2",
      "bloodtype_id": "3",
      },
      {
      "person_id": "14",
      "name": "Mohammed",
      "surname1": "Waad",
      "age": 22,
      "height": 178,
      "weight": 76,
      "city_id": "13",
      "study_id": null,
      "gender_id": "1",
      "bloodtype_id": "1",
      },
      {
      "person_id": "13",
      "name": "Dimitri",
      "surname1": "Arshavin",
      "age": 38,
      "height": 168,
      "weight": 74,
      "city_id": "14",
      "study_id": "2",
      "gender_id": "1",
      "bloodtype_id": "2",
      },
      {
      "person_id": "14",
      "name": "Tom",
      "surname1": "Jerry",
      "age": 15,
      "height": 155,
      "weight": 50,
      "city_id": "15",
      "study_id": "1",
      "gender_id": "1",
      "bloodtype_id": "1",
      },
      {
      "person_id": "14",
      "name": "Mo",
      "surname1": "Salah",
      "age": 28,
      "height": 175,
      "weight": 78,
      "city_id": "17",
      "study_id": null,
      "gender_id": "1",
      "bloodtype_id": "2",
      }
    ],
    cities: [{
      "city_id": "1",
      "utc":"UTC+1",
      "cityName": "Pamplona",
      "country_id": "1"
      },
      {
      "city_id": "2",
      "utc":"UTC",
      "cityName": "Santa Cruz de Tenerife",
      "country_id": "1"
      },
      {
      "city_id": "3",
      "utc":"UTC+9",
      "cityName": "Tokyo",
      "country_id": "4"
      },
      {
      "city_id": "4",
      "utc":"UTC-5",
      "cityName": "Bogotá",
      "country_id": "3"
      },
      {
      "city_id": "5",
      "utc":"UTC+1",
      "cityName": "Burdeos",
      "country_id": "2"
      },
      {
      "city_id": "6",
      "utc":"UTC",
      "cityName": "Lisboa",
      "country_id": "5"
      },
      {
      "city_id": "7",
      "utc":"UTC+8",
      "cityName": "Pekin",
      "country_id": "6"
      },
      {
      "city_id": "8",
      "utc":"UTC-5",
      "cityName": "New York",
      "country_id": "7"
      },
      {
      "city_id": "9",
      "utc":"UTC-3",
      "cityName": "Buenos Aires",
      "country_id": "8"
      },
      {
      "city_id": "10",
      "utc":"UTC+2",
      "cityName": "Kyev",
      "country_id": "9"
      },
      {
      "city_id": "11",
      "utc":"UTC-8",
      "cityName": "Los Angeles",
      "country_id": "7"
      },
      {
      "city_id": "12",
      "utc":"UTC-6",
      "cityName": "Ciudad de México",
      "country_id": "10"
      },
      {
      "city_id": "13",
      "utc":"UTC+3",
      "cityName": "Doha",
      "country_id": "11"
      },
      {
      "city_id": "14",
      "utc":"UTC+5",
      "cityName": "Ekaterinburgo",
      "country_id": "12"
      },
      {
      "city_id": "15",
      "utc":"UTC+10",
      "cityName": "Brisbane",
      "country_id": "13"
      },
      {
      "city_id": "16",
      "utc":"UTC",
      "cityName": "Las Palmas de Gran Canaria",
      "country_id": "1"
      },
      {
      "city_id": "17",
      "utc":"UTC+2",
      "cityName": "El Cairo",
      "country_id": "14"
      }
      ],
    countries: [{
    "country_id": "1",
    "countryName": "España",
    "continent_id":"1"
    },
    {
    "country_id": "2",
    "countryName": "Francia",
    "continent_id":"1"
    },
    {
    "country_id": "3",
    "countryName": "Colombia",
    "continent_id":"4"
    },
    {
    "country_id": "4",
    "countryName": "Japón",
    "continent_id":"2"
    },
    {
    "country_id": "5",
    "countryName": "Portugal",
    "continent_id":"1"
    },
    {
    "country_id": "6",
    "countryName": "China",
    "continent_id":"2"
    },
    {
    "country_id": "7",
    "countryName": "Estados Unidos",
    "continent_id":"4"
    },
    {
    "country_id": "8",
    "countryName": "Argentina",
    "continent_id":"4"
    },
    {
    "country_id": "9",
    "countryName": "Ucrania",
    "continent_id":"1"
    },
    {
    "country_id": "10",
    "countryName": "México",
    "continent_id":"4"
    },
    {
    "country_id": "11",
    "countryName": "Catar",
    "continent_id":"2"
    },
    {
    "country_id": "12",
    "countryName": "Rusia",
    "continent_id":"1"
    },
    {
    "country_id": "13",
    "countryName": "Australia",
    "continent_id":"5"
    },
    {
    "country_id": "14",
    "countryName": "Egipto",
    "continent_id":"3"
    }
    ],
    continent:[{
      "continent_id": "1",
      "continentName": "Europa"
    },
    {
      "continent_id": "2",
      "continentName": "Asia"
    },
    {
      "continent_id": "3",
      "continentName": "África"
    },
    {
      "continent_id": "4",
      "continentName": "América"
    },
    {
      "continent_id": "5",
      "continentName": "Oceanía"
    }
    ],
    studies: [{
      "study_id": "1",
      "level": "Universidad"
      },
      {
      "study_id": "2",
      "level": "Instituto"
      },
      ],
    gender: [{

    "gender_id": "1",
    "type": "Hombre"
    },
    {
    "gender_id": "2",
    "type": "Mujer"
    }
    ],
    bloodType: [{
      "bloodType_id": "1",
      "bloodName": "A"
      },
      {
      "bloodType_id": "2",
      "bloodName": "B"
      },
      {
      "bloodType_id": "3",
      "bloodName": "AB"
      },
      {
      "bloodType_id": "4",
      "bloodName": "0"
      }
      ]
    }
}
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
