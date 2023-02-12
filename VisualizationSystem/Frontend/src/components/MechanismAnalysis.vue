<template>
    <div style="height: 100%">
        <div class="frameworkTitle">

            <span class="title">
                <svg t="1676053486623" class="icon" viewBox="0 0 1024 1024" version="1.1"
                    xmlns="http://www.w3.org/2000/svg" p-id="36215" width="20" height="20">
                    <path
                        d="M743.232 210.837333c144.896 144.896 149.781333 376.789333 14.656 527.573334l160.32 160.298666a8.533333 8.533333 0 0 1 0 12.074667l-33.173333 33.173333a8.533333 8.533333 0 0 1-12.074667 0l-161.557333-161.557333c-150.762667 120.746667-371.477333 111.253333-511.232-28.501333-149.973333-149.973333-149.973333-393.109333 0-543.061334 149.973333-149.973333 393.088-149.973333 543.061333 0z m-497.813333 45.248c-124.970667 124.970667-124.970667 327.594667 0 452.565334 124.970667 124.949333 327.594667 124.949333 452.565333 0 124.949333-124.970667 124.949333-327.594667 0-452.565334-124.970667-124.970667-327.594667-124.970667-452.565333 0z"
                        fill="#534f4f" p-id="36216"></path>
                </svg>
                &nbsp; <span style="position: relative; top: 0px; font-weight: 600;">Mechanism
                    Analysis</span></span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
        </div>
        <div class="frameworkBody">
            <div style="width: 100%; height: 26px; margin-top: 5px;">
                <span style="font-size: 12px;">
                    [F-1] &nbsp; <svg width="10" height="10" viewBox="0 0 10 10" fill="none"
                        xmlns="http://www.w3.org/2000/svg" transform="translate(0,1.5)">
                        <rect x="0" y="0" width="10" height="10" rx="1.29984" fill="#EA7C16" fill-opacity="0.7" />
                    </svg> &nbsp;
                    [F-2] &nbsp; <svg width="10" height="10" viewBox="0 0 10 10" fill="none"
                        xmlns="http://www.w3.org/2000/svg" transform="translate(0,1.5)">
                        <rect x="0" y="0" width="10" height="10" rx="1.29984" fill="#53ad92" fill-opacity="0.7" />
                    </svg> &nbsp;
                    [F-3] &nbsp; <svg width="10" height="10" viewBox="0 0 10 10" fill="none"
                        xmlns="http://www.w3.org/2000/svg" transform="translate(0,1.5)">
                        <rect x="0" y="0" width="10" height="10" rx="1.29984" fill="#61bad6" fill-opacity="0.7" />
                    </svg>
                </span>
                <span style="float: right; position: relative; top: 1px;">
                    Filter by:
                    <el-select v-model="filterValue" class="m-2" placeholder="Select"
                        style="width: 70px; --el-border-color: white;">
                        <el-option v-for="item in filterOptions" :key="item" :label="item" :value="item" />
                    </el-select>
                </span>
            </div>
            <div ref="attr_bar" style="width: 100%; height: calc((100% - 26px) / 3);">
                [F-1: Preferential attachment ]
                <svg id="attr_bar" width="100%" height="calc(100% - 30px)">
                    <rect v-for="(item, i) in attachmentData" :key="'bar' + i" :x="5 + i * (barWidth - 5) / 20" :y="barHeight - item" :height="item" :width="(barWidth - 5) / 20" stroke="#D9D9D9" fill="#D9D9D9"></rect><path :d="'M 5 ' +  barHeight + ' L ' + barWidth + ' ' + barHeight" fill="none" stroke="#534f4f"></path>
                </svg>
            </div>
            
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
            <div style="width: 100%; height: calc((100% - 26px) / 3);">
                [F-2: Recency]
                <svg width="100%" height="calc(100% - 30px)">
                    <rect v-for="(item, i) in recencyData" :key="'bar' + i" :x="5 + i * (barWidth - 5) / 20" :y="barHeight - item" :height="item" :width="(barWidth - 5) / 20" stroke="#D9D9D9" fill="#D9D9D9"></rect>
                    <path :d="'M 5 ' +  barHeight + ' L ' + barWidth + ' ' + barHeight" fill="none" stroke="#534f4f"></path>
                </svg>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
            <div style="width: 100%; height: calc((100% - 26px) / 3);">
                [F-3: Propensity]
                <svg width="100%" height="calc(100% - 30px)">
                    <rect v-for="(item, i) in propensityData" :key="'bar' + i" :x="5 + i * (barWidth - 5) / 20" :y="barHeight - item" :height="item" :width="(barWidth - 5) / 20" stroke="#D9D9D9" fill="#D9D9D9"></rect><path :d="'M 5 ' +  barHeight + ' L ' + barWidth + ' ' + barHeight" fill="none" stroke="#534f4f"></path>
                </svg>
            </div>
        </div>
    </div>
</template>
<script>
import { scaleLinear } from 'd3-scale';
import { select } from 'd3-selection';

export default {
    name: 'APP',
    props: [''],
    data() {
        return {
            filterValue: 'Group',
            filterOptions: ['Group'],
            attachmentData: [3, 2, 1, 5, 3, 4, 2, 4, 2, 1,3, 2, 1, 5, 3, 4, 2, 4, 2, 1],
            recencyData: [3, 2, 1, 5, 3, 4, 2, 4, 2, 1,3, 2, 1, 5, 3, 4, 2, 4, 2, 1],
            propensityData: [3, 2, 1, 5, 3, 4, 2, 4, 2, 1,3, 2, 1, 5, 3, 4, 2, 4, 2, 1],
            barHeight: 0,
            barWidth: 5
        }
    },
    methods: {
        dataprocess () {
            let yScale = scaleLinear([0,5], [0, this.barHeight]);
            for (let i in this.attachmentData) {
                this.attachmentData[i] = yScale(this.attachmentData[i]);
                this.recencyData[i] = yScale(this.recencyData[i]);
                this.propensityData[i] = yScale(this.propensityData[i]);
            }
            // console.log(this.attachmentData)
        }
    },
    created() {
    },
    mounted() {
        this.barHeight = this.$refs.attr_bar.offsetHeight - 30;
        this.barWidth = this.$refs.attr_bar.offsetWidth;
        this.dataprocess();
        // console.log(this.barHeight, this.barWidth)
    },
}
</script>
<style>

.el-input__suffix-inner i {
    border: 1px solid #dcdfe6;
}

.el-input__inner {

    text-decoration: underline;
}

.el-input__wrapper {
    padding-left: 0px;
    padding-right: 0px;
}

</style>
