<template>
  <div>
    <h1>This is the countries page {{page}}</h1>

  <div class="countries">
    <div v-for="country in countries.slice((this.page-1)*20,this.page*20)" :key="country.name.common" class="country">
      <h6><u>Name:</u> {{country.name.common}}</h6>
      <h6><u>Capital:</u> {{country.capital[0]}}</h6>
      <h6><u>Region:</u> {{country.subregion}}, {{countries[0].region}}</h6>
    </div>
  </div>


  <div class="buttons">
    <button @click="page++;if (page>maxPages) {page=1;}">Next</button>
    <button @click="page--;if (page==0) {page=maxPages;}">Prev</button>  
  </div>
  </div>
</template>

<style scoped lang="less">
    .buttons{
        // width: 60%;
        padding: 0 10%;
        display: flex;
        justify-content: space-between;

    }
  .countries{
    display: flex;
    flex-flow: wrap;
    justify-content: start;
    padding: 0 10%;
  }
  .country {
    border: 1px solid black;
    border-radius: .7rem;
    padding: 1rem;
    margin:1rem;

    width: 10%;
  }
  .country:hover{
    background-color: grey;
  }
  .country h6{
    text-align: left;
    margin: 0;
  }
</style>

<script>
import * as countriesJSON from '@/assets/countries.json';

export default {
  name: "Countries",
  data(){
    console.log(countriesJSON);
    return {
      countries: countriesJSON.default,
    }
  },
  props: {
    page: {
      type: Number,
      default: 1
    }
  },
  computed: {
    maxPages: function () {return Math.ceil(this.countries.length/20);}
    }
  
  // methods : {
  //   // next: () =

  // }
};
</script>+