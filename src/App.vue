<template>
  <div id="app">
    <TheHeader/>
    <main>
    <JobListing :jobListData="listingData"/>
    <JobForm :sendListing="postListing"/>
    </main>
    <TheFooter/>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader';
import JobListing from './components/JobListing';
import JobForm from './components/JobForm';
import TheFooter from './components/TheFooter';

export default {
  name: 'App',
  components: { TheHeader, JobListing, JobForm, TheFooter },
  data() {
    return {
      apiURL: '../static/listings.json',
      listingData: []
    };
  },
  mounted() {
    this.getListings();
  },
  methods: {
    getListings() {
      fetch(this.apiURL)
        .then(response => response.json())
        .then(response => {
          this.listingData = response.reverse();
        });
    },
    postListing(listing) {
      this.listingData.unshift(listing);
    }
  }
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  font-weight: 150;
  color: #137059;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}

#TheHeader {
  grid-row: 1 / 2;
}
main {
  grid-row: 2/3;
  display: grid;
  grid-template-columns: 5% 42.5% 5% 42.5% 5%;
}
#JobListing {
  grid-column: 2/3;
}
#side-bar {
  grid-column: 4/5;
}
</style>
