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

                <span style="float: right; position: relative; top: 1px;">
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
                    <span style="margin-right: 20px;">
                        Select Group:
                        <el-select v-model="filterValue" class="m-2" placeholder="Select"
                            style="width: 70px; --el-border-color: white;">
                            <el-option v-for="item in filterOptions" :key="item" :label="item" :value="item" />
                        </el-select>
                    </span>
                    <span>
                        Select NFT Project:
                        <el-select v-model="filterValue" class="m-2" placeholder="Select"
                            style="width: 70px; --el-border-color: white;">
                            <el-option v-for="item in filterOptions" :key="item" :label="item" :value="item" />
                        </el-select>
                    </span>
                </span>
            </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
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

            <div ref="attr_bar" style="width: 29.7%; height: calc(100%); float: left;">
                <svg id="attr_bar" width="100%" height="calc(100%)">
                    <g>
                        <text x="5" y="20">[M-1: Preferential attachment]</text>
                        <g :transform="translate(5, 25, 0)">
                            <rect v-for="(item, i) in attachmentDataBar" :key="'bar' + i" :x="item.x"
                                :y="barHeight - item.y" :height="item.y" :width="item.w" stroke="#D9D9D9"
                                fill="#D9D9D9">
                            </rect>
                            <path :d="'M 5 ' + barHeight + ' L ' + (barWidth - 15) + ' ' + barHeight" fill="none"
                                stroke="#534f4f">
                            </path>
                            <path :d="'M -5 ' + (barHeight + 5) + ' L ' + (barWidth) + ' ' + (barHeight + 5)"
                                fill="none" stroke="#e0dede"></path>
                        </g>
                    </g>
                    <g :transform="translate(0, (barHeight + 29), 0)">
                        <text x="5" y="20">[M-2: Recency]</text>
                        <g :transform="translate(5, 25, 0)">
                            <rect v-for="(item, i) in recencyDataBar" :key="'bar' + i" :x="item.x"
                                :y="barHeight - item.y" :height="item.y" :width="item.w" stroke="#D9D9D9"
                                fill="#D9D9D9">
                            </rect>
                            <path :d="'M 5 ' + barHeight + ' L ' + (barWidth - 15) + ' ' + barHeight" fill="none"
                                stroke="#534f4f">
                            </path>
                            <path :d="'M -5 ' + (barHeight + 5) + ' L ' + (barWidth - 5) + ' ' + (barHeight + 5)"
                                fill="none" stroke="#e0dede"></path>
                        </g>
                    </g>

                    <g :transform="translate(0, 2 * (barHeight + 29), 0)">
                        <text x="5" y="20">[M-3: Propensity]</text>
                        <g :transform="translate(5, 25, 0)">
                            <rect v-for="(item, i) in propensityDataBar"  :key="'bar' + i" :x="item.x"
                                :y="barHeight - item.y" :height="item.y" :width="item.w" stroke="#D9D9D9"
                                fill="#D9D9D9">
                            </rect>
                            <path :d="'M 5 ' + barHeight + ' L ' + (barWidth - 15) + ' ' + barHeight" fill="none"
                                stroke="#534f4f">
                            </path>
                        </g>
                    </g>
                </svg>
            </div>
            <!-- <div ref="groupPie" style="width: 70.3%; height: 100%; float: right;">
                <svg id="groupPie" width="100%" height="calc(100%)"></svg>
            </div> -->
            <div style="height: 100%; width: 70.3%; float: right; overflow-x: scroll; overflow-y: hidden; white-space: nowrap" ref="groupView">
                <!-- <div v-for="(item, i) in groupSet" :key="'group' + i" :style="{
                    'width': groupWidth / 4 + 'px',
                    'height': '100%',
                    'padding': '0px 5px 5px 5px',
                    'border': '1px solid purple',
                    'display': 'inline-block'
                }"> -->
                <svg v-for="(item, i) in groupSet" :key="'group' + i" height="100%" width="25%">
                    <!-- <circle cx="10" cy="10" r="10" fill="red"></circle> -->
                    <text x="50%" y="20" font-size="16" text-anchor="middle" fill="#534F4F" font-weight="bold">{{
                        'Group ' + item
                    }}</text>
                    <g :transform="translate(groupWidth / 8, groupWidth / 8 + 15, 0)">
                        <text x="0" :y="-(groupWidth / 8 - 18)" font-size="7" text-anchor="middle" fill="#534F4F"
                            dy="0.3em" font-weight="bold">{{
                            '2022' }}</text>

                        <text v-for="(t_item, t_i) in monthName" :key="'gt' + t_i" :transform="translate(0, 0, 0)"
                            :x="Math.sin((Math.PI * (30 * t_i + 15)) / 180) * (groupWidth / 8 - 18)"
                            :y="-Math.cos((Math.PI * (30 * t_i + 15)) / 180) * (groupWidth / 8 - 18)" font-size="7"
                            dy="0.3em" text-anchor="middle" fill="#534F4F" font-weight="bold">{{ t_item }}</text>
                        <text v-for="(t_item, t_i) in axisName" :key="'gt' + t_i" :transform="translate(0, 0, 0)"
                            :x="Math.sin((Math.PI * (90 * t_i)) / 180) * (groupWidth / 8 - 40)"
                            :y="-Math.cos((Math.PI * (90 * t_i)) / 180) * (groupWidth / 8 - 40)" font-size="12" dy="0.3em"
                            text-anchor="middle" fill="#534F4F" font-weight="bold">{{ t_item }}</text>
                        <g :transform="translate(0, 0, 0)">
                            <path stroke-dasharray="5.5"
                                :d="'M 0 ' + -(groupWidth / 8 - 48) + ' L 0 ' + ((groupWidth / 8 - 48))" fill="none"
                                stroke="#D9D9D9"></path>
                            <path stroke-dasharray="5.5"
                                :d="'M ' + -(groupWidth / 8 - 48) + ' 0 L ' + ((groupWidth / 8 - 48)) + ' 0'" fill="none"
                                stroke="#D9D9D9"></path>
                            <circle x="0" y="0" :r="(groupWidth / 8 - 48)" fill="none" stroke="#D9D9D9"
                                stroke-dasharray="5.5"></circle>
                            <circle x="0" y="0" :r="(groupWidth / 8 - 48) * 2 / 3" fill="none" stroke="#D9D9D9"
                                stroke-dasharray="5.5"></circle>
                            <circle x="0" y="0" :r="(groupWidth / 8 - 48) * 1 / 3" fill="none" stroke="#D9D9D9"
                                stroke-dasharray="5.5"></circle>
                            <path v-for="(arc_item, arc_i) in monthArc" :key="'arc' + arc_i" :d="arc_item"
                                stroke="#D9D9D9" fill="none"></path>
                        </g>
                    </g>

                    <g :transform="translate(0, groupHeight - 55, 0)">
                        <text x="50%" y="20" font-size="14" text-anchor="middle" fill="#534F4F" font-weight="bold">{{
                        'Num_Projects 25' }}</text>
                        <text x="50%" y="40" font-size="14" text-anchor="middle" fill="#534F4F" font-weight="bold">{{
                            'Ave_Impact 60 '
                        }}</text>
                    </g>
                </svg>
                <!-- </div> -->
            </div>

            <!-- <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
            <div style="width: 100%; height: calc((100% - 26px) / 3);">
                [F-2: Recency]
                <svg width="31.8%" height="calc(100% - 30px)">
                    <rect v-for="(item, i) in recencyData" :key="'bar' + i" :x="5 + i * (barWidth - 5) / 20"
                        :y="barHeight - item" :height="item" :width="(barWidth - 5) / 20" stroke="#D9D9D9" fill="#D9D9D9">
                    </rect>
                    <path :d="'M 5 ' + barHeight + ' L ' + barWidth + ' ' + barHeight" fill="none" stroke="#534f4f"></path>
                </svg>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
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
<script>
import { scaleLinear } from 'd3-scale';
import { select } from 'd3-selection';
import { arc, pie } from 'd3-shape';

