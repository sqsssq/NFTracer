<template>
    <div style="height: 100%">
        <div class="frameworkTitle">
            <span class="title" style="float: left;">
                <svg t="1676053813985" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
                    p-id="37153" width="20" height="20">
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
                            text-anchor="middle">{{ i == 0 ? '-1' : i == 5 ? '0' : '+1' }}</text>
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
                                        :stroke="'none'" :fill="colormap1[arc_i == 0 ? 2 : arc_i == 1 ? 1 : 0]"></path>
                                    <path v-for="(arc_item, arc_i) in outLegendArc" :key="'arc' + arc_i" :d="arc_item"
                                        :stroke="'none'" :transform="translate(0, 0, -60)"
                                        :fill="arc_i == 0 ? '#a30e24' : arc_i == 1 ? '#2a57f7' : '#fc7b5c'"></path>
                                    <path d="M 0 -15 L 60 -15" fill="none" stroke="#C6BCBC"></path>
                                    <path d="M 18 10 L 60 10" fill="none" stroke="#C6BCBC"></path>
                                    <text x="55" y="-15" dx="0.5em" dy="0.3em" font-size="14">#300</text>
                                    <text x="55" y="10" dx="0.5em" dy="0.3em" font-size="14">-0.8</text>
                                </g>
                                <g :transform="translate(0, 10, 0)">
                                    <text x="-30" y="35" dx="0.5em" dy="0.3em" font-size="14">Group:</text>
                                    <text x="17" y="35" dx="0.5em" dy="0.3em" font-size="14" text-decoration="underline">1 /
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
                            <g v-for="(item, i) in correlationData" :key="'correlation_circle_' + i"
                                :transform="translate(item.x, item.y, 0)">
                                <path v-for="(a_item, a_i) in item.outArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                    :fill="a_item.fill"></path>
                                <path v-for="(a_item, a_i) in item.innerArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                    :fill="a_item.fill"></path>
                            </g>
                        </g>
                        <g>
                            <g v-for="(item, i) in textPlace" :key="'cross_text' + i"
                                :transform="translate(item.pos[0], item.pos[1], 0)">
                                <g clip-path="url(#clipPath)" :transform="translate(-40, -15, 0)">
                                    <image :href="item.link" x="0" y="0" height="30" width="30" />
                                </g>
                                <!-- <text :x="0" :y="0" font-size="14" text-anchor="end" dx="-0.5em" dy="-0.5em">
                                    {{ item.name }}
                                </text> -->
                            </g>
                        </g>
                    </svg>
                </div>
                <div ref="correlationTable"
                    style="float: right; position: absolute; right: 0px; top: 0px; width: calc(35% - 10px); height: calc(100%);">
                    <svg width="100%" height="100%">
                        <g transform="translate(0, 20)">
                            <!-- <text x="95" y="20" font-size="14">#Holders-#Buyers-#Sellers</text> -->
                            <text font-size="14" x="45" y="20" text-anchor="middle">#Seller</text>
                            <text font-size="14" x="135" y="20" text-anchor="middle">#Buyer</text>
                            <text font-size="14" x="225" y="20" text-anchor="middle">#Holder</text>
                            <path :d="'M 0 30 L ' + (ctWidth - 1) + ' 30'" fill="none" stroke="#C6BCBC"></path>
                            <path :d="'M 0 ' + (ctHeight - 40) + ' L ' + (ctWidth - 1) + ' ' + (ctHeight - 40)" fill="none"
                                stroke="#C6BCBC"></path>
                            <path :d="'M 0 30 L 0 ' + (ctHeight - 40)" fill="none" stroke="#C6BCBC"></path>
                            <path :d="'M  ' + (ctWidth / 3) + '  30 L  ' + (ctWidth / 3) + '  ' + (ctHeight - 40)"
                                fill="none" stroke="#C6BCBC"></path>
                            <path :d="'M  ' + (ctWidth * 2 / 3) + '  30 L ' + (ctWidth * 2 / 3) + '  ' + (ctHeight - 40)"
                                fill="none" stroke="#C6BCBC"></path>
                            <path :d="'M  ' + (ctWidth - 1) + '  30 L  ' + (ctWidth - 1) + '  ' + (ctHeight - 40)"
                                fill="none" stroke="#C6BCBC"></path>
                        </g>
                        <g>
                            <g v-for="(item, i) in textPlace" :key="'cross_text' + i"
                                :transform="translate(0, item.pos[1] + 25, 0)">
                                <!-- <g clip-path="url(#clipPath)" :transform="translate(-120, -20, 0)">
                                    <image
                                        xlink:href="https://img0.baidu.com/it/u=546973192,19042771&fm=253&fmt=auto&app=120&f=PNG?w=500&h=500"
                                        x="0" y="0" height="30" width="30" />
                                </g> -->
                                <g>
                                    <rect v-for="(r_item, r_i) in item.rectData" :key="'pro_bar_' + r_i" :x="r_item.x"
                                        :y="-12.5" :width="r_item.w" :height="r_item.h" :fill="r_item.fill"></rect>
                                </g>
                                <!-- <text :x="0" :y="0" font-size="14" text-anchor="start" dx="-0.5em" dy="0.5em">
                                    {{ item.name }}
                                </text> -->
                            </g>
                        </g>
                    </svg>
                </div>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
            <div style="width: 100%; height: 54%; margin-top: 5px;">
                <div style="height: 35px;">
                    [Impact dynamics of individual NFT project]
                    <span style="float: right; position: relative; top: 1px;">
                        Sort by:
                        <el-select v-model="sortValue" class="m-2" placeholder="Select"
                            style="width: 85px; --el-border-color: white;">
                            <el-option v-for="item in sortOptions" :key="item" :label="item" :value="item" />
                        </el-select>
                    </span>
                </div>
                <div style="height: calc(100% - 35px); width: 100%;">
                    <div ref="nameSpace" id="nameSpace" style="float: left; width: 15%; height: 92%;overflow-y: auto;">
                        <svg :width="nameWidth" :height="pjWidth * projectNum / 2">
                            <g v-for="(item, i) in timeData" :key="'time_x' + i">
                                <g :transform="translate(nameWidth / 2, i * pjHeight / 2 + 100, 0)">

                                    <path v-for="(a_item, a_i) in item.name.outArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                        :fill="a_item.fill" :stroke="a_item.stroke == 1 ? '#534f4f' : 'none'"></path>
                                    <path v-for="(a_item, a_i) in item.name.innerArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                        :fill="a_item.fill"></path>

                                    <clipPath id="clipPath2">
                                        <circle :cx="item.name.img_r" :cy="item.name.img_r" :r="item.name.img_r"></circle>
                                    </clipPath>
                                    <g clip-path="url(#clipPath2)"
                                        :transform="translate(-item.name.img_r, -item.name.img_r, 0)">
                                        <image :href="item.name.link" x="0" y="0" :height="item.name.img_r * 2"
                                            :width="item.name.img_r * 2" />
                                    </g>
                                </g>

                                <g :transform="translate(nameWidth / 2, i * pjHeight / 2 + 200, 0)">
                                    <text font-size="14" text-anchor="middle">Time Slot: </text>
                                    <text font-size="14" text-anchor="middle" text-decoration="underline" dy="2em">{{
                                        item.name.time }}</text>
                                </g>
                                <g>
                                    <path :d="'M0 ' + (pjHeight / 2 * i) + ' L' + nameWidth + ' ' + (pjHeight / 2 * i)"
                                        fill="none" stroke="#e0dede"></path>
                                </g>
                            </g>
                        </svg>
                    </div>
                    <div></div>
                    <div ref="timeSpace" id="timeSpace" style="float: right; width: 85%; height: 92%; overflow: auto;">

                        <svg :width="pjWidth * 2" :height="pjHeight * projectNum / 2">
                            <g v-for="(item, i) in timeData" :key="'time_x' + i"
                                :transform="translate(0, pjHeight / 2 * i, 0)">

                                <g :transform="translate(0, pjWidth / 2 * 0.5, 0)">
                                    <path v-for="(a_item, a_i) in item.l2Data" :key="'corr_out_' + a_i" :d="a_item.d"
                                        :fill="'none'" :stroke="a_item.fill"></path>
                                </g>
                                <g>

                                    <path v-for="(a_item, a_i) in item.l1Data" :key="'corr_out_' + a_i" :d="a_item.d"
                                        :fill="a_item.fill" :fill-opacity="0.5" :stroke="a_item.fill"></path>
                                </g>
                                <g>

                                    <path :d="'M0 ' + (pjHeight / 2 * 0.5) + ' L' + pjWidth * 2 + ' ' + (pjHeight / 2 * 0.5)"
                                        fill="none" stroke="#534f4f"></path>

                                    <path :d="'M0 ' + (pjHeight / 2 * 0.9) + ' L' + pjWidth * 2 + ' ' + (pjHeight / 2 * 0.9)"
                                        fill="none" stroke="#534f4f"></path>
                                    <path :d="'M0 ' + (pjHeight / 2) + ' L' + pjWidth * 2 + ' ' + (pjHeight / 2)" fill="none"
                                        stroke="#e0dede"></path>
                                </g>
                            </g>
                        </svg>
                    </div>
                    <div ref="legendSpace" id="legendSpace"
                        style="float: right; width: 85%; height: 8%; overflow-x: auto;">
                        <svg :width="pjWidth * 2" :height="legendHeight">

                        </svg>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>
