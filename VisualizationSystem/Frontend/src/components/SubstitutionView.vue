<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2023-02-11 23:40:58
 * @LastEditTime: 2023-03-11 13:47:38
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
                <svg height="27" width="400" transform="translate(0, 10)">
                    <g v-for="(item, i) in colormap" :key="'gcolor' + i">
                        <rect :x="0 + i * 50" :y="2" :width="50" :height="9" :fill="item" :stroke="'#534f4f'"></rect>
                        <text :x="0 + i * 50 + 25" :y="23" font-size="12" text-anchor="middle" fill="#534F4F">{{ 'Group' + i
                        }}</text>
                    </g>
                </svg>
                Filter by:
                <el-select v-model="filterValue" class="m-2" placeholder="Select"
                    style="width: 50px; --el-border-color: white;">
                    <el-option v-for="item in filterOptions" :key="item" :label="item" :value="item" />
                </el-select>
            </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
        </div>
        <div class="frameworkBody">
            <div style="height: 100%; width: 100%; margin-top: 5px;" ref="distributionView">
                <span style="position: absolute; top: 0px; color: #ABACBE; font-size: 14px;z-index: 100;">Selecting
                    <span class="php">16 projects</span> from <span class="php">55 results</span>
                    <span>
                        <p style="cursor:pointer; margin-top: 10px;">
                            <svg t="1678613511201" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="5014" width="25" height="25"><path d="M580.76 908.62a53.366667 53.366667 0 0 1-46.28-26.666667L404.1 656.133333l-154.666667 148.586667A21.333333 21.333333 0 0 1 213.333333 789.333333V106.666667a21.333333 21.333333 0 0 1 6.706667-15.526667c5.333333-5.02 15.26-8.74 25.72-2.7l91.946667 53.086667 498.833333 288a21.333333 21.333333 0 0 1-4.733333 38.966666l-206 59.64 130.386666 225.826667a53.333333 53.333333 0 0 1-19.526666 72.86l-129.333334 74.666667a53.02 53.02 0 0 1-26.573333 7.133333zM408.953333 600.546667a20.666667 20.666667 0 0 1 3 0.213333 21.333333 21.333333 0 0 1 15.48 10.453333l144 249.413334a10.666667 10.666667 0 0 0 14.566667 3.906666l129.333333-74.666666a10.666667 10.666667 0 0 0 3.906667-14.573334l-144-249.413333a21.333333 21.333333 0 0 1 12.546667-31.16l184.053333-53.286667L256 143.62v595.633333l138.18-132.76a21.333333 21.333333 0 0 1 14.773333-5.946666z" fill="#5C5C66" p-id="5015"></path></svg></p>
                            <p style="cursor:pointer; margin-top: 10px;">
                                <svg t="1678615963305" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="8533" width="25" height="25"><path d="M1017.6 492.8C1011.2 480 787.2 192 512 192 236.8 192 12.8 480 6.4 492.8c-6.4 12.8-6.4 25.6 0 38.4C12.8 544 236.8 832 512 832c275.2 0 499.2-288 505.6-300.8 6.4-12.8 6.4-25.6 0-38.4zM512 768c-204.8 0-384-192-441.6-256C128 448 307.2 256 512 256s384 192 441.6 256c-57.6 64-236.8 256-441.6 256z" fill="#5C5C66" p-id="8534"></path><path d="M512 352C422.4 352 352 422.4 352 512s70.4 160 160 160 160-70.4 160-160S601.6 352 512 352z m0 256c-51.2 0-96-44.8-96-96S460.8 416 512 416s96 44.8 96 96S563.2 608 512 608z" fill="#5C5C66" p-id="8535"></path></svg>
                            </p>
                            <p style="cursor:pointer; margin-top: 10px;">
                                <svg t="1678616026391" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="9500" width="25" height="25"><path d="M935.161672 427.51891c-14.511505-11.744485-37.643342-9.155521-49.1627 5.403057l-12.9438 16.20917c-0.926092-5.842055-1.995447-11.625782-3.158946-17.325597C831.326792 245.594511 666.360623 110.434182 477.668077 110.434182c-27.455305 0-55.099922 2.885723-82.198094 8.562003C179.036629 164.405397 39.60195 378.546545 84.655052 596.34499c38.522362 186.222285 203.488531 321.383638 392.229173 321.383638 27.430746 0 55.076386-2.873444 82.174558-8.549723 75.144444-15.746636 144.18589-53.508681 198.288089-108.002806l1.87572-1.662873c1.757017-1.74576 2.778276-3.432169 2.588965-3.443425l1.781576-2.387373c2.137687-3.527336 4.65502-9.191336 4.65502-16.173354 0-17.361413-14.035668-31.479969-31.326473-31.479969-4.275373 0-8.454556 0.914836-12.325723 2.612501l-1.90028-1.318018-8.644891 8.65717c-46.359864 46.478568-104.261599 78.042447-167.484525 91.283006-22.657023 4.750187-45.766346 7.160073-68.684312 7.160073-157.818375 0-295.733445-113.073288-327.96145-268.87268-37.738509-182.291766 78.849836-361.484961 259.918751-399.448598 22.657023-4.750187 45.766346-7.160073 68.708871-7.160073 157.793816 0 295.709909 113.061009 327.96145 268.860401 0.427742 2.101871 0.855484 4.227278 1.258667 6.364965l-13.751189-11.091616c-14.511505-11.768021-37.59627-9.1678-49.1627 5.390777-12.017708 15.056927-9.619078 37.156248 5.343705 49.269124l78.089519 63.1032c0.14224 0.106424 0.285502 0.213871 0.427742 0.332575l3.491521 2.814092 0.712221 0c6.483668 3.657296 15.770172 4.964058 21.065781 4.322445 9.475815-0.890276 17.954931-5.485945 23.940249-12.93152l62.723553-78.659501C952.498526 461.635939 950.052824 439.560154 935.161672 427.51891z" fill="#5C5C66" p-id="9501"></path></svg>
                            </p>
                    </span>
                </span>
                <div style="height: calc(100% - 0px); width: 100%;">
                <svg width="100%" height="100%" v-show="showTag">
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
                                <path v-for="(arc_item, arc_i) in monthArc" :key="'select_time' + arc_i" :d="arc_item"
                                    fill="#C6BCBC" stroke="#C6BCBC"></path>
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

                            </g>
                            <g :transform="translate(0, 0, 0)">

                                <path v-for="(arc_item, arc_i) in outerArc" :key="'arc' + arc_i" :d="arc_item" stroke="none"
                                    :fill="arc_i == groupTag ? 'none' : colormap[arc_i]"></path>

                                <path v-for="(arc_item, arc_i) in groupArc" :key="'arc' + arc_i" :d="arc_item.arc"
                                    :fill="arc_item.group == groupTag ? 'white' : colormap[parseInt(arc_item.group)]"
                                    :stroke="arc_item.group == groupTag ? '#C6BCBC' : colormap[parseInt(arc_item.group)]"
                                    stroke-width="1"></path>
                            </g>
                            <g>
                                <g v-for="(a_item, a_i) in innerArea" :key="'ia' + a_i"
                                    :transform="translate(0, 0, a_i * 12)">
                                    <path :d="a_item[innerAreaTag]" fill="#efa566" stroke="#efa566"></path>
                                </g>
                            </g>

                            <g>
                                <circle v-for="(c_item, c_i) in scatterData" :key="'gc' + c_i" :cx="c_item.cx"
                                    :cy="c_item.cy" :r="5" :fill="colormap[c_item.group]" @mouseenter="msTest(c_item)">
                                </circle>
                            </g>
                            <g>

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
import { arc, area, curveBasis, pie } from 'd3-shape';
import { useDataStore } from "../stores/counter";

