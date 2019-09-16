<template lang="html">
  <div>
    <h1>Economics, What?</h1>
    <div class="main-container">
      <!-- <intro-section :intro-sect="introPart"></intro-section> -->
        <the-intro-title :the-introduction-title="theIntroductionTitle"></the-intro-title>
        <the-intro-description :the-introduction-descscription="theIntroductionDescription"></the-intro-description>
      <!-- <gdp-section :gdp-part="gdpPart"></gdp-section> -->
        <gdp-countries-list :gdp-countries="gdpCountries"></gdp-countries-list>
        <gdp-country-detail :gdp-country="selectedGdpCountry"></gdp-country-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import TheIntroTitle from './components/TheIntroTitle.vue'
import TheIntroDescription from './components/TheIntroDescription.vue'
import GdpCountriesList from './components/GdpCountriesList.vue'
import GdpCountryDetail from './components/GdpCountryDetail.vue'

export default {
    data(){
      return {
        theIntroductionTitle: null,
        theIntroductionDescription: null,
        gdpCountries: [],
        selectedGdpCountry: null
      }
    },
    components: {
      "the-intro-title": TheIntroTitle,
      "the-intro-description": TheIntroDescription,
      "gdp-countries-list": GdpCountriesList,
      "gdp-country-detail": GdpCountryDetail
    },
    created: function() {
      this.fetchData();
    },
    methods: {
      json: './GDP-Countries-Table-2018.json',
      fetchData: function() {
        var self = this;
        this.getJSON(json, function(data) {
                  self.GdpCountriesList = data;
                  console.log(data);
        });
      }

    // mounted() {
    //   // fetch('https://www.quandl.com/api/v3/datasets/ODA/NRU_NGDPD?api_key=31__sQVP3TfgYg6BrZPs')
    //   // .then(res => res.json())
    //   // .then(gdpLeagueTable => this.gdpLeagueTable = gdpLeagueTable)
    //   var self = this
    //   this.getJSON("GDP-Countries-Table.json", function(json_data) {
    //     self.gdpLeagueTable = json_data.data
    //   })
    //
      eventBus.$on('gdp-country', (country) => {
        this.selectedGdpCountry = country
      })
    }
}

</script>



<style>
</style>