export default {
    name: 'APP',
    props: [''],
    data() {
        return {
            filterValue: 'Group',
            filterOptions: ['Group'],
            groupSet: [1, 2, 3, 4, 5, 6],
            monthStep: [20, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20],
            monthName: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'],
            axisName: ['F1', 'F3', 'Imp', 'F2'],
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
            monthArc: []
        }
    },
    methods: {
        translate(x, y, deg) {
            return 'translate(' + x + ',' + y + ') rotate(' + deg + ')';
        },
        
        calcArc () {
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
        dataProcess() {
            let xScale = scaleLinear([0, 20], [5, this.barWidth - 15])
            let yScale = scaleLinear([0, 5], [0, this.barHeight]);
            let a = [], r = [], p = [];
            for (let i in this.attachmentData) {
                a.push({
                    x: xScale(i),
                    y: yScale(this.attachmentData[i]),
                    w: (this.barWidth - 20) / 20
                });
                r.push({
                    x: xScale(i),
                    y: yScale(this.recencyData[i]),
                    w: (this.barWidth - 20) / 20
                });
                p.push({
                    x: xScale(i),
                    y: yScale(this.propensityData[i]),
                    w: (this.barWidth - 20) / 20
                });
            }
            console.log([a, r, p]);
            return [a, r, p];
            // console.log(this.attachmentData)
        }
    },
    created() {
    },
    mounted() {
        this.barHeight = (this.$refs.attr_bar.offsetHeight - 85) / 3;
        this.barWidth = this.$refs.attr_bar.offsetWidth;
        this.groupHeight = this.$refs.groupView.offsetHeight;
        this.groupWidth = this.$refs.groupView.offsetWidth;
        
        this.monthArc = this.calcArc();
        [this.attachmentDataBar, this.recencyDataBar, this.propensityDataBar] = this.dataProcess();
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
