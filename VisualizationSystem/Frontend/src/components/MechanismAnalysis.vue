<template>
    <div style="height: 100%">
        <div class="frameworkTitle">
    
            <span class="title" style="float: left;">
                                <svg t="1676053486623" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
                                    p-id="36215" width="20" height="20">
                                    <path
                                        d="M743.232 210.837333c144.896 144.896 149.781333 376.789333 14.656 527.573334l160.32 160.298666a8.533333 8.533333 0 0 1 0 12.074667l-33.173333 33.173333a8.533333 8.533333 0 0 1-12.074667 0l-161.557333-161.557333c-150.762667 120.746667-371.477333 111.253333-511.232-28.501333-149.973333-149.973333-149.973333-393.109333 0-543.061334 149.973333-149.973333 393.088-149.973333 543.061333 0z m-497.813333 45.248c-124.970667 124.970667-124.970667 327.594667 0 452.565334 124.970667 124.949333 327.594667 124.949333 452.565333 0 124.949333-124.970667 124.949333-327.594667 0-452.565334-124.970667-124.970667-327.594667-124.970667-452.565333 0z"
                                        fill="#534f4f" p-id="36216"></path>
                                </svg>
                                &nbsp; <span style="position: relative; top: 0px; font-weight: 600;">Mechanism Analysis</span>
            </span>
            <span style="float: right; position: relative; top: 3px; font-size: 16px;">
                
                                <span style="float: right;">
                                    <span style="margin-right: 20px;">
                                        [M-1] &nbsp; <svg width="15" height="15" viewBox="0 0 15 15" fill="none"
                                            xmlns="http://www.w3.org/2000/svg" transform="translate(0,3)">
                                            <rect x="0" y="0" width="15" height="15" rx="1.29984" fill="#EA7C16" fill-opacity="0.7" />
                                        </svg> &nbsp;
                                        [M-2] &nbsp; <svg width="15" height="15" viewBox="0 0 15 15" fill="none"
                                            xmlns="http://www.w3.org/2000/svg" transform="translate(0,3)">
                                            <rect x="0" y="0" width="15" height="15" rx="1.29984" fill="#53ad92" fill-opacity="0.7" />
                                        </svg> &nbsp;
                                        [M-3] &nbsp; <svg width="15" height="15" viewBox="0 0 15 15" fill="none"
                                            xmlns="http://www.w3.org/2000/svg" transform="translate(0,3)">
                                            <rect x="0" y="0" width="15" height="15" rx="1.29984" fill="#61bad6" fill-opacity="0.7" />
                                        </svg>&nbsp;
                                        [IMP] &nbsp; <svg width="15" height="15" viewBox="0 0 15 15" fill="none"
                                            xmlns="http://www.w3.org/2000/svg" transform="translate(0,3)">
                                            <rect x="0" y="0" width="15" height="15" rx="1.29984" fill="#d77a78" fill-opacity="0.7" />
                                        </svg>
                                    </span>
            <span style="margin-right: 220px;">
                                        Time Slot:
                                        <!-- <el-select v-model="filterValue" class="m-2" placeholder="Select"
                                            style="width: 70px; --el-border-color: white;">
                                            <el-option v-for="item in filterOptions" :key="item" :label="item" :value="item" />
                                        </el-select> -->
                                        <span style="text-decoration: underline; width: 200px; position: absolute; left: 90px; top: -3px;">
                                            {{ timeSelectionText }}
                                        </span>
    
            </span>
            <span>
                                        Select NFT Project:
                                        <el-select v-model="filterValue" class="m-2" placeholder="Select"
                                            style="width: 110px; --el-border-color: white;">
                                            <el-option v-for="item in filterOptions" :key="item.value" :label="item.label" :value="item.value" />
                                        </el-select>
                                    </span>
            </span>
            </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
        </div>
        <div class="frameworkBody" style="padding-bottom: 5px;">
            <!-- <div style="width: 100%; height: 26px; margin-top: 5px;">
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
                            </div> -->
    
            <div ref="attr_bar" style="width: 30%; height: calc(100%); float: left;">
                <svg v-show="showTag" id="attr_bar" width="100%" height="calc(100%)">
                                    <path :d="'M ' + (barWidth + 12) + ' ' + 10 + ' L ' + (barWidth + 12) + ' ' + (barHeight * 3 + 85)"
                                        fill="none" stroke="#c6bcbc"></path>
                
                                        
                                    <g :transform="translate(0, 2 * (barHeight + 29), 0)" id="m3Bar">
                                        <text x="5" y="20" fill="#534F4F">[M-3: Propensity]</text>
                                        <g :transform="translate(5, 25, 0)">
                                            
                                            <g>

                                            <rect v-for="(item, i) in propensityDataBar" :key="'bar' + i" :x="item.x" :y="item.y"
                                                :height="(barHeight - 3) - item.y" :width="item.w" stroke="white" fill="#D9D9D9">
                                                </rect>
                                            <g v-for="(r_item, r_i) in groupSet" :key="'sel_m' + r_i" :opacity="r_i == selectGroupTag ? 1: 0" :id="'sel_m3' + r_i">
                                            <rect v-for="(item, i) in groupSet[r_i].m3Bar" :key="'bar' + i" :x="item.x" :y="item.y"
                                                :height="(barHeight - 3) - item.y" :width="item.w" stroke="white" fill="#61bad6">
                                            </rect>
                                        </g>
                                            </g>
                                            <path :d="'M 20 ' + (barHeight - 3) + ' L ' + (barWidth - 10) + ' ' + (barHeight - 3)"
                                                fill="none" stroke="#534f4f">
                                            </path>
                                            <path :d="'M -5 ' + (barHeight + 5) + ' L ' + (barWidth - 5) + ' ' + (barHeight + 5)"
                                                fill="none" stroke="#c6bcbc" stroke-width="1"></path>
                                        </g>
                                    </g>
                                    <g :transform="translate(0, (barHeight + 29), 0)">
                                        <text x="5" y="20" fill="#534F4F">[M-2: Preferential attachment]</text>
                                        <g :transform="translate(5, 25, 0)" id="m1Bar">
                                            <rect v-for="(item, i) in attachmentDataBar" :key="'bar' + i" :x="item.x" :y="item.y"
                                                :height="(barHeight - 3) - item.y" :width="item.w" stroke="white" fill="#D9D9D9">
                                            </rect>
                                            <g v-for="(r_item, r_i) in groupSet" :key="'sel_m' + r_i" :opacity="r_i == selectGroupTag ? 1: 0" :id="'sel_m2' + r_i">
                                            <rect v-for="(item, i) in groupSet[r_i].m2Bar" :key="'bar' + i" :x="item.x" :y="item.y"
                                                :height="(barHeight - 3) - item.y" :width="item.w" stroke="white" fill="#53ad92">
                                            </rect>
                                        </g>
                                            <path :d="'M 20 ' + (barHeight - 3) + ' L ' + (barWidth - 10) + ' ' + (barHeight - 3)"
                                                fill="none" stroke="#534f4f">
                                            </path>
                                            <path :d="'M -5 ' + (barHeight + 5) + ' L ' + (barWidth - 5) + ' ' + (barHeight + 5)"
                                                fill="none" stroke="#c6bcbc"></path>
                                        </g>
                                    </g>
                
                
                                    <g :transform="translate(0, 0, 0)" id="m2Bar">
                                        <text x="5" y="20" fill="#534F4F">[M-1: Recency]</text>
                                        <g :transform="translate(5, 25, 0)">
                                            <rect v-for="(item, i) in recencyDataBar" :key="'bar' + i" :x="item.x" :y="item.y"
                                                :height="(barHeight - 3) - item.y" :width="item.w" stroke="white" fill="#D9D9D9">
                                            </rect>
                                            <g v-for="(r_item, r_i) in groupSet" :key="'sel_m' + r_i" :opacity="r_i == selectGroupTag ? 1: 0" :id="'sel_m1' + r_i">
                                            <rect v-for="(item, i) in groupSet[r_i].m1Bar" :key="'bar' + i" :x="item.x" :y="item.y"
                                                :height="(barHeight - 3) - item.y" :width="item.w" stroke="white" fill="#EA7C16">
                                            </rect>
                                        </g>
                                            <path :d="'M 20 ' + (barHeight - 3) + ' L ' + (barWidth - 10) + ' ' + (barHeight - 3)"
                                                fill="none" stroke="#534f4f">
                                            </path>
                                            <path :d="'M -5 ' + (barHeight + 5) + ' L ' + (barWidth - 5) + ' ' + (barHeight + 5)"
                                                fill="none" stroke="#c6bcbc"></path>
                                        </g>
                                    </g>
                
                                </svg>
            </div>
            <!-- <div ref="groupPie" style="width: 70.3%; height: 100%; float: right;">
                                <svg id="groupPie" width="100%" height="calc(100%)"></svg>
                            </div> -->
            <div style="height: 100%; width: 70%; float: right; overflow-x: scroll; overflow-y: hidden; white-space: nowrap" ref="groupView">
                <!-- <div v-for="(item, i) in groupSet" :key="'group' + i" :style="{
                                    'width': groupWidth / 4 + 'px',
                                    'height': '100%',
                                    'padding': '0px 5px 5px 5px',
                                    'border': '1px solid purple',
                                    'display': 'inline-block'
                                }"> -->
                <svg v-show="showTag" v-for="(item, i) in groupSet" :key="'group' + i" height="100%" width="25%">
                                    <!-- <circle cx="10" cy="10" r="10" fill="red"></circle> -->
                                    <text x="50%" y="20" font-size="16" text-anchor="middle" :fill="i != selectGroupTag ? '#534F4F' : colormap[i]" font-weight="bold" style="font-weight: 600;">{{
                                        'Group ' + i
                                    }}</text>
                                    <g :transform="translate(groupWidth / 8, groupWidth / 8 + 15, 0)">
                                        <path v-for="(t_item, t_i) in item['arc']" :key="'gHolder' + t_i" :d="t_item" :stroke="'none'" :fill="colormap[i]"></path>
                                        <path v-for="(t_item, t_i) in item['area']" :key="'gd' + t_i" :d="t_item"
                                            :transform="translate(0, 0, 90 * t_i)" :fill="axisColor[t_i]"></path>
                                        <text v-for="(t_item, t_i) in axisName" :key="'gt' + t_i" :transform="translate(0, 0, 0)"
                                            :x="Math.sin((Math.PI * (90 * t_i)) / 180) * (groupWidth / 8 - 25)"
                                            :y="-Math.cos((Math.PI * (90 * t_i)) / 180) * (groupWidth / 8 - 25)" font-size="12" dy="0.3em"
                                            text-anchor="middle" fill="#534F4F" font-weight="bold">{{ t_item }}</text>
                                        <g :transform="translate(0, 0, 0)">
                                            <path stroke-dasharray="5.5"
                                                :d="'M 0 ' + -(groupWidth / 8 - 48) + ' L 0 ' + ((groupWidth / 8 - 48))" fill="none"
                                                stroke="#D9D9D9"></path>
                                            <path stroke-dasharray="5.5"
                                                :d="'M ' + -(groupWidth / 8 - 48) + ' 0 L ' + ((groupWidth / 8 - 48)) + ' 0'" fill="none"
                                                stroke="#D9D9D9"></path>
                                            <circle x="0" y="0" :r="(groupWidth / 8 - 48 - 15) + 15" fill="none" stroke="#D9D9D9"
                                                stroke-dasharray="5.5"></circle>
                                            <circle x="0" y="0" :r="(groupWidth / 8 - 48 - 15) * 2 / 3 + 15" fill="none" stroke="#D9D9D9"
                                                stroke-dasharray="5.5"></circle>
                                            <circle x="0" y="0" :r="(groupWidth / 8 - 48 - 15) * 1 / 3 + 15" fill="none" stroke="#D9D9D9"
                                                stroke-dasharray="5.5"></circle>
                
                                            <circle x="0" y="0" :r="15" fill="white" stroke="#D9D9D9" stroke-dasharray="5.5"></circle>
                                            <!-- <path v-for="(arc_item, arc_i) in monthArc" :key="'arc' + arc_i" :d="arc_item" stroke="#D9D9D9"
                                                fill="none"></path> -->
                                        </g>
                
                                        <path v-for="(t_item, t_i) in item['projectLine']" :key="'pL' + t_i" :d="t_item.d" :fill="'none'" :stroke="'#534F4F'" :class="t_item.class" :id="'g_' + t_item.group + '_' + t_item.id" :opacity="filterValue == t_item.id ? 1 : 0"></path>
                                    </g>
                
                                    <g :transform="translate(0, groupHeight - 65, 0)">
                                        <text x="50%" y="20" font-size="14" text-anchor="middle" fill="#534F4F" font-weight="bold">{{
                                            'Num_Projects ' + item.num_project }}</text>
                                        <text x="50%" y="40" font-size="14" text-anchor="middle" fill="#534F4F" font-weight="bold">{{
                                            'Ave_Impact ' + (item.ave_impact)
                                        }}</text>
                                    </g>
                                </svg>
                <!-- </div> -->
            </div>
    
            <!-- <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
                            <div style="width: 100%; height: calc((100% - 26px) / 3);">
                                [F-2: Recency]
                                <svg width="31.8%" height="calc(100% - 30px)">
                                    <rect v-for="(item, i) in recencyData" :key="'bar' + i" :x="5 + i * (barWidth - 5) / 20"
                                        :y="barHeight - item" :height="item" :width="(barWidth - 5) / 20" stroke="#D9D9D9" fill="#D9D9D9">
                                    </rect>
                                    <path :d="'M 5 ' + barHeight + ' L ' + barWidth + ' ' + barHeight" fill="none" stroke="#534f4f"></path>
                                </svg>
                            </div>
                            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
                            <div style="width: 100%; height: calc((100% - 26px) / 3);">
                                [F-3: Propensity]
                                <svg width="31.8%" height="calc(100% - 30px)">
                                    <rect v-for="(item, i) in propensityData" :key="'bar' + i" :x="5 + i * (barWidth - 5) / 20"
                                        :y="barHeight - item" :height="item" :width="(barWidth - 5) / 20" stroke="#D9D9D9" fill="#D9D9D9">
                                    </rect>
                                    <path :d="'M 5 ' + barHeight + ' L ' + barWidth + ' ' + barHeight" fill="none" stroke="#534f4f"></path>
                                </svg>
                            </div> -->
        </div>
    </div>
