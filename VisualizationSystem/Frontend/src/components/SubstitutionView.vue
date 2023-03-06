<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2023-02-11 23:40:58
 * @LastEditTime: 2023-02-27 11:14:28
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

            <span style="float: right; position: relative; top: -2px; font-size: 16px;">
                <svg height="27" width="320" transform="translate(0, 10)">
                    <g v-for="(item, i) in colormap" :key="'gcolor' + i">
                        <rect :x="0 + i * 50" :y="2" :width="50" :height="9" :fill="item" :stroke="'#534f4f'"></rect>
                        <text :x="0 + i * 50 + 25" :y="23" font-size="12" text-anchor="middle" fill="#534F4F">{{ 'Group' + i
                        }}</text>
                    </g>
                </svg>
                Filter by:
                <el-select v-model="filterValue" class="m-2" placeholder="Select"
                    style="width: 70px; --el-border-color: white;">
                    <el-option v-for="item in filterOptions" :key="item" :label="item" :value="item" />
                </el-select>
            </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
        </div>
        <div class="frameworkBody">
            <div style="height: 100%; width: 100%; margin-top: 5px;" ref="distributionView">
                <span style="position: absolute; top: 0px; color: #ABACBE; font-size: 14px;">Showing
                    <span class="php">16 projects</span> from <span class="php">55 results</span>
                </span>
                <div style="height: calc(100% - 0px); width: 100%;">
                    <svg width="100%" height="100%">
                        <g :transform="translate(elWidth / 2, (distributionHeight) / 2, 0)">
                            <g>
                                <path v-for="(arc_item, arc_i) in mainArc" :key="'arc' + arc_i" :d="arc_item"
                                    stroke="#C6BCBC" fill="none"></path>
                                <!-- <path v-for="(arc_item, arc_i) in mainInnerArc" :key="'arc' + arc_i" :d="arc_item"
                                    stroke="#C6BCBC" fill="none"></path> -->
                                <text x="0" :y="-(distributionHeight * 0.9 / 2)" dy="0.5em" font-size="14"
                                    text-anchor="middle" fill="#534F4F" font-weight="bold">{{ '2022' }}</text>
                                <text x="0" :y="-(distributionHeight * 0.75 / 2 - 3)" dy="0.5em" font-size="14"
                                    text-anchor="middle" fill="#534F4F" font-weight="bold">{{ '2021' }}</text>

                                <text v-for="(t_item, t_i) in monthName" :key="'gt' + t_i" :transform="translate(0, 0, 0)"
                                    :x="Math.sin((Math.PI * (30 * t_i + 15)) / 180) * (distributionHeight * 0.9 / 2 - 5)"
                                    :y="-Math.cos((Math.PI * (30 * t_i + 15)) / 180) * (distributionHeight * 0.9 / 2 - 5)"
                                    font-size="14" dy="0.5em" text-anchor="middle" fill="#534F4F" font-weight="bold">{{
                                        t_item
                                    }}</text>
                            </g>

                            <g :transform="translate(0, 0, -6)">
                                <path v-for="(arc_item, arc_i) in innerArc" :key="'arc' + arc_i" :d="arc_item"
                                    stroke="#C6BCBC" :fill="arc_i == 0 ? 'none' : 'none'"></path>
                            </g>
                            <g>
                                <path v-for="(arc_item, arc_i) in monthArc" :key="'select_time' + arc_i" :d="arc_item" fill="#C6BCBC" stroke="#C6BCBC"></path>
                            </g>

                            <g>
                                <circle cx="0" cy="0" :r="distributionHeight * .53 / 2" fill="none" stroke="#534F4F"
                                    stroke-width="1"></circle>
                                <path v-for="item in 30" :key="'path' + item"
                                    :d="'M 0 0 L ' + (Math.sin(((item * 12 - 6) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' ' + (Math.cos(((item * 12 - 6) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2))"
                                    stroke="#534F4F" stroke-width="0.5"></path>
                                <path
                                    :d="'M ' + (Math.sin(((0) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' ' + (-Math.cos(((0) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' L' + (Math.sin(((120) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' ' + (-Math.cos(((120) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' L ' + (Math.sin(((240) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' ' + (-Math.cos(((240) * Math.PI) / 180) * (distributionHeight * .53 / 2 - 2)) + ' Z'"
                                    stroke-dasharray="5.5" stroke="#C6BCBC" fill="none"></path>

                                <text :x="(Math.sin(((0) * Math.PI) / 180) * (distributionHeight * .53 / 2 + 15))"
                                    :y="(-Math.cos(((0) * Math.PI) / 180) * (distributionHeight * .53 / 2 + 15))"
                                    font-size="14" dy="0.5em" text-anchor="middle" fill="#534F4F"
                                    font-weight="bold">H</text>
                                <text :x="(Math.sin(((120) * Math.PI) / 180) * (distributionHeight * .53 / 2 + 15))"
                                    :y="(-Math.cos(((120) * Math.PI) / 180) * (distributionHeight * .53 / 2 + 15))"
                                    font-size="14" dy="0.5em" text-anchor="middle" fill="#534F4F"
                                    font-weight="bold">B</text>
                                <text :x="(Math.sin(((240) * Math.PI) / 180) * (distributionHeight * .53 / 2 + 15))"
                                    :y="(-Math.cos(((240) * Math.PI) / 180) * (distributionHeight * .53 / 2 + 15))"
                                    font-size="14" dy="0.5em" text-anchor="middle" fill="#534F4F"
                                    font-weight="bold">S</text>
                            </g>
                            <g :transform="translate(0, 0, 0)">

                                <path v-for="(arc_item, arc_i) in outerArc" :key="'arc' + arc_i" :d="arc_item" stroke="none"
                                    :fill="arc_i == groupTag ? 'none' : colormap[arc_i]"></path>

                                <path v-for="(arc_item, arc_i) in groupArc" :key="'arc' + arc_i" :d="arc_item.arc"
                                    :fill="arc_item.group ==  groupTag? 'white' : colormap[parseInt(arc_item.group)]"
                                    :stroke="arc_item.group == groupTag ? '#C6BCBC' : colormap[parseInt(arc_item.group)]"
                                    stroke-width="1"></path>
                            </g>
                        </g>
                    </svg>
                </div>
            </div>

            <!-- <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1> -->

        </div>
    </div>
