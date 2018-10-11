<template>

    <v-container fluid grid-list-md >
      <v-layout column justify-space-between >
        <v-flex>
          <v-layout row wrap align-content-start>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
              <GraphCard :DataID="1"></GraphCard>
            
          </v-layout>
        </v-flex>
      </v-layout>
    </v-container>
</template>


<script>
 /* eslint-disable */
 /*
* Google trends homepage
* This is the landing page for google trends and all that
* you will have mutliple fun graphs to take up white space
* Functionality
* -> Host Game
* -> Join Game
* -> Settings
* -> Credits
*/
import GraphCard from "@/components/GraphCard";
export default {
  components: { GraphCard },
  name: "Homepage"
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
