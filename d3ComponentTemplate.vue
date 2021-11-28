<template>
  <svg id="d3ComponentTemplate"></svg>
</template>
<script>
import * as d3 from "d3";

export default {
  name: "d3ComponentTemplate",
  props: {
    rawData: {
        type: Array,
        required: false,
        default: function(){
            return []
        }
    },
    componentWidth: {
        type: Number,
        default: 800
    },
    componentHeight: {
        type: Number,
        default: 600
    },
  },
  methods: {
    parseData(){
        this.data = this.configs.rawData;
    },
    initialzeAxes() {
        
    },
    initializeDimensions(){
        document.getElementById('d3ComponentTemplate').style.width = this.configs.componentWidth;
        document.getElementById('d3ComponentTemplate').style.height = this.configs.componentHeight;
    },
    init(){
    this.svg = d3.select("#d3ComponentTemplate");
    this.configs = this._props;
    this.initializeDimensions();
    this.parseData()
    },
    draw(){

    }
  },
  mounted() {
    this.init();
    this.draw();
  },
  watch: {
    data: function(value){
      this.data = value;
      this.draw;
    }
  }
};
</script>
<style lang="scss">
</style>