</template>
<script>
import { arc, pie } from 'd3-shape';
import { useDataStore } from "../stores/counter";

export default {
    name: "APP",
    props: ["groupData"],
    data () {
        return {
            elWidth: 1000,
            distributionHeight: 0,
            groupHeight: 0,
            filterValue: "factor1",
            filterOptions: ["factor1"],
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
            axisName: ['F1', 'F3', 'Imp', 'F2'],
            colormap: ["#fff2cc", "#ffe699", "#ffd966", "#ffc000", "#bf9000", "#7f6000"],
            // groupData: [{
            //     "group": 1,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 12,
            //     "len": [3, 2, 5, 2]
            // }, {
            //     "group": 2,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 10,
            //     "len": [2, 2, 3, 3]
            // }, {
            //     "group": 3,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 10,
            //     "len": [2, 5, 3]
            // }, {
            //     "group": 4,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 6,
            //     "len": [3, 3]
            // }, {
            //     "group": 5,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 2,
            //     "len": [1, 1]
            // }, {
            //     "group": 6,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 15,
            //     "len": [5, 3, 7]
            // }, {
            //     "group": 7,
            //     "num_projects": 25,
            //     "ave_impact": 60,
            //     "sum_len": 15,
            //     "len": [15]
            // }],
            groupTag: -1,
            outerArc: [],
            groupArc: []
        };
    },
    methods: {
        translate (x, y, d) {
            return `translate(${x}, ${y}) rotate(${d})`;
        },
        calcTime(timeRange) {

        },
        calcArc (data) {
            // console.log(data['start_time'].split('-'));
            let st = data['start_time'].split('-');
            let et = data['end_time'].split('-');
            let SA, SB, EA, EB;
            let Marc = [];
            if (st[0] != et[0]) {
                SA = (parseInt(st[1] - 1) * 30 + 30 * parseInt(st[2]) / this.monthDay[st[0]][st[1] - 1]) * Math.PI / 180;
                SB = 360 * Math.PI / 180;
                let sData = [((1 - parseInt(st[2]) / this.monthDay[st[0]][st[1] - 1]) * 20)];
                for (let i = parseInt(st[1]) + 1; i <= 12; ++i) {
                    sData.push(20);
                }
            
                EA = 0;
                EB = (parseInt(et[1] - 1) * 30 + 30 * parseInt(et[2]) / this.monthDay[et[0]][et[1] - 1]) * Math.PI / 180;
                let eData = [(parseInt(et[2]) / this.monthDay[et[0]][et[1] - 1]) * 20]
                for (let i = 1; i <= parseInt(et[1] - 1); ++i) {
                    eData.push(20);
                }
                let sArcData = pie().startAngle(SA).endAngle(SB).padAngle(0.006).sortValues((a, b) => a - b)(sData);
                let eArcData = pie().startAngle(EA).endAngle(EB).padAngle(0.006).sortValues((a, b) => b - a)(eData);
                
                
                for (let i in sArcData) {
                    let dArc = arc().innerRadius(this.distributionHeight * 0.81 / 2 - 5).outerRadius(this.distributionHeight * 0.77 / 2 - 5)(sArcData[i]);
                    Marc.push(dArc);
                }

                for (let i in eArcData) {
                    let dArc = arc().innerRadius(this.distributionHeight * 0.85 / 2).outerRadius(this.distributionHeight * 0.81 / 2)(eArcData[i]);
                    Marc.push(dArc);
                }

            }
            return Marc;
        },
        mainDataProcess () {
            let arcs = pie().padAngle(0.005)(this.monthStep);
            let innerArc = [];
            let innerData = [];
            for (let i = 0; i < 30; i++) {
                innerData.push(20);
            }
            let innerArcData = pie().padAngle(0.007)(innerData);
            for (let d of innerArcData) {
                d.innerRadius = this.distributionHeight * .71 / 2 + 5;
                d.outerRadius = this.distributionHeight * .53 / 2 + 7;
                let darcs = arc()(d);
                innerArc.push(darcs);
            }

            let monthArc = [];
            let monthInnerArc = [];
            for (let d of arcs) {
                d.innerRadius = this.distributionHeight * 0.85 / 2;
                d.outerRadius = this.distributionHeight * 0.81 / 2;
                // d.padAngle  = 10;
                // d.padRadius = 10;
                let darcs = arc()(d);
                monthArc.push(darcs);
            }
            for (let d of arcs) {
                d.innerRadius = this.distributionHeight * 0.81 / 2 - 5;
                d.outerRadius = this.distributionHeight * 0.77 / 2 - 5;
                // d.padAngle  = 10;
                // d.padRadius = 10;
                let darcs = arc()(d);
                monthArc.push(darcs);
            }
            return [monthArc, monthInnerArc, innerArc];
        },
        outerArcProgress: function (data) {
            let group = {};
            let maxGroup = 0;
            for (let i in data) {
                if (typeof (group[data[i].Group]) == 'undefined') {
                    group[data[i].Group] = {
                        project: [],
                        sum_len: 0,
                        len: [],
                        group: data[i].Group
                    }
                    maxGroup = Math.max(maxGroup, parseInt(data[i].Group));
                }
                group[data[i].Group].project.push(data[i]);
                group[data[i].Group].sum_len ++;
                group[data[i].Group].len.push(parseInt(data[i].n_holder));
            }
            // console.log(data.length)
            if (data.length < 70) {
                group[maxGroup + 1] = {
                    sum_len: 70 - data.length,
                    len: [data.length],
                    group: maxGroup + 1
                }
                this.groupTag = maxGroup + 1;
                // console.log(this.groupTag)
            }
            // console.log(group)
            let res_group = [];
            for (let i in group) {
                res_group.push(group[i]);
            }
            // console.log(res_group);
            let outerArcData = pie().sort(null).padAngle(0.005).value(d => d.sum_len)(res_group);
            let outerArc = [];
            let groupArc = [];
            for (let d of outerArcData) {
                // console.log(d)
                let darcs = arc().innerRadius(this.distributionHeight * 0.99 / 2 - 5).outerRadius(this.distributionHeight * 0.99 / 2).cornerRadius(3)(d);
                outerArc.push(darcs);

                let groupArcData = pie().padAngle(0.005).startAngle(d.startAngle).endAngle(d.endAngle)(d.data.len.sort((a, b) => b - a));
                for (let g of groupArcData) {
                    let gArcs = arc().innerRadius(this.distributionHeight * 0.98 / 2 - 25).outerRadius(this.distributionHeight * 0.98 / 2 - 5)(g);
                    groupArc.push({
                        group: d.data.group,
                        arc: gArcs
                    });
                }
            }
            return [outerArc, groupArc];
        }
    },
    created () {
    },
    mounted () {
        this.elWidth = this.$refs.distributionView.offsetWidth;
        this.distributionHeight = this.$refs.distributionView.offsetHeight;
        // console.log(this.elWidth);
        const dataStore = useDataStore();
        let timeRange = dataStore.timeRange;
        this.monthArc = this.calcArc(timeRange);
        [this.mainArc, this.mainInnerArc, this.innerArc] = this.mainDataProcess();
        // console.log(this.innerArc)
        [this.outerArc, this.groupArc] = this.outerArcProgress(this.groupData);

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

/*chrome--------------------------------------------end*/
</style>