<script>
import { scaleLinear } from 'd3-scale';
// import time from 'd3-scale/src/time';
import { select } from 'd3-selection';
import { arc, area, curveBasis, line, pie } from 'd3-shape';

export default {
    name: 'APP',
    props: ['groupData'],
    data () {
        return {
            cvHeight: 0,
            cvWidth: 0,
            ctHeight: 0,
            ctWidth: 0,
            nameWidth: 0,
            pjWidth: 0,
            pjHeight: 0,
            legendHeight: 0,
            sortValue: 'Longevity',
            sortOptions: ['Longevity'],
            pieLegendData: [90, 135, 135],
            pieLegend: [],
            legendArc: [],
            outLegendArc: [],
            nftName: ['CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks'],
            lineData: [],
            textPlace: [],
            colormap1: ['#b69acb', '#6f319b', '#c9c9c9'],
            colorType: {
                seller: '#b69acb',
                buyer: '#6f319b',
                holder: '#c9c9c9'
            },
            colormap2: ['#2301d1', '#2a57f7', '#4186f9', '#5aaffa', '#79d2fc', '#ffffec', '#fc7b5c', '#fc4443', '#f4313b', '#d52133', '#a30e24'],
            correlationData: [],
            axisColor: { 'M1': '#EA7C16', 'M3': '#61bad6', 'IMP': '#d77a78', 'M2': '#53ad92' },
            tableRect: [],
            timeData: [],
            projectNum: 1
        }
    },
    methods: {
        translate (x, y, deg) {
            return `translate(${x}, ${y}) rotate(${deg})`;
        },
        dataProcess () {
            let arcs = pie().sort(null)(this.pieLegendData);
            let outData = [1, 1, 1];
            let outArcs = pie().padAngle(0.9).sort(null)(outData);
            // console.log(outArcs);
            let legendArc = [];
            for (let d of arcs) {
                // d.innerRadius = 10;
                // d.outerRadius = 20;
                // let darcs = arc()(d);
                // legendArc.push(darcs);
                d.innerRadius = 0;
                d.outerRadius = 15;

                let darcs = arc()(d);
                legendArc.push(darcs);
            }
            let outLegendArc = [];
            for (let d of outArcs) {
                // console.log(d);
                let outarc = arc().innerRadius(18).outerRadius(20).cornerRadius(5)(d);
                outLegendArc.push(outarc);
            }
            return [legendArc, outLegendArc];
        },
        calcCorrelation (data, r, x, y) {
            let tmpData = [];
            for (let i in data.inner) {
                tmpData.push({
                    type: i,
                    value: data.inner[i]
                });
            }
            let pieData = pie().sort(null).value(d => d.value)(tmpData);
            let innerArc = [];
            for (let i in pieData) {
                innerArc.push({
                    data: pieData[i].data,
                    d: arc().innerRadius(0).outerRadius(r)(pieData[i]),
                    fill: this.colorType[pieData[i].data.type]
                })
            }
            let outArc = [];
            let angle = 45;
            let colorScale = scaleLinear([-1, 1], [0, 10]);
            let cnt = 0;
            for (let i in data.outer) {
                outArc.push({
                    d: arc().innerRadius(r + 3).outerRadius(r + 5).cornerRadius(5)({
                        startAngle: ((cnt * 120) - angle / 2) * Math.PI / 180,
                        endAngle: ((cnt * 120) + angle / 2) * Math.PI / 180,
                        index: cnt++,
                        padAngle: 0,
                        value: 1
                    }),
                    fill: this.colormap2[(colorScale(data.outer[i])).toFixed(0)],
                    type: i
                });
            }
            return {
                x: x,
                y: y,
                outArc: outArc,
                innerArc: innerArc
            }
        },
        calcIndividual (data, r, x, y) {
            let tmpData = [];
            for (let i in data.inner) {
                tmpData.push({
                    type: i,
                    value: data.inner[i]
                });
            }
            let pieData = pie().sort(null).value(d => d.value)(tmpData);
            let innerArc = [];
            for (let i in pieData) {
                innerArc.push({
                    data: pieData[i].data,
                    d: arc().innerRadius(0).outerRadius(r - 12)(pieData[i]),
                    fill: this.colorType[pieData[i].data.type]
                })
            }
            let outArc = [];
            let angle = 45;
            let colorScale = scaleLinear([-1, 1], [0, 10]);
            let cnt = 0;
            let cOrder = ['M1', 'M3', 'IMP', 'M2'];
            // console.log(data);
            for (let i in cOrder) {
                outArc.push({
                    d: arc().innerRadius(r - 8).outerRadius(r)({
                        startAngle: ((cnt * 90)) * Math.PI / 180,
                        endAngle: ((cnt * 90) + data.outer[cOrder[i]] * 90) * Math.PI / 180,
                        index: cnt,
                        padAngle: 0,
                        value: 1
                    }),
                    fill: this.axisColor[cOrder[i]],
                    type: i,
                    stroke: 0
                });
                outArc.push({
                    d: arc().innerRadius(r - 8).outerRadius(r)({
                        startAngle: ((cnt * 90)) * Math.PI / 180,
                        endAngle: ((cnt * 90) + 90) * Math.PI / 180,
                        index: cnt++,
                        padAngle: 0,
                        value: 1
                    }),
                    fill: 'none',
                    type: i,
                    stroke: 1
                });
            }
            return {
                x: x,
                y: y,
                outArc: outArc,
                innerArc: innerArc,
                link: data.link,
                img_r: r / 2,
                name: data.name,
                time: data.time
            }
        },
        calcIndividualProject (data) {
            this.projectNum = data.length;
            // console.log(data);
            // let nameSvg = select('#nameSpace').append('svg').attr('id', 'nameSvg').attr('width', this.nameWidth).attr('height', this.pjHeight * data.length / 2);
            // let timeSvg = select('#timeSpace').append('svg').attr('id',  'timeSvg').attr('width', this.pjWidth * 2).attr('height', this.pjHeight * data.length / 2);
            // let legendSvg = select('#legendSpace').append('svg').attr('id', 'legendSvg').attr('width', this.pjWidth * 2).attr('height', this.legendHeight - 15);
            let xScale = scaleLinear([0, 23], [0, this.pjWidth * 2]);
            let areaScale = scaleLinear([0, 1], [this.pjHeight * 0.5 / 2, 0]);
            let lineScale = scaleLinear([0, 1], [this.pjHeight * 0.4 / 2, 0]);
            let areaGenerate = area().x(d => xScale(d.x)).y1(d => areaScale(d.y)).y0(areaScale(0)).curve(curveBasis);
            let lineGenerate = line().x(d => xScale(d.x)).y(d => lineScale(d.y)).curve(curveBasis);
            let timeData = []
            for (let i in data) {
                // console.log(data[i])
                let nameData = this.calcIndividual({
                    inner: {
                        holder: 130,
                        buyer: 100,
                        seller: 60
                    },
                    outer: {
                        M1: 0.7,
                        M2: 0.3,
                        M3: 0.5,
                        IMP: 0.2
                    },
                    link: data[i]['logo_link'],
                    name: data[i]['﻿Project Name'],
                    time: 'Jan. 20 - Feb. 05'
                }, this.nameWidth * 0.8 / 2, 0, 0);
                let lineData1 = [];
                let lineData2 = [];

                for (let i in this.colorType) {
                    let tLineData = [];
                    for (let j = 0; j < 24; ++j) {
                        tLineData.push({ x: j, y: Math.random() });
                    }
                    console.log(tLineData);
                    lineData1.push({
                        d: areaGenerate(tLineData),
                        fill: this.colorType[i],
                        type: i
                    })
                }
                for (let i in this.axisColor) {
                    let tLineData = [];
                    for (let j = 0; j < 24; ++j) {
                        tLineData.push({ x: j, y: Math.random() });
                    }
                    lineData2.push({
                        d: lineGenerate(tLineData),
                        fill: this.axisColor[i],
                        type: i
                    })
                }
                timeData.push({
                    name: nameData,
                    l1Data: lineData1,
                    l2Data: lineData2
                });
            }
            return timeData;

        },
        // calcCorrelationData (data)
        calcLine (data) {
            let lineScaleY = scaleLinear([-1, data.length], [this.cvHeight - 10 - (this.cvWidth - 3 - 0), this.cvHeight - 10]);
            let lineScaleX = scaleLinear([-1, data.length], [0, this.cvWidth - 3]);
            let lineData = [];
            let textPlace = [];
            const lineGenerate = line()
                .x(d => lineScaleX(d[0]))
                .y(d => lineScaleY(d[1]));
            function getRandom (n, m) {
                var num = Math.floor(Math.random() * (m - n + 1) + n)
                return num
            }
            let rectScale = scaleLinear([0, 100], [0, this.ctWidth / 3 - 5]);
            for (let i = -1; i < data.length + 1; i++) {

                if (i < data.length && i > -1) {
                    let cnt_len = 0;
                    let tableRect = []

                    for (let j = 0; j < 3; ++j) {
                        let rw = rectScale(getRandom(0, 100))
                        tableRect.push({
                            x: cnt_len,
                            w: rw,
                            h: 25,
                            y: lineScaleY(i) - 15,
                            fill: this.colormap1[j]
                        })
                        cnt_len += this.ctWidth / 3;
                    }
                    //  console.log(tableRect);
                    textPlace.push({
                        rectData: tableRect,
                        name: data[i]['﻿Project Name'],
                        link: data[i]['logo_link'],
                        pos: [lineScaleX(data.length - 1 - i), lineScaleY(i)]
                    });
                }
                lineData.push(lineGenerate([[i, data.length - 1 - i], [i, data.length]]));
                lineData.push(lineGenerate([[data.length - i - 1, i], [data.length, i]]));
            }
            let sizeScale = scaleLinear([0, 1], [0.5, 0.7]);
            for (let i = 0; i < data.length; i++) {
                for (let j = data.length - i; j < data.length; j++) {
                    if (Math.random() > 0.8) {

                        this.correlationData.push(this.calcCorrelation({
                            inner: {
                                holder: Math.random(50, 100),
                                buyer: Math.random(50, 100),
                                seller: Math.random(50, 100)
                            },
                            outer: {
                                c1: Math.random(-1, 1),
                                c2: Math.random(-1, 1),
                                c3: Math.random(-1, 1)
                            }
                        }, sizeScale(Math.random()) * (lineScaleX(1) - lineScaleX(0)) / 2, lineScaleX(i), lineScaleY(j)))
                    }
                }
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
        this.ctHeight = this.$refs.correlationTable.offsetHeight;
        this.ctWidth = this.$refs.correlationTable.offsetWidth;
        this.pjHeight = this.$refs.timeSpace.offsetHeight;
        this.pjWidth = this.$refs.timeSpace.offsetWidth;
        this.legendHeight = this.$refs.legendSpace.offsetHeight;
        this.nameWidth = this.$refs.nameSpace.offsetWidth;
        // this.dataprocess();
        // console.log(this.barHeight, this.barWidth)

        [this.legendArc, this.outLegendArc] = this.dataProcess();
        // console.log(this.legendArc)
        let group = {};
        for (let i in this.groupData) {
            if (typeof (group[this.groupData[i].Group]) === 'undefined') {
                group[this.groupData[i].Group] = [];
            }
            group[this.groupData[i].Group].push(this.groupData[i]);
        }
        [this.lineData, this.textPlace] = this.calcLine(group[1]);
        // this.calcIndividual({
        //     inner: {
        //         holder: 130,
        //         buyer: 100,
        //         seller: 60
        //     },
        //     outer: {
        //         M1: 0.7,
        //         M2: 0.3,
        //         M3: 0.5,
        //         IMP: 0.2
        //     },
        //     link: 'https://lh3.googleusercontent.com/XHZY9623keDQqFSDHKqOdcjD99Y7N82K1egYRM2Mm1Z-Jxn5myrkKiC5NBktWKStVtTzDzwELy9dNpzTWJTIkLsdMIxUHI86jduQ=s120',
        //     name: 'BAYC',
        //     time: 'Jan. 20 - Feb. 05'
        // }, 50, 100, 100);
        this.timeData = this.calcIndividualProject(group[1]);
        console.log(this.timeData)
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

#nameSpace::-webkit-scrollbar {
    display: none;
}</style>