export default {
    name: "APP",
    props: ["groupData"],
    data () {
        return {
            innerAreaTag: 'm1d',
            elWidth: 1000,
            distributionHeight: 0,
            groupHeight: 0,
            filterValue: "M-1",
            filterOptions: ["M-1", "M-2", "M-3", "IMP"],
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
            showTag: 0
        };
    },
    methods: {
        translate (x, y, d) {
            return `translate(${x}, ${y}) rotate(${d})`;
        },
        calcTime (timeRange) {

        },
        msTest (data) {
            // console.log(data)
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
            } else if (st[0] == et[0]) {
                if (st[1] != et[1]) {
                    let cnt = 0;
                    console.log(st[0], st[1]);
                    SA = (parseInt(st[1] - 1) * 30 + 30 * parseInt(st[2]) / this.monthDay[st[0]][st[1] - 1]) * Math.PI / 180;
                    let aData = [{ v: ((1 - parseInt(st[2]) / this.monthDay[st[0]][st[1] - 1]) * 20), id: cnt }];
                    for (let i = parseInt(st[1]) + 1; i < parseInt(et[1]); ++i) {
                        cnt++;
                        aData.push({
                            v: 20,
                            id: cnt
                        })
                    }
                    aData.push({
                        v: (parseInt(et[2]) / this.monthDay[et[0]][et[1] - 1]) * 20,
                        id: cnt
                    });
                    EB = (parseInt(et[1] - 1) * 30 + 30 * parseInt(et[2]) / this.monthDay[et[0]][et[1] - 1]) * Math.PI / 180;

                    let sArcData = pie().startAngle(SA).endAngle(EB).padAngle(0.006).sort((a, b) => a.id - b.id).value(d => d.v)(aData);


                    for (let i in sArcData) {
                        let dArc = arc().innerRadius(st[0] == '2021' ? this.distributionHeight * 0.81 / 2 - 5 : this.distributionHeight * 0.85 / 2).outerRadius(st[0] == '2021' ? this.distributionHeight * 0.77 / 2 - 5 : this.distributionHeight * 0.81 / 2)(sArcData[i]);
                        Marc.push(dArc);
                    }
                } else if (st[1] == et[1]) {
                    let cnt = 0;
                    SA = (parseInt(st[1] - 1) * 30 + 30 * parseInt(st[2]) / this.monthDay[st[0]][st[1] - 1]) * Math.PI / 180;
                    let aData = [{ v: ((parseInt(et[2]) - parseInt(st[2]) / this.monthDay[st[0]][st[1] - 1]) * 20), id: 0 }];
                    EB = (parseInt(et[1] - 1) * 30 + 30 * parseInt(et[2]) / this.monthDay[et[0]][et[1] - 1]) * Math.PI / 180;

                    let sArcData = pie().startAngle(SA).endAngle(EB).padAngle(0.006).sort((a, b) => a.id - b.id).value(d => d.v)(aData);
                    // console.log(sArcData);

                    for (let i in sArcData) {
                        let dArc = arc().innerRadius(st[0] == '2021' ? this.distributionHeight * 0.81 / 2 - 5 : this.distributionHeight * 0.85 / 2).outerRadius(st[0] == '2021' ? this.distributionHeight * 0.77 / 2 - 5 : this.distributionHeight * 0.81 / 2)(sArcData[i]);
                        Marc.push(dArc);
                    }
                }
            }
            return Marc;
        },
        calcScatter (data) {
            let scatterData = [];
            let t_h = Math.abs((-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .53 / 2 + 15)) - (-Math.cos(((0) * Math.PI) / 180) * (this.distributionHeight * .53 / 2 + 15)));
            let areaData = [];
            for (let i = 0; i < 30; ++i) {
                areaData.push({
                    project: [],
                    m1Area: new Array(5).fill(0),
                    m2Area: new Array(5).fill(0),
                    m3Area: new Array(5).fill(0),
                    impArea: new Array(5).fill(0)
                })
            }
            let m1_max = 0, m2_max = 0, m3_max = 0, imp_max = 0;
            for (let i in data) {
                // console.log(data[i]);
                let tp = {
                    data: data[i],
                    group: data[i].Group,
                    x: (parseFloat(data[i].Holder) + parseFloat(data[i].Buyer) * 2) / Math.sqrt(3),
                    y: parseFloat(data[i].Holder),
                    cx: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .53 / 2 + 15)) + (parseFloat(data[i].Holder) + parseFloat(data[i].Buyer) * 2) / Math.sqrt(3) * t_h,
                    cy: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .53 / 2 + 15)) - parseFloat(data[i].Holder) * t_h
                };
                scatterData.push(tp);
                let t_cnt = (Math.acos(tp.cy / (Math.sqrt(Math.pow(tp.cx, 2) + Math.pow(tp.cy, 2)))) / (Math.PI / 180) + (tp.cx >= 0 ? 0 : 180) - 6) / 12;
                // console.log(Math.floor(t_cnt));

                let m11 = Math.floor(data[i]['M1'] / (1 / 5));
                let m22 = Math.floor(data[i]['M2'] / (1 / 5));
                let m33 = Math.floor(data[i]['M3'] / (1 / 5));
                let impp = Math.floor((Math.random()) / (1 / 5));
                m1_max = Math.max(m1_max, m11);
                m2_max = Math.max(m2_max, m22);
                m3_max = Math.max(m3_max, m33);
                imp_max = Math.max(imp_max, impp);
                m11 = m11 == 5 ? m11 - 1 : m11;
                m22 = m22 == 5 ? m22 - 1 : m22;
                m33 = m33 == 5 ? m33 - 1 : m33;
                impp = impp == 5 ? impp - 1 : impp;
                areaData[Math.floor(t_cnt)].project.push(data[i]);
                areaData[Math.floor(t_cnt)].m1Area[m11]++;
                areaData[Math.floor(t_cnt)].m2Area[m22]++;
                areaData[Math.floor(t_cnt)].m3Area[m33]++;
                areaData[Math.floor(t_cnt)].impArea[impp]++;
            }
            let ayScale = scaleLinear([0, 4], [this.distributionHeight * .53 / 2 + 15, this.distributionHeight * .71 / 2 - 10]);
            let m1Scale = scaleLinear([0, m1_max], [0, 25]);
            let m2Scale = scaleLinear([0, m2_max], [0, 25]);
            let m3Scale = scaleLinear([0, m3_max], [0, 25]);
            let impScale = scaleLinear([0, imp_max], [0, 25]);
            let ag1 = area()
                .curve(curveBasis)
                .x0(d => m1Scale(d))
                .x1(d => -m1Scale(d))
                .y((d, i) => ayScale(i));
            let ag2 = area()
                .curve(curveBasis)
                .x0(d => m2Scale(d))
                .x1(d => -m2Scale(d))
                .y((d, i) => ayScale(i));
            let ag3 = area()
                .curve(curveBasis)
                .x0(d => m3Scale(d))
                .x1(d => -m3Scale(d))
                .y((d, i) => ayScale(i));
            let ag4 = area()
                .curve(curveBasis)
                .x0(d => impScale(d))
                .x1(d => -impScale(d))
                .y((d, i) => ayScale(i));
            let res_area = [];
            for (let i in areaData) {
                res_area.push({
                    m1d: ag1(areaData[i].m1Area),
                    m2d: ag2(areaData[i].m2Area),
                    m3d: ag3(areaData[i].m3Area),
                    impd: ag4(areaData[i].impArea)
                });
                // break;
            }


            return [scatterData, res_area];
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
                group[data[i].Group].sum_len++;
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
        this.showTag = 1;
        let timeRange = dataStore.timeRange;
        // console.log(timeRange);

        this.monthArc = this.calcArc(timeRange);
        [this.mainArc, this.mainInnerArc, this.innerArc] = this.mainDataProcess();
        // console.log(this.innerArc)
        [this.outerArc, this.groupArc] = this.outerArcProgress(this.groupData);
        [this.scatterData, this.innerArea] = this.calcScatter(this.groupData);
        dataStore.$subscribe((mutations, state) => {
        })

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
