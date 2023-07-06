<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2023-07-05 18:17:06
 * @LastEditors: Qing Shi
 * @LastEditTime: 2023-07-05 20:40:16
-->
<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2023-02-11 23:40:58
 * @LastEditTime: 2023-07-02 15:22:29
-->
<template>
    <div style="height: 100%;">
        <div class="frameworkTitle">

            <span class="title" style="float: left;">
                <svg t="1676051676925" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
                    p-id="28401" width="20" height="20">
                    <path
                        d="M896.00324 352c70.7 0 128-57.3 128-128 0-70.6-57.4-128-128-128-70.7 0-128 57.3-128 128 0 18.8 4.1 36.7 11.3 52.8 2.7 6 1.4 13.1-3.3 17.8l-92.9 92.9c-5.4 5.4-13.8 6.3-20.1 2.1-20.3-13.6-44.8-21.5-71-21.5-2.1 0-4.2 0.1-6.3 0.1-6 0.3-11.7-2.8-14.7-8l-58-100.4c-3.4-5.8-2.7-13.1 1.6-18.3 18.6-22.5 29.7-51.6 29.3-83.2C543.10324 89 486.40324 32.6 417.10324 32c-70.6-0.6-128.2 56-129.1 126.3-0.9 69.5 56.5 128.6 126 129.7 9.4 0.1 18.5-0.7 27.4-2.5 6.8-1.4 13.6 1.7 17.1 7.7l50.8 88c3.7 6.5 2.5 14.8-3 19.8-15.7 14.1-27.8 32.1-35 52.4-2.3 6.4-8.4 10.6-15.2 10.6H262.70324c-6.6 0-12.6-4-14.9-10.2-18.1-48-64.3-82.2-118.5-82.8C58.70324 370.3 0.50324 427.6 0.00324 498.1-0.49676 569.2 57.00324 627 128.00324 627c56.7 0 104.8-36.9 121.6-87.9 2.2-6.6 8.3-11.1 15.2-11.1h191.4c6.7 0 12.8 4.2 15 10.6 4.7 13.3 11.5 25.7 20.1 36.6 4 5.1 4.4 12.2 1.2 17.8l-71.8 124.4c-3.7 6.3-11.1 9.4-18.2 7.4-11.1-3.1-22.7-4.7-34.8-4.7-69.7 0.1-127 56.8-127.8 126.6-0.8 71.7 57.4 130 129.1 129.4 69.5-0.6 126.3-57.3 126.9-126.8 0.3-28-8.5-53.9-23.5-75.1-3.6-5.1-3.9-11.8-0.8-17.2L546.00324 628.4c3.5-6 10.5-9.2 17.3-7.6 9.2 2.1 18.9 3.2 28.8 3.2 17.7 0 34.6-3.6 49.9-10.1 7.4-3.1 16-0.2 20 6.8l79 136.8c3.5 6.1 2.5 13.8-2.3 18.9-21.6 22.9-34.7 53.7-34.7 87.6 0 70.9 57.9 128.5 128.9 128 69.7-0.5 126.2-56.7 127.1-126.3 0.9-70.1-57-129.3-127.1-129.7-6.2 0-12.3 0.4-18.3 1.2-6.5 0.9-12.8-2.2-16.1-7.8l-92.2-159.7c-2.7-4.7-2.9-10.4-0.5-15.2 9-17.5 14.1-37.4 14.1-58.4 0-13-2-25.6-5.6-37.5-1.7-5.6-0.1-11.7 4-15.9l101.4-101.4c4.9-4.9 12.4-6 18.7-2.9 17.4 8.7 36.9 13.6 57.6 13.6zM416.00324 224c-35.3 0-64-28.7-64-64s28.7-64 64-64 64 28.7 64 64-28.7 64-64 64zM128.00324 563c-35.3 0-64-28.7-64-64s28.7-64 64-64 64 28.7 64 64-28.7 64-64 64z m240 349c-35.3 0-64-28.7-64-64s28.7-64 64-64 64 28.7 64 64-28.7 64-64 64z m464-112c35.3 0 64 28.7 64 64s-28.7 64-64 64-64-28.7-64-64 28.7-64 64-64zM592.00324 560c-35.3 0-64-28.7-64-64s28.7-64 64-64 64 28.7 64 64-28.7 64-64 64z m304-400c35.3 0 64 28.7 64 64s-28.7 64-64 64-64-28.7-64-64 28.7-64 64-64z"
                        p-id="28402" stroke="#534f4f" fill="#534f4f"></path>
                </svg>
                &nbsp; <span style="position: relative; top: 0px; font-weight: 600;">Substitution View</span>
            </span>

            <!-- <span style="float: right; position: relative; top: -2px; font-size: 16px;">
                <svg height="27" width="500" transform="translate(0, 10)">
                    <g v-for="(item, i) in (all_group_array)" :key="'gcolor' + i">
                        <rect :x="0 + i * 50" :y="2" :width="50" :height="9" :fill="colormap[i]" :stroke="'#534f4f'"></rect>
                        <text :x="0 + i * 50 + 25" :y="23" font-size="12" text-anchor="middle" fill="#534F4F">{{ 'Group' + i
                        }}</text>
                    </g>
                    <g>
                        <rect :x="0 + 400" :y="2" :width="9" :height="9" :fill="'#A50021'" :stroke="'#534f4f'"></rect>
                        <text :x="0 + 400 + 4.5" :y="23" font-size="12" text-anchor="middle" fill="#534F4F">{{ 'In-flow'
                        }}</text>


                        <rect :x="0 + 450" :y="2" :width="9" :height="9" :fill="'#181CF7'" :stroke="'#534f4f'"></rect>
                        <text :x="0 + 450 + 4.5" :y="23" font-size="12" text-anchor="middle" fill="#534F4F">{{ 'Out-flow'
                        }}</text>
                    </g>
                </svg>
                Filter by:
                <el-select v-model="filterValue" class="m-2" placeholder="Select"
                    style="width: 50px; --el-border-color: white;">
                    <el-option v-for="item in filterOptions" :key="item" :label="item.label" :value="item.value" />
                </el-select>
            </span> -->
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
        </div>
        <div class="frameworkBody">
            <div style="height: 100%; width: 100%; margin-top: 5px;" ref="distributionView">

                <!-- <div class="tooltip"
                    style="opacity: 0; background-color: white; border: solid; border-width: 2px; border-radius: 5px; padding: 5px; position: absolute; z-index: 100; left: -1000px;">
                    <div>
                        <svg width="150" height="90">
                            <g v-for="(item, i) in glyphData" :transform="translate(75, 45, 0)">
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
                        </svg>
                    </div>
                    <div v-for="(item, i) in glyphData" style="width: 150px;">
                        <div style="text-align: center;">#Project Name</div>
                        <div style="text-align: center;">{{ item.name.name }}</div>
                        <div style="text-align: center;">#Holder</div>
                        <div style="text-align: center;">{{ item.name.holder }}</div>
                    </div>
                </div> -->


                <!-- <div class="tooltipFlow"
                    style="opacity: 0; background-color: white; border: solid; border-width: 2px; border-radius: 5px; padding: 5px; position: absolute; z-index: 100; left: -1000px;">
                    <div>
                        <svg width="310" height="50">
                            <text x="150" y="25" stroke="#534f4f" text-anchor="middle"
                                font-weight="400">{{ flowHoverVal }}</text>
                            <path d="M120,35L180,35" stroke="#534f4f" fill="none" marker-end="url(#arrow)" stroke-width="2">
                            </path>
                            <g v-for="(item, i) in flowHoverData" :transform="translate(75 + i * 160, 25, 0)">
                                <clipPath id="clipPath2">
                                    <circle :cx="20" :cy="20" :r="20"></circle>
                                </clipPath>
                                <g clip-path="url(#clipPath2)" :transform="translate(-20, -20, 0)">
                                    <image :href="item.logo_link" x="0" y="0" :height="40" :width="40" />
                                </g>
                            </g>
                        </svg>
                    </div>
                    <div v-for="(item, i) in flowHoverData"
                        :style="{ width: '150px', display: 'inline', float: i == 0 ? 'left' : 'right' }">
                        <div style="text-align: center;">{{ item.name }}</div>
                    </div>
                </div> -->
                <span style="position: absolute; top: 0px; color: #ABACBE; font-size: 14px;z-index: 100;">
                    Selecting <span class="php">{{ select_project_num }} projects</span> from <span
                        class="php">{{ allProject_num }} results</span>
                    <br>
                    Time Slot: <span class="php">{{ timeSelectionText }}</span>
                </span>
                <div style="height: calc(100% - 0px); width: 100%;">
                    <svg width="100%" height="100%">
                        <g :transform="translate(this.elWidth / 2, this.distributionHeight / 2 , 0)">
                            <!-- <g v-for="(item, i) in projectArc" :key="'arc_' + i">
                                <path :d="item.d" :stroke="item.fill" :fill="item.fill"></path>
                            </g> -->
                            <g v-for="(item, i) in projectConnect" :key="'connect_' + i">
                                <path :d="item.d" :stroke="'#666'" :fill="'#666'" :opacity="0.2"></path>
                            </g>
                            <g v-for="(item, i) in projectPosition" :key="'logo_' + i" :transform="translate(-20, -20, 0)">
                                <clipPath id="clipPath20">
                                    <circle :cx="20" :cy="20" :r="40 / 2"></circle>
                                </clipPath>

                                <g clip-path="url(#clipPath20)" :transform="translate(item.pos[0], item.pos[1], 0)">
                                    <image :href="item.link" x="0" y="0" :height="40" :width="40" />
                                </g>
                                <!-- <circle  :transform="translate(item.pos[0], item.pos[1], 0)" :cx="0" :cy="0" :r="20" :fill="item.fill"></circle> -->
                            </g>
                        </g>
                    </svg>
                </div>
            </div>

            <!-- <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2> -->

        </div>
    </div>