</template>
``
<script>
import { scaleLinear } from 'd3-scale';
import { select, selectAll } from 'd3-selection';
import { arc, area, curveBasis, curveLinear, line, pie } from 'd3-shape';

import { axisLeft, axisBottom } from 'd3-axis';
import { sum } from 'd3-array';
import { useDataStore } from '../stores/counter';

export default {
    name: 'APP',
    props: ['cpData'],
    data() {
        return {
            filterValue: '',
            showTag: 0,
            filterOptions: [],
            projectMap: {},
            groupSet: [0, 1, 2, 3, 4, 5],
            // colormap: ["#fff2cc", "#ffe699", "#ffd966", "#ffc000", "#bf9000", "#7f6000"],
            // colormap: ["#DA927C", "#175E7D", "#B1E1E9", "#A6BAA7", "#9B9364", "#C59CA0", "#FFDDB7"],
            // colormap: ["#F3F0C7", "#BEC68A", "#72926A", "#F7C183", "#FEA541", "#FBC9C6", "#8A8CA8"],
            // colormap: ["#565C76", "#B06E62", "#66323E", "#90A1B8", "#9D717C", "#838F7E", "#ADA397"],
            colormap: ["#8F5362", "#B1818F", "#DFA57C", "#CCAA66", "#A6C9A6", "#6888A5", "#12507B"],
            // colormap: ["#B3AE94", "#C59A81", "#D8876F", "#DDBE8F", "#94A7C7", "#9B8FB7", "#D883AF"],
            monthStep: [20, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20],
            monthName: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'],
            axisName: ['M1', 'M3', 'IMP', 'M2'],
            axisColor: ['#EA7C16', '#61bad6', '#d77a78', '#53ad92'],
            attachmentData: [3, 2, 1, 5, 3, 4, 2, 4, 2, 1, 3, 2, 1, 5, 3, 4, 2, 4, 2, 1],
            recencyData: [3, 2, 1, 5, 3, 4, 2, 4, 2, 1, 3, 2, 1, 5, 3, 4, 2, 4, 2, 1],
            propensityData: [3, 2, 1, 5, 3, 4, 2, 4, 2, 1, 3, 2, 1, 5, 3, 4, 2, 4, 2, 1],
            attachmentDataBar: [],
            recencyDataBar: [],
            propensityDataBar: [],
            barHeight: 100,
            barWidth: 100,
            groupWidth: 1000,
            groupHeight: 100,
            monthArc: [],
            clusterData: [],
            timeSelectionText: '',
            selectGroupTag: -1
        }
    },
    methods: {
        translate(x, y, deg) {
            return 'translate(' + x + ',' + y + ') rotate(' + deg + ')';
        },
        calcArc() {
            let arcs = pie()(this.monthStep);
            let monthArc = [];
            for (let d of arcs) {
                d.innerRadius = this.elWidth / 8 - 30;
                d.outerRadius = this.elWidth / 8 - 25;
                let darcs = arc()(d);
                monthArc.push(darcs);
            }
            return monthArc;
        },
        dataProcess(data) {
            let projectName = [];
            let projectMap = {};
            for (let i in data) {
                projectName.push({
                    label: data[i]['Project Name'],
                    value: i,
                    group: data[i]['Group']
                });
                projectMap[data[i]['Project Name']] = {
                    id: i,
                    group: data[i]['Group']
                };
            }
            this.projectMap = projectMap;
            // console.log(projectName);
            this.filterOptions = projectName;
            let m1 = [],
                m2 = [],
                m3 = [],
                group = {};
            let max_m1 = 0,
                max_m2 = 0,
                max_m3 = 0,
                max_imp = 0;
            let min_m1 = 99999,
                min_m2 = 99999,
                min_m3 = 99999,
                min_imp = 99999;
            let groupSet = [];
            for (let i in data) {
                if (typeof(group[data[i].Group]) == 'undefined') {
                    group[data[i].Group] = {
                        project: [],
                        project_holder: [],
                        m1: [],
                        m2: [],
                        m3: [],
                        imp: [],
                        m1Bar: new Array(20),
                        m2Bar: new Array(20),
                        m3Bar: new Array(20),
                        m1Area: new Array(10).fill(0),
                        m2Area: new Array(10).fill(0),
                        m3Area: new Array(10).fill(0),
                        impArea: new Array(10).fill(0),
                        projectLine: []
                    };
                }
                group[data[i].Group].project.push(data[i]);
                group[data[i].Group].project_holder.push(parseInt(data[i].Holder))
                group[data[i].Group].m1.push(parseFloat(data[i].M1));
                group[data[i].Group].m2.push(parseFloat(data[i].M2));
                group[data[i].Group].m3.push(parseFloat(data[i].M3));
                group[data[i].Group].imp.push(parseFloat(data[i].IMP));
                // console.log(data[i].M1);
                m1.push(parseFloat(data[i].M1));
                m2.push(parseFloat(data[i].M2));
                m3.push(parseFloat(data[i].M3));
                max_m1 = Math.max(max_m1, data[i].M1)
                max_m2 = Math.max(max_m2, data[i].M2)
                max_m3 = Math.max(max_m3, data[i].M3)
                max_imp = Math.max(max_imp, data[i].IMP);
                min_m1 = Math.min(min_m1, data[i].M1);
                min_m2 = Math.min(min_m2, data[i].M2);
                min_m3 = Math.min(min_m3, data[i].M3);
                min_imp = Math.min(min_imp, data[i].IMP);
            }
            // const hBin = bin().threshold(20).domain([0, 1]);
            // console.log(new Array(10));

            let maxA = 0;
            let maxR = 0;
            let maxP = 0;

            let xScale = scaleLinear([0, 20], [22, this.barWidth - 15])
            let a = new Array(20),
                r = new Array(20),
                p = new Array(20);
            for (let i in group) {
                for (let j = 0; j < 20; ++j) {
                    group[i].m1Bar[j] = {
                        x: xScale(j),
                        v: 0,
                        y: 0,
                        w: (this.barWidth - 20) / 20
                    };
                    group[i].m2Bar[j] = {
                        x: xScale(j),
                        v: 0,
                        y: 0,
                        w: (this.barWidth - 20) / 20
                    };
                    group[i].m3Bar[j] = {
                        x: xScale(j),
                        v: 0,
                        y: 0,
                        w: (this.barWidth - 20) / 20
                    };
                }
            }
            for (let i = 0; i < 20; i++) {
                a[i] = {
                    x: xScale(i),
                    v: 0,
                    y: 0,
                    w: (this.barWidth - 20) / 20
                }
                r[i] = {
                    x: xScale(i),
                    v: 0,
                    y: 0,
                    w: (this.barWidth - 20) / 20
                }
                p[i] = {
                    x: xScale(i),
                    v: 0,
                    y: 0,
                    w: (this.barWidth - 20) / 20
                }
            }
            // console.log(m1)
            for (let i = 0; i < m1.length; i++) {
                let rr = Math.floor(((m1[i] - min_m1) / (max_m1 - min_m1)) / (1 / 20));
                if (rr >= 20) rr--;
                let aa = Math.floor(((m2[i] - min_m2) / (max_m2 - min_m2)) / (1 / 20));
                if (aa >= 20) aa--;
                let pp = Math.floor(((m3[i] - min_m3) / (max_m3 - min_m3)) / (1 / 20));
                if (pp >= 20) pp--;

                a[aa].v++;
                r[rr].v++;
                p[pp].v++;
                maxA = Math.max(maxA, a[aa].v);
                maxR = Math.max(maxR, r[rr].v);
                maxP = Math.max(maxP, p[pp].v);
            }
            let max_g = 0;

            for (let i in group) {
                // console.log(group[i]);
                for (let j in group[i].m1) {
                    let m11 = Math.floor(((group[i].m1[j] - min_m1) / (max_m1 - min_m1)) / (1 / 10));
                    let m22 = Math.floor(((group[i].m2[j] - min_m2) / (max_m2 - min_m2)) / (1 / 10));
                    let m33 = Math.floor(((group[i].m3[j] - min_m3) / (max_m3 - min_m3)) / (1 / 10));
                    let impp = Math.floor(((group[i].imp[j] - min_imp) / (max_imp - min_imp)) / (1 / 10));
                    m11 = m11 == 10 ? m11 - 1 : m11;
                    m22 = m22 == 10 ? m22 - 1 : m22;
                    m33 = m33 == 10 ? m33 - 1 : m33;
                    impp = impp == 10 ? impp - 1 : impp;
                    group[i].m1Area[m11]++;
                    group[i].m2Area[m22]++;
                    group[i].m3Area[m33]++;
                    group[i].impArea[impp]++;
                    max_g = Math.max(max_g, group[i].m1Area[m11], group[i].m2Area[m22], group[i].m3Area[m33], group[i].impArea[impp]);

                    let lineYScale = scaleLinear([0, 1], [-15, -(this.groupWidth / 8 - 38)])

                    let projectLineData = [
                        [0, lineYScale(m11 / 10)],
                        [-lineYScale(m33 / 10), 0],
                        [0, -lineYScale(impp / 10)],
                        [lineYScale(m22 / 10), 0],
                        [0, lineYScale(m11 / 10)],

                    ];
                    let projectLineGenerate = line().x(d => d[0]).y(d => d[1]);
                    // if (j == 0 && i == 0) {
                    // console.log(m11, m22, m33, impp);
                    // console.log(projectLineData);
                    group[i].projectLine.push({
                        d: projectLineGenerate(projectLineData),
                        project: group[i].project[j]['Project Name'],
                        id: projectMap[group[i].project[j]['Project Name']].id,
                        group: i,
                        class: 'projectRadar'
                    });
                    // }


                    let m111 = Math.floor(((group[i].m1[j] - min_m1) / (max_m1 - min_m1)) / (1 / 20));
                    let m222 = Math.floor(((group[i].m2[j] - min_m2) / (max_m2 - min_m2)) / (1 / 20));
                    let m333 = Math.floor(((group[i].m3[j] - min_m3) / (max_m3 - min_m3)) / (1 / 20));

                    m111 = m111 == 20 ? m111 - 1 : m111;
                    m222 = m222 == 20 ? m222 - 1 : m222;
                    m333 = m333 == 20 ? m333 - 1 : m333;
                    group[i].m1Bar[m111].v++;
                    group[i].m2Bar[m222].v++;
                    group[i].m3Bar[m333].v++;
                }
            }

            let gXScale = scaleLinear([0, max_g], [0, 30]);
            let gYScale = scaleLinear([0, 1], [-15, -(this.groupWidth / 8 - 38)])
            let yAScale = scaleLinear([0, maxA], [this.barHeight - 3, 10]);
            let yRScale = scaleLinear([0, maxR], [this.barHeight - 3, 10]);
            let yPScale = scaleLinear([0, maxP], [this.barHeight - 3, 10]);
            select('#m1Bar').append('g').call(axisLeft(yAScale).ticks(3)).attr('transform', 'translate(21, 0)');

            select('#m2Bar').append('g').call(axisLeft(yRScale).ticks(3)).attr('transform', 'translate(26, 25)');

            select('#m3Bar').append('g').call(axisLeft(yPScale).ticks(3)).attr('transform', 'translate(26, 25)');
            for (let i in a) {
                a[i].y = yAScale(a[i].v);
                r[i].y = yRScale(r[i].v);
                p[i].y = yPScale(p[i].v);
            }
            for (let i in group) {
                for (let j in group[i].m1Bar) {
                    group[i].m1Bar[j].y = yRScale(group[i].m1Bar[j].v);
                    group[i].m2Bar[j].y = yAScale(group[i].m2Bar[j].v);
                    group[i].m3Bar[j].y = yPScale(group[i].m3Bar[j].v);
                }
            }
            let areaGenerate = area()
                .curve(curveBasis)
                .x0(d => gXScale(d))
                .x1(d => -gXScale(d))
                .y((d, i) => gYScale(i / 10));

            for (let d in group) {
                group[d]['area'] = [areaGenerate(group[d].m1Area), areaGenerate(group[d].m3Area), areaGenerate(group[d].impArea), areaGenerate(group[d].m2Area)];
                group[d]['num_project'] = group[d].project.length;
                group[d]['ave_impact'] = (sum(group[d].imp) / group[d].imp.length).toFixed(2);
                group[d]['pie'] = pie().padAngle(0.01)(group[d].project_holder);
                group[d]['arc'] = [];
                for (let i in group[d].pie) {
                    let tArc = arc().cornerRadius(3)
                        .innerRadius(this.groupWidth / 8 - 42)
                        .outerRadius(this.groupWidth / 8 - 36)(group[d].pie[i]);
                    group[d]['arc'].push(tArc);
                }
                // console.log(group[d]['ave_impact'])
                groupSet.push(group[d]);
            }
            // console.log(groupSet);
            return [a, r, p, groupSet];
            // // console.log(this.attachmentData)
        },
        // calcFilter (data) {}
    },
    created() {},
    mounted() {
        // console.log
        this.barHeight = (this.$refs.attr_bar.offsetHeight - 85) / 3;
        this.barWidth = this.$refs.attr_bar.offsetWidth - 15;
        this.groupHeight = this.$refs.groupView.offsetHeight;
        this.groupWidth = this.$refs.groupView.offsetWidth;
        // console.log(this.cpData)

        // [this.attachmentDataBar, this.recencyDataBar, this.propensityDataBar, this.groupSet] = this.dataProcess(this.cpData.data);
        const dataStore = useDataStore();
        dataStore.$subscribe((mutations, state) => {
            if (dataStore.allData.tag == 1) {
                this.showTag = 1;
                this.timeSelectionText = dataStore.timeRange.start_format + ' - ' + dataStore.timeRange.end_format;

                [this.attachmentDataBar, this.recencyDataBar, this.propensityDataBar, this.groupSet] = this.dataProcess(dataStore.allData.cpData.data);
            }

            if (dataStore.selectGroup != -1) {
                this.selectGroupTag = dataStore.selectGroup;
                this.$refs.groupView.scrollLeft = (dataStore.selectGroup + 1 - 4) * this.groupWidth / 4;
                let project_name = [];
                // for ()
                for (let i in this.cpData.data) {
                    if (this.cpData.data[i]['Group'] == dataStore.selectGroup || dataStore.selectGroup == -2)
                    project_name.push({
                        label: this.cpData.data[i]['Project Name'],
                        value: i
                    })
                }
                this.filterValue = '';
                this.filterOptions = project_name;
            }
        })
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

/*chrome--------------------------------------------start*/

::-webkit-scrollbar {
    width: 8px;
    height: 8px;
}

/* Track */

::-webkit-scrollbar-track {
    background: #ffffff;
    border-radius: 8px;
}

/* Handle */

::-webkit-scrollbar-thumb {
    background: rgb(201, 201, 202);
    border-radius: 8px;
}

/* Handle on hover */

::-webkit-scrollbar-thumb:hover {
    background: rgb(162, 162, 163);
}

.el-menu::-webkit-scrollbar,
.el-table__body-wrapper::-webkit-scrollbar {
    display: none;
}

.el-menu:hover::-webkit-scrollbar,
.el-table__body-wrapper:hover::-webkit-scrollbar {
    display: block;
}

/*chrome--------------------------------------------end*/

.axisA:after {
    content: "";
    position: absolute;
    border: 8px solid transparent;
    border-right-color: rgb(99, 99, 99);
    /* width: 0px;
  height: 10px; */
    top: calc(50% - 8px);
    left: -16px;
}
</style>
