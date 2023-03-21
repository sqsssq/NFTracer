<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2022-09-17 23:36:36
 * @LastEditTime: 2023-03-14 23:28:33
-->
<template>
  <div class="common-layout" style="width: 100%; height: 100vh; background-color: rgb(238, 236, 236);"
    v-loading="!initSign" :element-loading-text="loadingText" element-loading-background="rgba(0, 0, 0, 0.8)">
    <Main :cpData="cpData" />
  </div>
</template>

<script>
import Main from '../components/Main.vue';
import { useDataStore } from "../stores/counter";

import timeData from '../assets/sn_d_tot.json'
import basicData from '../assets/data_view.json';
import sliceData from '../assets/slice_info.json';
// import nftData from '../assets/data.csv';
// import cpData from '../assets/data/control_panel.json';
import nftData from '../assets/run_full_1/preferential_attachment.json';
import cpData from '../assets/run_full_1/control_panel.json';
import flow_data from '../assets/run_full_1/substitution_flow.json';

export default {
  name: "home_view",
  data () {
    return {
      msgH: null,
      groupData: null,
      cpData: null,
      flow_data: null,
    };
  },
  computed: {
    initSign () {
      this.cpData = cpData;
      this.flow_data = flow_data;
      // console.log(this.cpData)
      return this.cpData != null;
    },
    loadingText () {
      return "Loading"
      // return "Loading:    " + 'Route: \n' +
      //     !!this.route + '   Station: \n'+ !!this.station + '   Alldata: \n'+ !!this.alldata
    }
  },
  mounted () {
    // const dataStore = useDataStore();
    // dataStore.fetchHello();
    // this.msgH = dataStore.msg;
  },
  methods: {
    fetchData () {
    }
  },
  components: { Main }
};
</script>
<style scoped>
.boundary {
  /*border-style: dashed;*/
  border-style: solid;
  border-color: #d3dce6;
  border-width: 0.5px;
  border-radius: 3px;
}
</style>