</template>

<script>
import { scaleLinear } from 'd3-scale';
import { select, selectAll } from 'd3-selection';
import { arc, area, curveBasis, pie } from 'd3-shape';
import { useDataStore } from "../stores/counter";
import { extent } from 'd3-array';
import * as d3 from 'd3';
import flow_data from '../assets/run_full_1/substitution_flow.json';
import cpData from '../assets/run_full_1/control_panel.json';

export default {
    name: "APP",
    props: [],
    data () {
        return {
            lineHover: -1,
            timeSelectionText: "",
            flowHoverVal: 0,
            flowHoverData: [],
            cpData: {},
            showHSB: 1,
            groupSelect: 0,
            groupClick: 0,
            projectSelectSta: 0,
            ProjectClickSta: 0,
            ProjectClickName: '',
            zoomTag: 1,
            select_project_num: 0,
            allProject_num: 0,
            all_group_num: 0,
            all_group_array: [],
            innerAreaTag: 'm1d',
            elWidth: 1000,
            distributionHeight: 100,
            groupHeight: 0,
            filterValue: "m1d",
            filterOptions: [{ label: "M-1", value: "m1d" }, { label: "M-2", value: "m2d" }, { label: "M-3", value: "m3d" }, { label: "IMP", value: "impd" }],
            groupSet: [1, 2, 3, 4, 5, 6],
            monthStep: [20, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20],
            monthName: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'],
            monthDay: {
                2021: [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31],
                2022: [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31],
            },
            monthArc: [],
            mainInnerArc: [],
            mainArc: [],
            innerArc: [],
            allGroupArc: [],
            axisName: ['F1', 'F3', 'Imp', 'F2'],
            axisColorA: { 'm1d': '#EA7C16', 'm3d': '#61bad6', 'impd': '#d77a78', 'm2d': '#53ad92' },
            // colormap: ["#fff2cc", "#ffe699", "#ffd966", "#ffc000", "#bf9000", "#7f6000"],
            // colormap: ["#DA927C", "#175E7D", "#B1E1E9", "#A6BAA7", "#9B9364", "#C59CA0", "#FFDDB7"],
            // colormap: ["#F3F0C7", "#BEC68A", "#72926A", "#F7C183", "#FEA541", "#FBC9C6", "#8A8CA8"],
            // colormap: ["#565C76", "#B06E62", "#66323E", "#90A1B8", "#9D717C", "#838F7E", "#ADA397"],
            colormap: ["#8F5362", "#B1818F", "#DFA57C", "#CCAA66", "#A6C9A6", "#6888A5", "#12507B"],
            // colormap: ["#B3AE94", "#C59A81", "#D8876F", "#DDBE8F", "#94A7C7", "#9B8FB7", "#D883AF"],
            groupTag: -1,
            outerArc: [],
            groupArc: [],
            scatterData: [],
            innerArea: [],
            showTag: 0,
            projectFlow: [],
            selectGroup: -1,
            projectSelect: [],
            valueRange: {},
            glyphData: [],
            axisColor: { 'M1': '#EA7C16', 'M3': '#61bad6', 'IMP': '#d77a78', 'M2': '#53ad92' },
            colorType: {
                holder: '#c9c9c9',
                seller: '#b69acb',
                buyer: '#6f319b',
            },
            flow_data: {},
            projectPosition: [],
            projectObj: {},
            projectConnect: [],
            projectArc: []
        };
    },
    methods: {
        translate (x, y, deg) {
            return `translate(${x}, ${y}) rotate(${deg})`;
        },
        calcProjectPosition (data) {
            let r = (this.distributionHeight - 60) / 2;
            let logoAngle = (360) / data.length;
            let res_pos = [];
            let res_project = new Object();
            let arcData = [];
            data.sort((a, b) => {
                return parseInt(a['Group']) - parseInt(b['Group']);
            })
            for (let i in data) {
                let tmp = i * logoAngle * Math.PI / 180
                res_pos.push({
                    name: data[i]['Project Name'],
                    link: data[i]['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data[i]['logo_link'],
                    pos: [r * Math.sin(tmp), -r * Math.cos(tmp)],
                    fill: this.colormap[parseInt(data[i]['Group'])]
                });
                res_project[data[i]['Project Name']] = {
                    name: data[i]['Project Name'],
                    link: data[i]['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data[i]['logo_link'],
                    pos: [r * Math.sin(tmp), r * Math.cos(tmp)],
                    logoAngle: logoAngle * Math.PI / 180,
                    angle: tmp,
                    r: r
                };
                arcData.push({
                    d: arc().innerRadius(r - 35).outerRadius(r - 30).padAngle(0.005).cornerRadius(3)({
                        startAngle: tmp - logoAngle * Math.PI / 360,
                        endAngle: tmp + logoAngle * Math.PI / 360
                    }),
                    fill: this.colormap[parseInt(data[i]['Group'])]
                })
            }
            return [res_pos, res_project, arcData];
        },
        calcFlow (data, project) {
            let ribbonGenerator = d3.ribbon();
            let repeatData = {};
            let tmp_data = [];
            let min_flow = 999999999;
            let max_flow = -99999999;
            for (let i in data) {
                let v = parseFloat(data[i]['SubstitutionFlow']);
                if (v < 0) continue;
                min_flow = Math.min(min_flow, v);
                max_flow = Math.max(max_flow, v);
            }
            let flowScale =  scaleLinear([min_flow, max_flow], [0.1, 1]);
            let typeName = data[0]['Project Name From'];
            for (let i in data) {
                let a = data[i]['Project Name From'];
                let b = data[i]['Project Name To'];
                let v = data[i]['SubstitutionFlow'];
                if (v < 0) continue;
                // if (!(a == typeName || b == typeName))
                //     continue;
                if (repeatData[a + b] == 1) continue;
                repeatData[a + b] = 1;
                // console.log(project[a], a, data[i]);
                let tmp_arc  ={
                    source: {
                        startAngle: project[a].angle - flowScale(v) * (project[a].logoAngle / 2),
                        endAngle: project[a].angle + flowScale(v) * (project[a].logoAngle / 2), radius: project[a].r - 0
                    },
                    target: {
                        startAngle: project[b].angle - flowScale(v) * (project[b].logoAngle / 2),
                        endAngle: project[b].angle + flowScale(v) * (project[b].logoAngle / 2), radius: project[b].r - 0
                    }
                };
                tmp_data.push({
                    arc: tmp_arc,
                    d: ribbonGenerator(tmp_arc),
                    fill: b == typeName ? '#A50021' : '#181CF7'
                })
                // if (repeatData[])
                // if (data[i])
            }
            // console.log(tmp_data);
            return tmp_data;
        }
    },
    created () { },
    mounted () {
        this.elWidth = this.$refs.distributionView.offsetWidth;
        this.distributionHeight = this.$refs.distributionView.offsetHeight;
        [this.projectPosition, this.projectObj, this.projectArc] = this.calcProjectPosition(cpData.data);
        // console.log(this.projectPosition);
        this.projectConnect = this.calcFlow(flow_data.data, this.projectObj);
    }
}
</script>

<style scoped>
.php {
    text-decoration: underline;
    color: #534F4F;
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

.tooltip {
    /* background-color: gray; */
    /* height: 70px; */
    /* position: relative;
  width: 150px; */
    /* border-radius: 15px; */
}

/*chrome--------------------------------------------end*/
</style>
