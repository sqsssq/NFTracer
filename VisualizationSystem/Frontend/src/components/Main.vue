<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2022-11-20 23:25:35
 * @LastEditTime: 2023-03-11 17:41:24
-->
<template>
    <div id="navBar">
        <div style=" height: 40px; margin-top: calc((4.3vh - 40px) / 2);">
            <div style="float: left;">
                <svg width="42" height="41" viewBox="0 0 42 41" fill="none" xmlns="http://www.w3.org/2000/svg"
                    xmlns:xlink="http://www.w3.org/1999/xlink">
                    <mask id="mask0_453_50543" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="41"
                        height="41">
                        <rect width="40" height="40" fill="url(#pattern0)" />
                    </mask>
                    <g mask="url(#mask0_453_50543)">
                        <rect x="2" width="40" height="40" fill="white" />
                    </g>
                    <defs>
                        <pattern id="pattern0" patternContentUnits="objectBoundingBox" width="1" height="1">
                            <use xlink:href="#image0_453_50543" transform="scale(0.00195312)" />
                        </pattern>
                        <image id="image0_453_50543" width="512" height="512"
                            xlink:href="data:image/png;base64,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" />
                    </defs>
                </svg>
                <span style="position: relative; top: -11px;">NFTuner</span>

            </div>
            <div style="height: 100%;float: right;">

                <span style="position: relative; top: -3px;">Visual Analytics for substitutive system in NFT
                    marketspace</span>
            </div>
        </div>
    </div>
    <div style="height: calc(95.7vh - 0px); width: calc(100% - 0px); background-color: #E0DEDE;">
        <div class="framework" id="PropensityAnalysis"
            style="position: absolute; left: calc(5px); top: calc(5px); height: calc(67vh - 10px); width: calc(20%);">
            <PropensityAnalysis :groupData="groupData" />
        </div>
        <div class="framework" id="MechanismAnalysis"
            style="position: absolute; left: calc(5px); top: calc(67vh); height: calc(95.7vh - 5px - 67vh); width: calc(66.2vw + 5px);">
            <MechanismAnalysis :groupData="groupData" />
        </div>
        <div class="framework" id="ModelExplainer"
            style="position: absolute; left: calc(5px + 20vw + 5px); top: calc(5px); height: calc((67vh) - 10px); width: calc(46.2vw);">
            <SubstitutionView :groupData="groupData"/>
        </div>
        <div class="framework" id="CorrelationView"
            style="position: absolute; left: calc(66.2vw + 15px);  top: calc(5px); height: calc(95.7vh - 10px); width: calc(100vw - 66.2vw - 20px);">

            <ImpactDynamicView :groupData="groupData" />
        </div>
    </div>
</template>
<script>
import { dataService } from '@/service'

import PropensityAnalysis from './PropensityAnalysis.vue';
import MechanismAnalysis from './MechanismAnalysis.vue';
import SubstitutionView from './SubstitutionView.vue';
import ImpactDynamicView from './ImpactDynamicView.vue';
export default {
    name: "APP",
    props: ["groupData"],
    data () {
        return {
            msg1: "Hello, main!"
        };
    },
    methods: {},
    created () {
    },
    mounted () {
        // console.log("groupData", this.groupData);

    },
    components: { PropensityAnalysis, MechanismAnalysis, SubstitutionView, ImpactDynamicView }
}
</script>
<style>
.framework {
    /* margin: 5px; */
    border: 0px solid rgb(105, 119, 122);
    border-radius: 6.91892px;
    background-color: white;
    /* background-color: #2b2b2b; */

    /* border-color: rgb(237, 237, 238); */
    /* border-color: ; */

    /* -webkit-box-shadow: 0px 3px 3px 2px #bdbaba;
    -moz-box-shadow: 0px 3px 3px 2px #bdbaba;
    box-shadow: 0px 3px 3px 2px #bdbaba; */

    /* height: calc(50% - 30px);
    width: calc(50% - 40px); */
    /* margin-top: 10px; */
    /* margin-left: 30px; */
}

.framework .frameworkTitle {
    /* background-color: rgb(151, 196, 208); */
    height: 40px;
    padding-left: 10px;
    padding-right: 10px;
    /* width: 100%; */
}

.framework .frameworkBody {
    /* background-color: #000; */
    height: calc(100% - 40px);
    font-size: 16px;
    color: #534F4F;
    font-family: Arial, Helvetica, sans-serif;
    /* width: 100%; */
    /* background-color: #4C87EC; */
    padding: 0px 10px 10px 10px;
}

.framework .frameworkTitle .title {
    /* float: left;
    width: fit-content;

    background-color: rgb(105, 119, 122);
    height: 40px;

    font-weight: bold;
    font-size: 24px;
    color: white;
    padding-left: 10px;
    padding-right: 3px;
    font-family: 'KoHo';
    line-height: 35px; */
    font-family: 'KoHo';
    font-style: normal;
    font-weight: bold;
    font-size: 20px;
    line-height: 23px;
    display: flex;
    align-items: center;
    text-align: center;
    height: 100%;

    color: #534F4F;

}

.framework .frameworkTitle .titleTriangle {
    /* position: absolute;
    left: 180px; */
    /* display: inline; */
    float: left;
    width: 0;
    height: 0;
    border-color: transparent rgb(105, 119, 122);
    border-width: 0px 0px 40px 35px;
    border-style: solid;
}

#navBar {
    background-color: rgba(83, 79, 79);
    /* background-color: rgba(0, 0, 0, 0.8); */
    /* padding-left: 36%; */
    /* text-algin: center; */
    text-align: left;
    font-weight: bold;
    color: white;
    font-size: 28px;
    height: calc(4.3%);
    padding-top: 3px;
    padding-bottom: 5px;
    /* padding-top: 0.5%;
    padding-bottom: 0.5%; */
    padding-left: 10px;
    padding-right: 10px;
    /* font-family: STHeiti; */
    font-family: 'KoHo', 'Avenir', Helvetica, Arial, sans-serif;
}
</style>
