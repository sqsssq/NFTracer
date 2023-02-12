<template>
    <div style="height: 100%">
        <div class="frameworkTitle">
            <span class="title" style="float: left;">
                <svg t="1676053813985" class="icon" viewBox="0 0 1024 1024" version="1.1"
                    xmlns="http://www.w3.org/2000/svg" p-id="37153" width="20" height="20">
                    <path
                        d="M170.666667 42.666667l682.666667 0q52.992 0 90.496 37.504t37.504 90.496l0 682.666667q0 52.992-37.504 90.496t-90.496 37.504l-682.666667 0q-52.992 0-90.496-37.504t-37.504-90.496l0-682.666667q0-52.992 37.504-90.496t90.496-37.504zM896 742.997333l-213.333333-213.333333-366.336 366.336 537.002667 0q17.664 0 30.165333-12.501333t12.501333-30.165333l0-110.336zM853.333333 128l-682.666667 0q-17.664 0-30.165333 12.501333t-12.501333 30.165333l0 682.666667q0 17.664 12.501333 30.165333t30.165333 12.501333l25.002667 0 486.997333-486.997333 213.333333 213.333333 0-451.669333q0-17.664-12.501333-30.165333t-30.165333-12.501333zM341.333333 213.333333q52.992 0 90.496 37.504t37.504 90.496-37.504 90.496-90.496 37.504-90.496-37.504-37.504-90.496 37.504-90.496 90.496-37.504zM341.333333 298.666667q-17.664 0-30.165333 12.501333t-12.501333 30.165333 12.501333 30.165333 30.165333 12.501333 30.165333-12.501333 12.501333-30.165333-12.501333-30.165333-30.165333-12.501333z"
                        p-id="37154" font-size="14"></path>
                </svg>
                &nbsp; Impact Dynamic View
            </span>
            <span style="float: right; position: relative; top: -2px; font-size: 16px;">
                <svg height="27" width="260" transform="translate(0, 10)">
                    <g v-for="(item, i) in colormap1" :key="'icolor' + i" :transform="translate(20, 0, 0)">
                        <rect :x="0 + i * 40" :y="2" :width="9" :height="9" :fill="item" :stroke="'#534f4f'"></rect>
                        <text :x="0 + i * 40 + 4.5" :y="23" font-size="12" text-anchor="middle">{{ i == 0 ? 'Sell' : i
                        == 1 ? 'Buy' : 'Hold' }}</text>
                    </g>
                    <g v-for="(item, i) in colormap2" :key="'icolor' + i" :transform="translate(140, 0, 0)">
                        <rect :x="0 + i * 11" :y="1" :width="11" :height="11" :fill="item" :stroke="'none'"></rect>
                        <text v-if="i == 0 || i == 5 || i == 10" :x="0 + i * 11 + 5.5" :y="23" font-size="12"
                            text-anchor="middle">{{ i == 0 ? '-1' : i == 6 ? '0' : '+1' }}</text>
                    </g>
                </svg>
            </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
        </div>
        <div class="frameworkBody">
            <div style="width: 100%; height: 46%; margin-top: 5px;">
                <div>
                    [Preferential attachment view]
                </div>
                <div ref="correlationView" style="position: relative; left: 0px; width: 65%; height: calc(100% - 35px)">
                    <svg width="100%" height="100%">
                        <defs>
                            <clipPath id="clipPath">
                                <circle :cx="15" :cy="15" :r="15"></circle>
                            </clipPath>
                        </defs>

                        <g :transform="translate(30, 50, 0)">
                            <g>
                                <g>
                                    <path v-for="(arc_item, arc_i) in legendArc" :key="'arc' + arc_i" :d="arc_item"
                                        :stroke="'none'"
                                        :fill="colormap1[arc_i == 0 || arc_i == 1 ? 2 : arc_i == 2 || arc_i == 3 ? 1 : 0]"
                                        :opacity="arc_i % 2 == 1 ? 1 : 0.5"></path>
                                    <path d="M 0 -20 L 60 -20" fill="none" stroke="#C6BCBC"></path>
                                    <path d="M 0 10 L 60 10" fill="none" stroke="#C6BCBC"></path>
                                    <text x="55" y="-20" dx="0.5em" dy="0.3em" font-size="14">#400</text>
                                    <text x="55" y="10" dx="0.5em" dy="0.3em" font-size="14">#200</text>
                                </g>
                                <g :transform="translate(0, 10, 0)">
                                    <text x="-30" y="35" dx="0.5em" dy="0.3em" font-size="14">Group:</text>
                                    <text x="17" y="35" dx="0.5em" dy="0.3em" font-size="14"
                                        text-decoration="underline">1 /
                                        user selected</text>
                                    <text x="-30" y="60" dx="0.5em" dy="0.3em" font-size="14">Time Slot:</text>
                                    <text x="37" y="60" dx="0.5em" dy="0.3em" font-size="14"
                                        text-decoration="underline">Jan. 20 - Feb. 05</text>
                                </g>
                            </g>
                        </g>
                        <g>
                            <path v-for="(item, i) in lineData" :key="'cross_line' + i" :d="item" fill="none"
                                stroke="#C6BCBC"></path>
                        </g>
                        <g>
                            <g v-for="(item, i) in textPlace" :key="'cross_text' + i"
                                :transform="translate(item.pos[0], item.pos[1], 0)">
                                <g clip-path="url(#clipPath)" :transform="translate(-120, -20, 0)">
                                    <image
                                        xlink:href="https://img0.baidu.com/it/u=546973192,19042771&fm=253&fmt=auto&app=120&f=PNG?w=500&h=500"
                                        x="0" y="0" height="30" width="30" />
                                </g>
                                <text :x="0" :y="0" font-size="14" text-anchor="end" dx="-0.5em" dy="0em">
                                    {{ item.name }}
                                </text>
                            </g>
                        </g>
                    </svg>
                </div>
                <div ref="correlationView" style="float: right; position: absolute; right: 0px; top: 0px; width: calc(35% - 10px); height: calc(100%); border: 1px solid red;">
                    <svg width="100%" height="100%">
                    </svg>
                </div>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
            <div style="width: 100%; height: 54%; margin-top: 5px;">
                [Impact dynamics of individual NFT project]
                <span style="float: right; position: relative; top: 1px;">
                    Sort by:
                    <el-select v-model="sortValue" class="m-2" placeholder="Select"
                        style="width: 85px; --el-border-color: white;">
                        <el-option v-for="item in sortOptions" :key="item" :label="item" :value="item" />
                    </el-select>
                </span>
            </div>

        </div>
    </div>
