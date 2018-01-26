<template>
    <section id ="JobListing">
      <h2>Job Listings</h2>
      <ul id="job-listings">
        <li v-for="listing in jobListData" :key="listing.id">
          <h4>{{listing.title}}</h4>
          <small>{{listing.pay}}</small>
          <p>{{listing.description}}</p>
          <small v-if="listing.interested.length === 1">{{listing.interested.length}} dino is interested in this job.</small> 
          <small v-else>{{listing.interested.length}} dinos are interested in this job.</small> 
         </li>
      </ul>
    </section>
</template>
<script>
export default {
  name: 'JobListing',
  props: ['jobListData']
};
</script>

<style scoped>
.JobListing {
  grid-column: 2/3;
}

h2 {
  margin: 0;
  color: #61ccb1;
}

li {
  display: flex;
  flex-flow: column;
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  margin-bottom: 10px;
  padding: 10px;
}

ul {
  list-style: none;
}

h4 {
  margin: 0;
}

small {
  color: black;
  font-size: 0.5rem;
  margin-left: 10px;
}

p {
  font-size: 0.8rem;
}
</style>
