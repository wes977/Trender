<template>


        <v-card>
<highcharts  :options='this.option' ref='highcharts'></highcharts >
  
          <v-card-title primary-title>
            <div>
              <h3 class='headline mb-0'>{{ this.option.title.text }}</h3>
              <div>{{this.option.series[0].name}} VS {{this.option.series[1].name}}</div>
            </div>
          </v-card-title>
  
          <v-card-actions>
            <v-btn flat color='orange'>Share</v-btn>
            <v-btn flat color='orange'>Explore</v-btn>
          </v-card-actions>
        </v-card>


</template>


<script>
 /* eslint-disable */
/*
* Graph Card
* This component is for the Google trends homepage and all
* basically just display these cards on the home screen with cool
* VS Topics like oranges vs Apples.
* all this will be fed from web sockets
*/
import { Chart } from "highcharts-vue";
var options = {
  title: {
    text: "Monthly Average Temperature",
    x: -20
  },
  subtitle: {
    text: "Source: WorldClimate.com",
    x: -20
  },
  xAxis: {
    categories: [
      "Jan",
      "Feb",
      "Mar",
      "Apr",
      "May",
      "Jun",
      "Jul",
      "Aug",
      "Sep",
      "Oct",
      "Nov",
      "Dec"
    ]
  },
  yAxis: {
    min: 0,
    max: 100,
    visible: false,
    title: {
      enabled: false,
    },
    plotLines: [
      {
        value: 0,
        width: 1,
        color: "#808080"
      }
    ]
  },
  tooltip: {
    valueSuffix: "°C"
  },
  legend: {
    enabled: false,
    layout: "vertical",
    align: "right",
    verticalAlign: "middle",
    borderWidth: 0
  },
  series: [
    {
      name: "Tokyo",
      data: [7.0, 6.9, 9.5, 14.5, 18.2, 21.5, 25.2, 26.5, 23.3, 18.3, 13.9, 9.6]
    },
    {
      name: "New York",
      data: [-0.2, 0.8, 5.7, 11.3, 17.0, 22.0, 24.8, 24.1, 20.1, 14.1, 8.6, 2.5]
    }
  ]
};
var options2 = {
  title: {
    text: "WES GRPAH AND ALL THAT ",
    x: -20
  },
  subtitle: {
    text: "Source: WorldClimate.com",
    x: -20
  },
  xAxis: {
    categories: [
      "Jan",
      "Feb",
      "Mar",
      "Apr",
      "May",
      "Jun",
      "Jul",
      "Aug",
      "Sep",
      "Oct",
      "Nov",
      "Dec"
    ]
  },
  yAxis: {
    title: {
      text: "Temperature (°C)"
    },
    plotLines: [
      {
        value: 0,
        width: 1,
        color: "#808080"
      }
    ]
  },
  tooltip: {
    valueSuffix: "°C"
  },
  legend: {
    layout: "vertical",
    align: "right",
    verticalAlign: "middle",
    borderWidth: 0
  },
  series: [
    {
      name: "Tokyo",
      data: [7.0, 6.9, 9.5, 14.5, 18.2, 21.5, 25.2, 26.5, 23.3, 18.3, 13.9, 9.6]
    },
    {
      name: "New York",
      data: [-0.2, 0.8, 5.7, 11.3, 17.0, 22.0, 24.8, 24.1, 20.1, 14.1, 8.6, 2.5]
    },
    {
      name: "Berlin",
      data: [-0.9, 0.6, 3.5, 8.4, 13.5, 17.0, 18.6, 17.9, 14.3, 9.0, 3.9, 1.0]
    },
    {
      name: "London",
      data: [3.9, 4.2, 5.7, 8.5, 11.9, 15.2, 17.0, 16.6, 14.2, 10.3, 6.6, 4.8]
    }
  ]
};
export default {
  components: { highcharts: Chart },
  data() {
    return {
      options: this.option
    };
  },
  mounted() {
    console.log(this.option); // {x:1}
    console.log(this.DataID);
  },
  props: ["DataID"],
  computed: {
    option: function() {
      if (this.DataID === 1) {
        console.log("1");
        return options;
      } else if (this.DataID === 2) {
        console.log("2");
        return options2;
      } else {
        console.log("other");
        console.log(this.DataID);
        return {};
      }
    }
  }
};
</script>


<!-- Add 'scoped' attribute to limit CSS to this component only -->
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