</template>
<script>
import { scaleLinear } from 'd3-scale';
import { select } from 'd3-selection';
import { arc, line, pie } from 'd3-shape';

export default {
    name: 'APP',
    props: [''],
    data () {
        return {
            cvHeight: 0,
            cvWidth: 0,

            sortValue: 'Longevity',
            sortOptions: ['Longevity'],
            pieLegendData: [90, 135, 135],
            pieLegend: [],
            legendArc: [],
            nftName: ['CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks'],
            lineData: [],
            textPlace: [],
            colormap1: ['#b69acb', '#6f319b', '#c9c9c9'],
            colormap2: ['#2301d1', '#2a57f7', '#4186f9', '#5aaffa', '#79d2fc', '#ffffec', '#fc7b5c', '#fc4443', '#f4313b', '#d52133', '#a30e24'],
        }
    },
    methods: {
        translate (x, y, deg) {
            return `translate(${x}, ${y}) rotate(${deg})`;
        },
        dataprocess () {
            let arcs = pie().sort(null)(this.pieLegendData);
            let legendArc = [];
            for (let d of arcs) {
                d.innerRadius = 10;
                d.outerRadius = 20;
                let darcs = arc()(d);
                legendArc.push(darcs);
                d.innerRadius = 0;
                d.outerRadius = 10;
                darcs = arc()(d);
                legendArc.push(darcs);
            }
            return legendArc;
        },
        calcLine (data) {
            let lineScaleY = scaleLinear([0, data.length - 1], [25, this.cvHeight - 10]);
            let lineScaleX = scaleLinear([0, data.length - 1], [120, this.cvWidth - 3]);
            let lineData = [];
            let textPlace = [];
            const lineGenerate = line()
                .x(d => lineScaleX(d[0]))
                .y(d => lineScaleY(d[1]));

            for (let i = 0; i < data.length; i++) {
                if (1) {
                    textPlace.push({
                        name: data[i],
                        pos: [lineScaleX(data.length - 1 - i), lineScaleY(i)]
                    });
                }
                lineData.push(lineGenerate([[i, data.length - 1 - i], [i, data.length - 1]]));
                lineData.push(lineGenerate([[data.length - i - 1, i], [data.length - 1, i]]));
            }
            // console.log(lineData);
            return [lineData, textPlace];

        }
    },
    created () {
    },
    mounted () {
        this.cvHeight = this.$refs.correlationView.offsetHeight;
        this.cvWidth = this.$refs.correlationView.offsetWidth;
        // this.dataprocess();
        // console.log(this.barHeight, this.barWidth)

        this.legendArc = this.dataprocess();
        [this.lineData, this.textPlace] = this.calcLine(this.nftName)
        // console.log(this.legendArc)

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
