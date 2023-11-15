<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2023-03-17 11:04:09
 * @LastEditors: Qing Shi
 * @LastEditTime: 2023-11-13 18:13:32
-->
<template>
    <div style="height: 100%">
        <div class="frameworkTitle">
            <span class="title" style="float: left;">
                <svg t="1676053813985" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
                    p-id="37153" width="20" height="20">
                    <path
                        d="M170.666667 42.666667l682.666667 0q52.992 0 90.496 37.504t37.504 90.496l0 682.666667q0 52.992-37.504 90.496t-90.496 37.504l-682.666667 0q-52.992 0-90.496-37.504t-37.504-90.496l0-682.666667q0-52.992 37.504-90.496t90.496-37.504zM896 742.997333l-213.333333-213.333333-366.336 366.336 537.002667 0q17.664 0 30.165333-12.501333t12.501333-30.165333l0-110.336zM853.333333 128l-682.666667 0q-17.664 0-30.165333 12.501333t-12.501333 30.165333l0 682.666667q0 17.664 12.501333 30.165333t30.165333 12.501333l25.002667 0 486.997333-486.997333 213.333333 213.333333 0-451.669333q0-17.664-12.501333-30.165333t-30.165333-12.501333zM341.333333 213.333333q52.992 0 90.496 37.504t37.504 90.496-37.504 90.496-90.496 37.504-90.496-37.504-37.504-90.496 37.504-90.496 90.496-37.504zM341.333333 298.666667q-17.664 0-30.165333 12.501333t-12.501333 30.165333 12.501333 30.165333 30.165333 12.501333 30.165333-12.501333 12.501333-30.165333-12.501333-30.165333-30.165333-12.501333z"
                        p-id="37154" font-size="14" fill="#534f4f"></path>
                </svg>
                &nbsp; Impact Dynamic View
            </span>
            <span style="float: right; position: relative; top: -2px; font-size: 16px;">
                <svg height="27" width="200" transform="translate(0, 10)">
                    <g v-for="(item, i) in colormap1" :key="'icolor' + i" :transform="translate(20, 0, 0)">
                        <rect :x="0 + i * 40" :y="2" :width="9" :height="9" :fill="item" :stroke="'#534f4f'"></rect>
                        <text :x="0 + i * 40 + 4.5" :y="25" font-size="14" text-anchor="middle">{{ i == 0 ? 'Sell' : i
                            == 1 ? 'Buy' : 'Hold' }}</text>
                    </g>
                    <g v-for="(item, i) in colormap2" :key="'icolor' + i" :transform="translate(140, 0, 0)">
                        <rect :x="0 + i * 40" :y="2" :width="9" :height="9" :fill="item" :stroke="'#534f4f'"></rect>
                        <text :x="i * 40 + 4.5" :y="25" font-size="14"
                            text-anchor="middle">{{ i == 0 ? '<0' : '>0' }}</text>
                    </g>
                </svg>
            </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
        </div>
        <div class="frameworkBody">
            <div class="tooltipName"
                style="opacity: 0; background-color: white; border: solid; border-width: 2px; border-radius: 5px; padding: 5px; position: absolute; z-index: 100; left: -1000px; width: 150px; text-align: center;">
                <div>#Project Name</div>
                <div>{{ mouseoverProjectName }}</div>
            </div>
            <div style="width: 100%; height: 46%; margin-top: 5px;">
                <div>
                    [Preferential attachment view]
                </div>
                <div ref="correlationView" style="position: relative; left: 0px; width: 65%; height: calc(100% - 35px)">
                    <svg width="100%" height="100%" v-show="selectGroupTag != -1">
                        <defs>
                            <clipPath id="clipPath">
                                <circle :cx="15" :cy="15" :r="15"></circle>
                            </clipPath>
                        </defs>


                        <g :transform="translate(30, 50, 0)">
                            <g>
                                <g :transform="translate(-5, -70, 0)">
                                    <text x="-30" y="35" dx="0.5em" dy="0.3em" font-size="16" fill="#534f4f">Group:</text>
                                    <text x="25" y="35" dx="0.5em" dy="0.3em" font-size="16" text-decoration="underline"
                                        fill="#534f4f">{{ selectGroupTag }}</text>
                                    <!-- <text x="-30" y="60" dx="0.5em" dy="0.3em" font-size="14" fill="#534f4f">Time
                                        Slot:</text>
                                    <text x="37" y="60" dx="0.5em" dy="0.3em" font-size="14" text-decoration="underline"
                                        fill="#534f4f">{{ timeSelectionText }}</text> -->
                                </g>
                                <g v-if="legendTag != 0">
                                    <!-- <g v-for="(item, i) in legendData" :key="'correlation_circle_' + i"> -->
                                    <g :transform="translate(cvWidth * 0.15 + 30, cvWidth * 0.15 + 30, 0)">
                                        <!-- <path v-for="(a_item, a_i) in legendData.outArc" :key="'corr_out_' + a_i"
                                            :d="a_item.dLegend" :fill="a_item.fill"></path> -->
                                        <!-- <path v-for="(a_item, a_i) in legendData.outArc" :key="'corr_out_' + a_i"
                                            :transform="translate(0, 0, a_i * 120)" :d="'M0 68L0 75'" :fill="'none'"
                                            stroke="black" stroke-width="2"></path> -->

                                        <path v-for="(a_item, a_i) in legendData.innerArc" :key="'corr_out_' + a_i"
                                            :d="a_item.dLegendOut" stroke="white" :fill="a_item.fill2"></path>
                                        <path v-for="(a_item, a_i) in legendData.innerArc" :key="'corr_out_' + a_i"
                                            :d="a_item.dLegend" stroke="none" :fill="a_item.fill"></path>
                                        <!-- <text v-for="(o, i) in legendData.innerArc" :key="'out_k' + i" text-anchor="middle"
                                            :transform="translatePos(o.textTrans)" dy="0.5em" font-size="18" fill="black"
                                            style="font-weight: bold;">
                                            {{ o.text }}
                                        </text>
                                        <text v-for="(o, i) in legendData.outArc" :key="'out_k' + i"
                                            :text-anchor="i == 0 ? 'middle' : i == 1 ? 'start' : 'end'"
                                            :transform="translatePos([(i == 0) ? 0 : (i == 1 ? (cvWidth * .15 + 5) * Math.cos(Math.PI / 6) : (-(cvWidth * .15 + 5) * Math.cos(Math.PI / 6))), (i == 0 ? (-cvWidth * .15 - 5) : ((cvWidth * .15 + 5) * Math.sin(Math.PI / 6)))])" style="font-weight: bold;"
                                            dy="0em" font-size="18" fill="#534f4f">
                                            {{ o.text }}
                                        </text>
                                        <text v-for="(o, i) in legendData.outArc" :key="'out_k' + i" 
                                            :text-anchor="i == 0 ? 'middle' : i == 1 ? 'start' : 'end'"
                                            :transform="translatePos([(i == 0) ? 0 : (i == 1 ? (cvWidth * .15 + 5) * Math.cos(Math.PI / 6) : (-(cvWidth * .15 + 5) * Math.cos(Math.PI / 6))), (i == 0 ? (-cvWidth * .15 - 5) : ((cvWidth * .15 + 5) * Math.sin(Math.PI / 6)))])" style="font-weight: bold;" :dx="i == 1 ? '-1em' :  i == 2 ? '1em' : '0em'" 
                                            :dy="i == 0 ? '-1.5em' : '1.5em'" font-size="16" fill="#534f4f">
                                            {{ 'CC-' + o.type_name + 's' }}
                                        </text> -->

                                    </g>
                                    <!-- <path d="M 0 -15 L 60 -15" fill="none" stroke="#C6BCBC"></path>
                                        <path d="M 18 10 L 60 10" fill="none" stroke="#C6BCBC"></path>
                                        <text x="55" y="-15" dx="0.5em" dy="0.3em" font-size="14" fill="#534f4f">#{{
                                            item.co_sum }}</text>
                                        <text x="55" y="10" dx="0.5em" dy="0.3em" font-size="14" fill="#534f4f">{{
                                            item.buyer_pre }}</text> -->
                                    <!-- </g> -->
                                </g>
                            </g>
                        </g>
                        <g>
                            <path v-for="(item, i) in lineData" :key="'cross_line' + i" :d="item" fill="none"
                                stroke="#C6BCBC"></path>
                        </g>
                        <g>
                            <g v-for="(item, i) in correlationData" :key="'correlation_circle_' + i">
                                <path :d="item.HighlightPath" :stroke="item.circleData.stroke" :stroke-width="4" fill="none"
                                    :opacity="item.opacity"></path>
                            </g>
                        </g>
                        <g>
                            <g v-for="(item, i) in correlationData" :key="'correlation_circle_' + i"
                                :transform="translate(item.x, item.y, 0)" @mouseover="hoverCorrelation(item)"
                                @mouseout="outCorrelation()"
                                @click="clickCorrelation(i, item.projectA, item.projectB, item)">
                                <circle :x="0" :y="0" :fill="'white'" :stroke="item.circleData.stroke"
                                    :r="item.circleData.r" :opacity="item.opacity" :stroke-width="4"></circle>
                                <!-- <path :d="item.HighlightPath" :stroke="'black'" :stroke-width="4" fill="none" :opacity="item.opacity" :transform="translate(-item.x, -item.y, 0)"></path> -->

                                <!-- <path v-for="(a_item, a_i) in item.outArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                    :fill="a_item.fill"></path> -->
                                <path v-for="(a_item, a_i) in item.innerArc" :key="'corr_out_' + a_i" :d="a_item.dOut"
                                    stroke="white" :fill="a_item.fill2"></path>
                                <path v-for="(a_item, a_i) in item.innerArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                    stroke="#534f4f" :fill="a_item.fill"></path>
                            </g>
                        </g>
                        <g>
                            <g v-for="(item, i) in textPlace" :key="'cross_text' + i"
                                :transform="translate(item.pos[0], item.pos[1], 0)">
                                <g clip-path="url(#clipPath)" :transform="translate(-40, -15, 0)"
                                    @mouseenter="mouseoverName($event, item.name)" @mouseout="mouseoutName">
                                    <image :href="item.link" x="0" y="0" height="30" width="30" />
                                </g>
                            </g>
                        </g>
                    </svg>
                </div>
                <div ref="correlationTable"
                    style="float: right; position: absolute; right: 0px; top: 0px; width: calc(35% - 10px); height: calc(100%);">
                    <svg width="100%" height="100%" v-show="selectGroupTag != -1">

                        <g>
                            <g v-for="(item, i) in textPlace" :key="'cross_text' + i"
                                :transform="translate(0, item.pos[1] + 25, 0)">
                                <g>
                                    <rect v-for="(r_item, r_i) in item.rectData" :key="'pro_bar_' + r_i" :x="r_item.x"
                                        :y="-12.5" :width="r_item.w" :height="r_item.h" :fill="r_item.fill"></rect>
                                </g>
                                <!-- <text :x="0" :y="0" font-size="14" text-anchor="start" dx="-0.5em" dy="0.5em">
                                                                                            {{ item.name }}
                                                                                        </text> -->
                            </g>
                        </g>

                        <g>
                            <g v-for="(item, i) in correlationData" :key="'selectKey' + i">
                                <path v-for="(p_item, p_i) in item.lineData" :key="'select_line_' + p_i"
                                    :transform="translate(0, 25, 0)"
                                    :d="'M' + (p_item.x + p_item.rw) + ',' + p_item.y + 'L' + (p_item.x + p_item.rw) + ',' + (p_item.y + p_item.h)"
                                    :fill="'none'" :stroke="p_item.stroke" :stroke-width="3" :opacity="item.opacity"></path>
                                <text v-for="(t_item, t_i) in item.lineData" :key="'select_text_' + t_i"
                                    :x="ctWidth / 3 + t_item.x" :y="t_item.y + t_item.h" fill="black" text-anchor="end"
                                    dx="-0.1em" dy="1em" style="font-weight: bold;"
                                    :opacity="item.opacity">{{ t_item.text }}</text>
                            </g>
                        </g>
                        <g transform="translate(0, 20)">
                            <!-- <text x="95" y="20" font-size="14">#Holders-#Buyers-#Sellers</text> -->
                            <text font-size="16" :x="ctWidth / 3 - ctWidth / 6" y="20" text-anchor="middle"
                                fill="#534f4f">#Seller</text>
                            <text font-size="14" x="5" y="45" text-anchor="start" fill="#534f4f"
                                font-family="sans-serif">0</text>
                            <text font-size="14" :x="ctWidth / 3 - 5" y="45" text-anchor="end" fill="#534f4f"
                                font-family="sans-serif">{{ max_people }}</text>
                            <text font-size="16" :x="ctWidth * 2 / 3 - ctWidth / 6" y="20" text-anchor="middle"
                                fill="#534f4f">#Buyer</text>
                            <text font-size="14" :x="ctWidth / 3 + 5" y="45" text-anchor="start" fill="#534f4f"
                                font-family="sans-serif">0</text>
                            <text font-size="14" :x="ctWidth * 2 / 3 - 5" y="45" text-anchor="end" fill="#534f4f"
                                font-family="sans-serif">{{ max_people }}</text>
                            <text font-size="16" :x="ctWidth - ctWidth / 6" y="20" text-anchor="middle"
                                fill="#534f4f">#Holder</text>
                            <text font-size="14" :x="ctWidth * 2 / 3 + 5" y="45" text-anchor="start" fill="#534f4f"
                                font-family="sans-serif">0</text>
                            <text font-size="14" :x="ctWidth * 3 / 3 - 5" y="45" text-anchor="end" fill="#534f4f"
                                font-family="sans-serif">{{ max_holder }}</text>
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
                    </svg>
                </div>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
            <div style="width: 100%; height: 54%; margin-top: 5px;">
                <div style="height: 35px;">
                    [Impact dynamics of individual NFT project]
                    <span style="float: right; position: relative; top: 1px; font-size: 16px;">
                        Sort by:
                        <el-select v-model="sortValue" class="m-2" placeholder="Select"
                            style="width: 85px; --el-border-color: white;">
                            <el-option v-for="item in sortOptions" :key="item" :label="item.label" :value="item.value" />
                        </el-select>
                    </span>
                </div>
                <div style="height: calc(100% - 35px); width: 100%;">
                    <div ref="nameSpace" id="nameSpace"
                        style="float: left; width: calc(15% + 30px); height: 93%; overflow: hidden;">
                        <svg width="100%" v-show="selectGroupTag != -1" :height="pjWidth * projectNum / 2 - 1"
                            id="nameSpaceSvg">
                            <g v-for="(item, i) in timeData" :key="'time_x' + i">
                                <g :transform="translate((nameWidth) / 2 - 10, i * pjHeight / 2 + 100, 0)">

                                    <path v-for="(a_item, a_i) in item.name.outArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                        :fill="a_item.fill" :stroke="a_item.stroke == 1 ? '#534f4f' : 'none'"></path>
                                    <path v-for="(a_item, a_i) in item.name.innerArc" :key="'corr_out_' + a_i" :d="a_item.d"
                                        :fill="a_item.fill"></path>

                                    <clipPath id="clipPath20">
                                        <circle :cx="item.name.img_r * 0.75" :cy="item.name.img_r * 0.75"
                                            :r="item.name.img_r / 2"></circle>
                                    </clipPath>

                                    <g clip-path="url(#clipPath20)"
                                        :transform="translate(-item.name.img_r * 0.75, -item.name.img_r * 0.75, 0)">
                                        <image :href="item.name.link" x="0" y="0" :height="item.name.img_r * 1.5"
                                            :width="item.name.img_r * 1.5" />
                                    </g>
                                </g>
                                <!-- <g :transform="translate(nameWidth / 2 - 10, i * pjHeight / 2 + 180, 0)">
                                                        
                                                        <text fill="#534f4f" font-size="16" text-anchor="middle">{{ item.name.name }}</text>
                                                    </g> -->
                                <g :transform="translate(nameWidth / 2 - 10, i * pjHeight / 2 + 200, 0)">
                                    <text fill="#534f4f" font-size="16" text-anchor="middle">Time Slot: </text>
                                    <text fill="#534f4f" font-size="16" text-anchor="middle" text-decoration="underline"
                                        dy="2em">{{
                                            item.name.timeS }}</text>
                                    <text fill="#534f4f" font-size="16" text-anchor="middle" dy="3.5em">{{
                                        '-' }}</text>
                                    <text fill="#534f4f" font-size="16" text-anchor="middle" text-decoration="underline"
                                        dy="5em">{{
                                            item.name.timeE }}</text>

                                </g>
                                <g>
                                    <path
                                        :d="'M0 ' + (pjHeight / 2 * (i + 1)) + ' L' + nameWidth + ' ' + (pjHeight / 2 * (i + 1))"
                                        fill="none" stroke="#e0dede"></path>
                                </g>

                                <!-- <g :transform="translate(nameWidth, pjHeight / 2 * i, 0)">
                                                        <g :transform="translate(0, 0, 0)">
                                                            <path v-for="(a_item, a_i) in item.l2Data" :key="'corr_out_' + a_i" :d="a_item.d"
                                                                :fill="'none'" :stroke="a_item.fill"></path>
                                                        </g>
                                                        <g>
                    
                                                            <path v-for="(a_item, a_i) in item.l1Data" :key="'corr_out_' + a_i" :d="a_item.d"
                                                                :fill="a_item.fill" :fill-opacity="0.5" :stroke="a_item.fill"></path>
                                                        </g>
                                                        <g>
                                                            <rect v-for="(a_item, a_i) in item.rectData" :key="'corr_out_' + a_i" :x="a_item.x" :y="a_item.y" :height="a_item.h" :width="a_item.w" :fill="a_item.color" :stroke="'white'"></rect>
                                                        </g>
                                                        <g :transform="translate(0, 0, 0)">
                                                            <circle v-for="(a_item, a_i) in item.scatter" :key="'corr_cir_' + a_i"
                                                                :cx="a_item.x" :cy="a_item.y" :r="2" :fill="a_item.fill"></circle>
                                                        </g>
                                                        <g>
                    
                                                            <path
                                                                :d="'M0 ' + (pjHeight / 2 * 0.35) + ' L' + (pjWidth - 20) + ' ' + (pjHeight / 2 * 0.35)"
                                                                fill="none" stroke="#534f4f"></path>
                    
                                                            <path
                                                                :d="'M0 ' + (pjHeight / 2 * 0.65 + 10) + ' L' + (pjWidth - 20) + ' ' + (pjHeight / 2 * 0.65 + 10)"
                                                                fill="none" stroke="#534f4f"></path>
                    
                                                            <path
                                                                :d="'M0 ' + (pjHeight / 2 * 0.95) + ' L' + (pjWidth - 20) + ' ' + (pjHeight / 2 * 0.95)"
                                                                fill="none" stroke="#534f4f"></path>
                                                            <path :d="'M0 ' + (pjHeight / 2) + ' L' + pjWidth * 2 + ' ' + (pjHeight / 2)"
                                                                fill="none" stroke="#e0dede"></path>
                                                        </g>
                                                    </g> -->
                            </g>
                        </svg>
                    </div>
                    <div ref="timeSpace" id="timeSpace"
                        style="float: right; width: calc(85% - 30px); height: 93%; overflow: auto;" @scroll="sysScroll()">

                        <svg :width="barWidth * allDay" :height="pjHeight * projectNum / 2" v-show="selectGroupTag != -1">

                            <g v-for="(item, i) in timeData" :key="'time_x' + i">
                                <g :transform="translate(0, i * pjHeight / 2, 0)">
                                    <g :transform="translate(0, 0, 0)">
                                        <g :transform="translate(0, 0, 0)">
                                            <path v-for="(a_item, a_i) in item.l2Data" :key="'corr_out_' + a_i"
                                                :d="a_item.d" :fill="'none'" :stroke="a_item.fill"></path>
                                        </g>
                                        <g>

                                            <path v-for="(a_item, a_i) in item.l1Data" :key="'corr_out_' + a_i"
                                                :d="a_item.d" :fill="a_item.fill" :fill-opacity="0.5" :stroke="a_item.fill">
                                            </path>
                                        </g>
                                        <g>
                                            <rect v-for="(a_item, a_i) in item.rectData" :key="'corr_out_' + a_i"
                                                :x="a_item.x" :y="a_item.y" :height="a_item.h" :width="a_item.w"
                                                :fill="a_item.color" :stroke="'white'"></rect>
                                        </g>
                                        <g :transform="translate(0, 0, 0)">
                                            <circle v-for="(a_item, a_i) in item.scatter" :key="'corr_cir_' + a_i"
                                                :cx="a_item.x" :cy="a_item.y" :r="4" :fill="a_item.fill"></circle>
                                        </g>
                                        <g>

                                            <path
                                                :d="'M0 ' + (pjHeight / 2 * 0.35 + 0.7) + ' L' + (barWidth * allDay) + ' ' + (pjHeight / 2 * 0.35 + 0.7)"
                                                fill="none" stroke="#534f4f"></path>

                                            <path
                                                :d="'M0 ' + (pjHeight / 2 * 0.65 + 10) + ' L' + (barWidth * allDay) + ' ' + (pjHeight / 2 * 0.65 + 10)"
                                                fill="none" stroke="#534f4f"></path>

                                            <path
                                                :d="'M0 ' + (pjHeight / 2 * 0.95) + ' L' + (barWidth * allDay) + ' ' + (pjHeight / 2 * 0.95)"
                                                fill="none" stroke="#534f4f"></path>
                                            <path
                                                :d="'M0 ' + (pjHeight / 2) + ' L' + (barWidth * allDay) + ' ' + (pjHeight / 2)"
                                                fill="none" stroke="#e0dede"></path>
                                        </g>
                                    </g>
                                </g>
                            </g>
                        </svg>
                    </div>
                    <div ref="legendSpace" id="legendSpace"
                        style="float: right; width: calc(85% - 30px); height: 6%; overflow: auto; margin-top: 0.5%;">
                        <svg :height="legendHeight" id="xAxisLegend" :width="allDay * barWidth"
                            v-show="selectGroupTag != -1">
                            <!-- <path :d="'M0 38 L ' + (pjWidth * 2 - 0) + ' 38'" fill="none" :stroke="'#534f4f'"></path>
                                                <g v-for="(item, i) in timeAxis" :key="'timeAxis_' + i"
                                                    :transform="translate(0 + i * (pjWidth * 2 - 0) / 23, 38, 0)">
                                                    <path d="M0 0L0 6" fill="none" stroke="#534f4f"></path>
                                                    <text :text-anchor="i == 0 ? 'start' : (i == 23 ? 'end' : 'middle')"
                                                        font-family="sans-serif" font-size="12" fill="#534f4f" dy="-0.3em">{{ item }}</text>
                                                </g> -->
                        </svg>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import { axisBottom, axisLeft } from 'd3-axis';
import { scaleLinear, scaleUtc } from 'd3-scale';
// import time from 'd3-scale/src/time';
import { select, selectAll } from 'd3-selection';
import { arc, area, curveBasis, curveBumpX, curveMonotoneX, line, pie } from 'd3-shape';
import { useDataStore } from '../stores/counter';

import { extent, sum } from 'd3-array';
import { objectToString } from '@vue/shared';

export default {
    name: 'APP',
    props: [],
    data () {
        return {
            mouseoverProjectName: '',
            cvHeight: 0,
            cvWidth: 0,
            ctHeight: 0,
            ctWidth: 0,
            nameWidth: 0,
            pjWidth: 100,
            pjHeight: 0,
            legendHeight: 100,
            sortValue: 'longevity',
            sortOptions: [{ label: 'Longevity', value: 'longevity' }, { label: 'Impact dynamic', value: 'IMP' }, { label: 'Total stakeholders', value: 'sumPeople' }],
            pieLegendData: [90, 135, 135],
            pieLegend: [],
            legendArc: [],
            outLegendArc: [],
            group_colormap: ["#8F5362", "#B1818F", "#DFA57C", "#CCAA66", "#A6C9A6", "#6888A5", "#12507B"],
            legendData: [],
            monthName: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'],
            nftName: ['CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks', 'CryptoPunks'],
            legendTag: 0,
            lineData: [],
            textPlace: [],
            colormap1: ['#b69acb', '#6f319b', '#c9c9c9'],
            colorType: {
                holder: '#c9c9c9',
                seller: '#b69acb',
                buyer: '#6f319b',
            },
            colormap3: ['#2301d1', '#2a57f7', '#4186f9', '#5aaffa', '#79d2fc', '#f4d58d', '#fc7b5c', '#fc4443', '#f4313b', '#d52133', '#a30e24'],
            colormap2: ['#56B0FF', '#FF3D3D'],
            correlationData: [],
            axisColor: { 'M1': '#EA7C16', 'M3': '#61bad6', 'IMP': '#d77a78', 'M2': '#53ad92' },
            tableRect: [],
            timeData: [],
            projectNum: 1,
            timeAxis: ['21-1', '21-2', '21-3', '21-4', '21-5', '21-6', '21-7', '21-8', '21-9', '21-10', '21-11', '21-12', '22-1', '22-2', '22-3', '22-4', '22-5', '22-6', '22-7', '22-8', '22-9', '22-10', '22-11', '22-12'],
            timeSelectionText: '',
            max_people: 0,
            max_holder: 0,
            select_circle: {
                x: 0,
                y: 0,
                r: 0,
                stroke: 'none'
            },
            selectGroupTag: -1,
            allDay: 0,
            barWidth: 15,
            pre_select_corr: -1
        }
    },
    methods: {
        translatePos (arr) {
            return `translate(${arr})`;
        },
        mouseoverName (event, name) {
            this.mouseoverProjectName = name;
            select('.tooltipName')
                .style('opacity', 1)
                .style('left', event.layerX + 20 + 'px')
                .style('top', event.layerY - 15 + 'px')
        },
        mouseoutName () {

            select('.tooltipName').style('opacity', 0)
                .style('left', '-1000px')
                .style('top', '0px')

        },
        hoverCorrelation (data) {
            if (this.legendTag == 2) return;
            this.legendTag = 1;
            this.legendData = data;
        },
        outCorrelation () {
            if (this.legendTag != 2)
                this.legendTag = 0;
        },
        clickCorrelation (cnt, projectA, projectB, data) {
            this.legendTag = 2;
            this.legendData = data;
            if (this.pre_select_corr != -1) {
                this.correlationData[this.pre_select_corr].opacity = 0;
            }
            this.correlationData[cnt].opacity = 1;
            this.pre_select_corr = cnt;
            let namespace = {};
            namespace[projectA] = 1;
            namespace[projectB] = 1;
            const dataStore = useDataStore();
            console.log(namespace);
            this.timeData = this.calcIndividualProjectPie(dataStore.allData.data.nft_project_table, dataStore.allData.projectData, dataStore.allData.cpData.data, namespace);
        },
        dateFormat (date) {
            date = new Date(date);
            let monthName = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'];
            return monthName[date.getUTCMonth()] + '.' + ((date.getUTCDate() + 1) >= 10 ? '' : '0') + (date.getUTCDate() + 1) + '.' + date.getUTCFullYear()
        },
        sysScroll () {
            if (this.$refs.timeSpace.scrollTop != this.$refs.nameSpace.scrollTop) {
                this.$refs.nameSpace.scrollTop = this.$refs.timeSpace.scrollTop
            }
            if (this.$refs.timeSpace.scrollLeft != this.$refs.legendSpace.scrollLeft) {
                this.$refs.legendSpace.scrollLeft = this.$refs.timeSpace.scrollLeft;
            }
        },

        // sysScrollL() {
        //     if (this.$refs.timeSpace.scrollTop != this.$refs.nameSpace.scrollTop) {
        //         this.$refs.timeSpace.scrollTop = this.$refs.nameSpace.scrollTop
        //     }
        // },
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
                link: data.link == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data.link,
                img_r: r,
                name: data.name,
                time: data.time,
                timeS: data.timeS,
                timeE: data.timeE,
                IMP: data.outer['IMP'],
                sumPeople: data.inner.holder + data.inner.seller + data.inner.buyer,
            }
        },
        calcIndividualProjectPie (data11, data22, data33, namespaceX) {
            const dataStore = useDataStore();
            let end_time = dataStore.timeRange.end_format;
            // let m1_range = [9999999, -99999999];
            // let m2_range = [9999999, -99999999];
            // let m3_range = [9999999, -99999999];
            let imp_range = [9999999, -99999999];
            // console.log(data11, data22, data33);
            for (let i in data22) {
                // let m11_range = extent(data22[i]['M1Line'], d => d.value);
                // let m22_range = extent(data22[i]['M2Line'], d => d.value);
                // let m33_range = extent(data22[i]['M3Line'], d => d.value);
                let impp_range = extent(data22[i]['IMPLine'], d => d.value);
                // if (!isNaN(m11_range[0]))
                // m1_range[0] = Math.min(m11_range[0], m1_range[0]);
                // if (!isNaN(m22_range[0]))
                // m2_range[0] = Math.min(m22_range[0], m2_range[0]);
                // if (!isNaN(m33_range[0]))
                // m3_range[0] = Math.min(m33_range[0], m3_range[0]);
                if (!isNaN(impp_range[0]))
                    imp_range[0] = Math.min(impp_range[0], imp_range[0]);
                // if (!isNaN(m11_range[1]))
                // m1_range[1] = Math.max(m11_range[1], m1_range[1]);
                // if (!isNaN(m22_range[1]))
                // m2_range[1] = Math.max(m22_range[1], m2_range[1]);
                // if (!isNaN(m33_range[1]))
                // m3_range[1] = Math.max(m33_range[1], m3_range[1]);
                if (!isNaN(impp_range[1]))
                    imp_range[1] = Math.max(impp_range[1], imp_range[1]);
                // console.log(i, data22[i], m11_range, m1_range, m22_range, m2_range, impp_range, imp_range)

            }

            let data1 = new Array();
            let data2 = {};
            let data3 = new Array();
            let select_project_obj = {};
            let max_m1 = 0,
                max_m2 = 0,
                max_m3 = 0,
                max_imp = 0;
            let min_m1 = 99999,
                min_m2 = 99999,
                min_m3 = 99999,
                min_imp = 99999;

            for (let i in data33) {
                max_m1 = Math.max(max_m1, data33[i].M1)
                max_m2 = Math.max(max_m2, data33[i].M2)
                max_m3 = Math.max(max_m3, data33[i].M3)
                max_imp = Math.max(max_imp, data33[i].IMP);
                min_m1 = Math.min(min_m1, data33[i].M1);
                min_m2 = Math.min(min_m2, data33[i].M2);
                min_m3 = Math.min(min_m3, data33[i].M3);
                min_imp = Math.min(min_imp, data33[i].IMP);
            }
            for (let i in data33) {
                if (namespaceX[data33[i]['Project Name']] == 1) {
                    select_project_obj[data33[i]['Project Name']] = 1;
                    data3.push(data33[i]);
                }
            }
            for (let i in data11) {
                if (select_project_obj[data11[i]['Project Name']] == 1) {
                    data1.push(data11[i]);
                }
            }
            for (let i in data22) {
                if (select_project_obj[i] == 1) {
                    data2[i] = data22[i];
                }
            }
            // console.log(data1, data2, data3)


            let margin = {
                left: 0,
                right: 0,
                bottom: -15,
            }
            // console.log(data2[data1[0]['Project Name']]);
            // let selectTimeData = data2[data1[0]['Project Name']]['HolderLine'];
            // let dataStore = useDataStore();
            let timeRange = [new Date(dataStore.timeRange.start_time), new Date(dataStore.timeRange.end_time)];
            // console.log(extent(selectTimeData, d => d.time))
            console.log(timeRange);
            let timeX = scaleUtc()
                .domain(timeRange)
                .range([margin.left, this.barWidth * this.allDay - margin.right]);
            let timeXAxis = (g, x, height) => g
                .attr("transform", `translate(0,${height - margin.bottom})`)
                .attr('font-size', '14px')
                .call(axisBottom(x).ticks(this.barWidth * this.allDay / 80).tickSizeOuter(0))
            selectAll('timeAxis_g').remove();
            select('#xAxisLegend').append('g').attr('id', 'timeAxis_g').attr('font-size', '14px').call(timeXAxis, timeX, 0)
            // console.log(data3);
            let data = [];
            for (let i in data1) {
                let t_data = {};
                t_data = data2[data1[i]['Project Name']];
                // t_data['HolderLine'] = data1[i]['
                data.push(t_data);
            }
            this.projectNum = data.length;
            // console.log(data);
            // let nameSvg = select('#nameSpace').append('svg').attr('id', 'nameSvg').attr('width', this.nameWidth).attr('height', this.pjHeight * data.length / 2);
            // let timeSvg = select('#timeSpace').append('svg').attr('id',  'timeSvg').attr('width', this.pjWidth * 2).attr('height', this.pjHeight * data.length / 2);
            // let legendSvg = select('#legendSpace').append('svg').attr('id', 'legendSvg').attr('width', this.pjWidth * 2).attr('height', this.legendHeight - 15);

            let timeData = [];
            let pro_id_cnt = 0;
            for (let i in data) {
                // console.log(data[i]);
                let m1_range = extent(data[i]['M1Line'], d => d.value);
                let m2_range = extent(data[i]['M2Line'], d => d.value);
                let m3_range = extent(data[i]['M3Line'], d => d.value);
                // let imp_range = extent(data[i]['IMPLine'], d => d.value);
                let holder_range = extent(data[i]['HolderLine'], d => d.value);
                let seller_range = extent(data[i]['SellerLine'], d => d.value);
                let buyer_range = extent(data[i]['BuyerLine'], d => d.value);
                let max_n_range = 0;
                for (let j in data[i]['SellerLine']) {
                    max_n_range = Math.max(max_n_range, data[i]['SellerLine'][j].value + data[i]['BuyerLine'][j].value);
                    // console.log(data[i]['SellerLine'][j].value, data[i]['BuyerLine'][j].value, max_n_range);
                }
                // let min_n_range = Math.min(holder_range[0], seller_range[0], buyer_range[0]);
                let min_n_range = 0;
                let rxScale = scaleLinear([0, data[i]['M1Line'].length], [margin.left, this.pjWidth - margin.right]);
                let xScale = scaleLinear([0, data[i]['M1Line'].length - 1], [margin.left, this.pjWidth - margin.right]);
                let areaScale = scaleLinear([min_n_range, max_n_range], [this.pjHeight * 0.35 / 2, 10]);
                let areaScale2 = scaleLinear([0, holder_range[1]], [this.pjHeight * .65 / 2 + 10, this.pjHeight * 0.35 / 2 + 10]);
                let lineScale = scaleLinear([0, 1], [this.pjHeight * 0.95 / 2, this.pjHeight * 0.65 / 2 + 20]);
                let areaGenerate = area().x(d => timeX(new Date(d.x))).y1(d => areaScale(d.y)).y0(areaScale(0)).curve(curveMonotoneX);
                let areaGenerate2 = area().x(d => timeX(new Date(d.x))).y1(d => areaScale2(d.y)).y0(areaScale2(0)).curve(curveMonotoneX);
                selectAll('#vAxis' + pro_id_cnt).remove();
                select('#nameSpaceSvg').append('g').attr('id', 'vAxis' + pro_id_cnt).call(axisLeft(lineScale).ticks(3)).attr('transform', `translate(${this.nameWidth - 1}, ${this.pjHeight / 2 * i})`);
                select('#nameSpaceSvg').append('g').attr('id', 'vAxis' + pro_id_cnt).call(axisLeft(areaScale).ticks(3)).attr('transform', `translate(${this.nameWidth - 1}, ${this.pjHeight / 2 * i})`);
                select('#nameSpaceSvg').append('g').attr('id', 'vAxis' + pro_id_cnt).call(axisLeft(areaScale2).ticks(3)).attr('transform', `translate(${this.nameWidth - 1}, ${this.pjHeight / 2 * i})`);
                pro_id_cnt++;
                let lineGenerate = line().x(d => timeX(new Date(d.x))).y(d => lineScale(d.y)).curve(curveMonotoneX);
                // console.log(data[i])
                // console.log(min_m1, max_m1, data[i].M1, (data[i]['M1'] - min_m1) / (max_m1 - min_m1))
                let nameData = this.calcIndividual({
                    inner: {
                        holder: data[i]['Holder'],
                        buyer: data[i]['Buyer'],
                        seller: data[i]['Seller']
                    },
                    outer: {
                        M1: (data[i]['M1'] - min_m1) / (max_m1 - min_m1),
                        M2: (data[i]['M2'] - min_m2) / (max_m2 - min_m2),
                        M3: (data[i]['M3'] - min_m3) / (max_m3 - min_m3),
                        IMP: (data[i]['IMP'] - min_imp) / (max_imp - min_imp)
                    },

                    link: data[i]['Project Name'] == "Moonbirds" ? 'https://i.seadn.io/gae/H-eyNE1MwL5ohL-tCfn_Xa1Sl9M9B4612tLYeUlQubzt4ewhr4huJIR5OLuyO3Z5PpJFSwdm7rq-TikAh7f5eUw338A2cy6HRH75?auto=format&w=256' : data[i]['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data[i]['logo_link'],
                    // link: data[i]['logo_link'],
                    name: data[i]['Project Name'],
                    timeS: this.dateFormat(data[i]['create_time']),
                    timeM: '-',
                    timeE: (data[i]['cease_time'] == "" ? end_time : this.dateFormat(data[i]['cease_time']))
                }, (this.nameWidth * 0.8 - 20) / 2, 0, 0);
                let lineData1 = [];
                let lineData2 = [];
                let scatter = [];
                // console.log(data[i]);
                let rectData = [];

                for (let j in data[i]['SellerLine']) {
                    // max_n_range = Math.max(max_n_range, data[i]['SellerLine'][j].value + data[i]['BuyerLine'][j].value);
                    // console.log(data[i]['SellerLine'][j].value, data[i]['BuyerLine'][j].value, max_n_range, i);
                    // console.log(data[i]['BuyerLine'][j].time)
                    rectData.push({
                        x: timeX(new Date(data[i]['BuyerLine'][j].time)),
                        w: this.barWidth,
                        y: areaScale(data[i]['BuyerLine'][j].value),
                        h: -areaScale(data[i]['BuyerLine'][j].value) + areaScale(0),
                        color: this.colorType['buyer']
                    });
                    rectData.push({
                        x: timeX(new Date(data[i]['SellerLine'][j].time)),
                        w: this.barWidth,
                        y: areaScale(data[i]['BuyerLine'][j].value + data[i]['SellerLine'][j].value),
                        h: -areaScale(data[i]['SellerLine'][j].value) + areaScale(0),
                        color: this.colorType['seller']
                    });

                }

                for (let k in this.colorType) {
                    let tLineData = [];
                    let sel_name = '';
                    if (k != 'holder')
                        continue;
                    if (k == 'holder')
                        sel_name = 'HolderLine';
                    else if (k == 'buyer')
                        sel_name = 'BuyerLine';
                    else if (k == 'seller')
                        sel_name = 'SellerLine';
                    for (let j = 0; j < data[i][sel_name].length; ++j) {
                        // console.log(data[i][sel_name]);
                        tLineData.push({ x: data[i][sel_name][j].time, y: data[i][sel_name][j].value });
                    }
                    console.log(tLineData);
                    lineData1.push({
                        d: k == 'holder' ? areaGenerate2(tLineData) : areaGenerate(tLineData),
                        fill: this.colorType[k],
                        type: k
                    })
                }
                for (let k in this.axisColor) {
                    let tLineData = [];
                    let sData = []
                    for (let j = 0; j < data[i][k + 'Line'].length; ++j) {
                        let x = data[i][k + 'Line'][j].time;
                        let y = data[i][k + 'Line'][j].value;
                        if (k == 'M1') {
                            y = (y - m1_range[0]) / (m1_range[1] - m1_range[0]);
                        } else if (k == 'M2') {
                            y = (y - m2_range[0]) / (m2_range[1] - m2_range[0]);
                        } else if (k == 'M3') {
                            y = (y - m3_range[0]) / (m3_range[1] - m3_range[0]);
                        } else if (k == 'IMP') {
                            y = (y - imp_range[0]) / (imp_range[1] - imp_range[0]);
                        }
                        tLineData.push({ x: x, y: y });
                        sData.push({ x: timeX(new Date(x)), y: lineScale(y), rx: x, ry: y, fill: this.axisColor[k] });
                    }
                    if (k != 'IMP')
                        lineData2.push({
                            d: lineGenerate(tLineData),
                            fill: this.axisColor[k],
                            type: k
                        })
                    if (k == 'IMP') {
                        scatter = sData;
                        // console.log(scatter);
                    }
                }
                // console.log(data[i])
                timeData.push({
                    name: nameData,
                    rectData: rectData,
                    l1Data: lineData1,
                    l2Data: lineData2,
                    scatter: scatter,
                    IMP: nameData['IMP'],
                    sumPeople: nameData['sumPeople'],
                    longevity: new Date(data[i]['create_time'])
                });
            }
            timeData.sort((a, b) => a.longevity - b.longevity);
            return timeData;

        },
        calcIndividualProject (data11, data22, data33, groupNum) {
            const dataStore = useDataStore();
            let end_time = dataStore.timeRange.end_format;
            // let m1_range = [9999999, -99999999];
            // let m2_range = [9999999, -99999999];
            // let m3_range = [9999999, -99999999];
            let imp_range = [9999999, -99999999];
            // console.log(data11, data22, data33);
            for (let i in data22) {
                // let m11_range = extent(data22[i]['M1Line'], d => d.value);
                // let m22_range = extent(data22[i]['M2Line'], d => d.value);
                // let m33_range = extent(data22[i]['M3Line'], d => d.value);
                let impp_range = extent(data22[i]['IMPLine'], d => d.value);
                // if (!isNaN(m11_range[0]))
                // m1_range[0] = Math.min(m11_range[0], m1_range[0]);
                // if (!isNaN(m22_range[0]))
                // m2_range[0] = Math.min(m22_range[0], m2_range[0]);
                // if (!isNaN(m33_range[0]))
                // m3_range[0] = Math.min(m33_range[0], m3_range[0]);
                if (!isNaN(impp_range[0]))
                    imp_range[0] = Math.min(impp_range[0], imp_range[0]);
                // if (!isNaN(m11_range[1]))
                // m1_range[1] = Math.max(m11_range[1], m1_range[1]);
                // if (!isNaN(m22_range[1]))
                // m2_range[1] = Math.max(m22_range[1], m2_range[1]);
                // if (!isNaN(m33_range[1]))
                // m3_range[1] = Math.max(m33_range[1], m3_range[1]);
                if (!isNaN(impp_range[1]))
                    imp_range[1] = Math.max(impp_range[1], imp_range[1]);
                // console.log(i, data22[i], m11_range, m1_range, m22_range, m2_range, impp_range, imp_range)

            }


            let data1 = new Array();
            let data2 = {};
            let data3 = new Array();
            let select_project_obj = {};
            let max_m1 = 0,
                max_m2 = 0,
                max_m3 = 0,
                max_imp = 0;
            let min_m1 = 99999,
                min_m2 = 99999,
                min_m3 = 99999,
                min_imp = 99999;

            for (let i in data33) {
                max_m1 = Math.max(max_m1, data33[i].M1)
                max_m2 = Math.max(max_m2, data33[i].M2)
                max_m3 = Math.max(max_m3, data33[i].M3)
                max_imp = Math.max(max_imp, data33[i].IMP);
                min_m1 = Math.min(min_m1, data33[i].M1);
                min_m2 = Math.min(min_m2, data33[i].M2);
                min_m3 = Math.min(min_m3, data33[i].M3);
                min_imp = Math.min(min_imp, data33[i].IMP);
            }
            for (let i in data33) {
                if (data33[i]['Group'] == groupNum) {
                    select_project_obj[data33[i]['Project Name']] = 1;
                    data3.push(data33[i]);
                }
            }
            for (let i in data11) {
                if (select_project_obj[data11[i]['Project Name']] == 1) {
                    data1.push(data11[i]);
                }
            }
            for (let i in data22) {
                if (select_project_obj[i] == 1) {
                    data2[i] = data22[i];
                }
            }
            // console.log(data1, data2, data3)


            let margin = {
                left: 0,
                right: 0,
                bottom: -15,
            }
            // console.log(data2[data1[0]['Project Name']]);
            // let selectTimeData = data2[data1[0]['Project Name']]['HolderLine'];
            // let dataStore = useDataStore();
            let timeRange = [new Date(dataStore.timeRange.start_time), new Date(dataStore.timeRange.end_time)];
            // console.log(extent(selectTimeData, d => d.time))
            // console.log(timeRange);
            let timeX = scaleUtc()
                .domain(timeRange)
                .range([margin.left, this.barWidth * this.allDay - margin.right]);
            let timeXAxis = (g, x, height) => g
                .attr("transform", `translate(0,${height - margin.bottom})`)
                .attr('font-size', '14px')
                .call(axisBottom(x).ticks(this.barWidth * this.allDay / 80).tickSizeOuter(0))
            selectAll('timeAxis_g').remove();
            select('#xAxisLegend').append('g').attr('id', 'timeAxis_g').attr('font-size', '14px').call(timeXAxis, timeX, 0)
            // console.log(data3);
            let data = [];
            for (let i in data1) {
                let t_data = {};
                t_data = data2[data1[i]['Project Name']];
                // t_data['HolderLine'] = data1[i]['
                data.push(t_data);
            }
            this.projectNum = data.length;
            // console.log(data);
            // let nameSvg = select('#nameSpace').append('svg').attr('id', 'nameSvg').attr('width', this.nameWidth).attr('height', this.pjHeight * data.length / 2);
            // let timeSvg = select('#timeSpace').append('svg').attr('id',  'timeSvg').attr('width', this.pjWidth * 2).attr('height', this.pjHeight * data.length / 2);
            // let legendSvg = select('#legendSpace').append('svg').attr('id', 'legendSvg').attr('width', this.pjWidth * 2).attr('height', this.legendHeight - 15);

            let timeData = [];
            let pro_id_cnt = 0;
            for (let i in data) {
                // // console.log(data[i]);
                let m1_range = extent(data[i]['M1Line'], d => d.value);
                let m2_range = extent(data[i]['M2Line'], d => d.value);
                let m3_range = extent(data[i]['M3Line'], d => d.value);
                // let imp_range = extent(data[i]['IMPLine'], d => d.value);
                let holder_range = extent(data[i]['HolderLine'], d => d.value);
                let seller_range = extent(data[i]['SellerLine'], d => d.value);
                let buyer_range = extent(data[i]['BuyerLine'], d => d.value);
                let max_n_range = 0;
                for (let j in data[i]['SellerLine']) {
                    max_n_range = Math.max(max_n_range, data[i]['SellerLine'][j].value + data[i]['BuyerLine'][j].value);
                    // console.log(data[i]['SellerLine'][j].value, data[i]['BuyerLine'][j].value, max_n_range);
                }
                // let min_n_range = Math.min(holder_range[0], seller_range[0], buyer_range[0]);
                let min_n_range = 0;
                let rxScale = scaleLinear([0, data[i]['M1Line'].length], [margin.left, this.pjWidth - margin.right]);
                let xScale = scaleLinear([0, data[i]['M1Line'].length - 1], [margin.left, this.pjWidth - margin.right]);
                let areaScale = scaleLinear([min_n_range, max_n_range], [this.pjHeight * 0.35 / 2, 10]);
                let areaScale2 = scaleLinear([0, holder_range[1]], [this.pjHeight * .65 / 2 + 10, this.pjHeight * 0.35 / 2 + 10]);
                let lineScale = scaleLinear([0, 1], [this.pjHeight * 0.95 / 2, this.pjHeight * 0.65 / 2 + 20]);
                let areaGenerate = area().x(d => timeX(new Date(d.x))).y1(d => areaScale(d.y)).y0(areaScale(0)).curve(curveMonotoneX);
                let areaGenerate2 = area().x(d => timeX(new Date(d.x))).y1(d => areaScale2(d.y)).y0(areaScale2(0)).curve(curveMonotoneX);
                selectAll('#vAxis' + pro_id_cnt).remove();
                select('#nameSpaceSvg').append('g').attr('id', 'vAxis' + pro_id_cnt).call(axisLeft(lineScale).ticks(3)).attr('transform', `translate(${this.nameWidth - 1}, ${this.pjHeight / 2 * i})`);
                select('#nameSpaceSvg').append('g').attr('id', 'vAxis' + pro_id_cnt).call(axisLeft(areaScale).ticks(3)).attr('transform', `translate(${this.nameWidth - 1}, ${this.pjHeight / 2 * i})`);
                select('#nameSpaceSvg').append('g').attr('id', 'vAxis' + pro_id_cnt).call(axisLeft(areaScale2).ticks(3)).attr('transform', `translate(${this.nameWidth - 1}, ${this.pjHeight / 2 * i})`);
                pro_id_cnt++;
                let lineGenerate = line().x(d => timeX(new Date(d.x))).y(d => lineScale(d.y)).curve(curveMonotoneX);
                // console.log(data[i])
                // console.log(min_m1, max_m1, data[i].M1, (data[i]['M1'] - min_m1) / (max_m1 - min_m1))
                let nameData = this.calcIndividual({
                    inner: {
                        holder: data[i]['Holder'],
                        buyer: data[i]['Buyer'],
                        seller: data[i]['Seller']
                    },
                    outer: {
                        M1: (data[i]['M1'] - min_m1) / (max_m1 - min_m1),
                        M2: (data[i]['M2'] - min_m2) / (max_m2 - min_m2),
                        M3: (data[i]['M3'] - min_m3) / (max_m3 - min_m3),
                        IMP: (data[i]['IMP'] - min_imp) / (max_imp - min_imp)
                    },

                    link: data[i]['Project Name'] == "Moonbirds" ? 'https://i.seadn.io/gae/H-eyNE1MwL5ohL-tCfn_Xa1Sl9M9B4612tLYeUlQubzt4ewhr4huJIR5OLuyO3Z5PpJFSwdm7rq-TikAh7f5eUw338A2cy6HRH75?auto=format&w=256' : data[i]['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data[i]['logo_link'],
                    // link: data[i]['logo_link'],
                    name: data[i]['Project Name'],
                    timeS: this.dateFormat(data[i]['create_time']),
                    timeM: '-',
                    timeE: (data[i]['cease_time'] == "" ? end_time : this.dateFormat(data[i]['cease_time']))
                }, (this.nameWidth * 0.8 - 20) / 2, 0, 0);
                let lineData1 = [];
                let lineData2 = [];
                let scatter = [];
                // console.log(data[i]);
                let rectData = [];

                for (let j in data[i]['SellerLine']) {
                    // max_n_range = Math.max(max_n_range, data[i]['SellerLine'][j].value + data[i]['BuyerLine'][j].value);
                    // console.log(data[i]['SellerLine'][j].value, data[i]['BuyerLine'][j].value, max_n_range, i);
                    // console.log(data[i]['BuyerLine'][j].time)
                    rectData.push({
                        x: timeX(new Date(data[i]['BuyerLine'][j].time)),
                        w: this.barWidth,
                        y: areaScale(data[i]['BuyerLine'][j].value),
                        h: -areaScale(data[i]['BuyerLine'][j].value) + areaScale(0),
                        color: this.colorType['buyer']
                    });
                    rectData.push({
                        x: timeX(new Date(data[i]['SellerLine'][j].time)),
                        w: this.barWidth,
                        y: areaScale(data[i]['BuyerLine'][j].value + data[i]['SellerLine'][j].value),
                        h: -areaScale(data[i]['SellerLine'][j].value) + areaScale(0),
                        color: this.colorType['seller']
                    });

                }

                for (let k in this.colorType) {
                    let tLineData = [];
                    let sel_name = '';
                    if (k != 'holder')
                        continue;
                    if (k == 'holder')
                        sel_name = 'HolderLine';
                    else if (k == 'buyer')
                        sel_name = 'BuyerLine';
                    else if (k == 'seller')
                        sel_name = 'SellerLine';
                    for (let j = 0; j < data[i][sel_name].length; ++j) {
                        // console.log(data[i][sel_name]);
                        tLineData.push({ x: data[i][sel_name][j].time, y: data[i][sel_name][j].value });
                    }
                    // console.log(tLineData);
                    lineData1.push({
                        d: k == 'holder' ? areaGenerate2(tLineData) : areaGenerate(tLineData),
                        fill: this.colorType[k],
                        type: k
                    })
                }
                for (let k in this.axisColor) {
                    let tLineData = [];
                    let sData = []
                    for (let j = 0; j < data[i][k + 'Line'].length; ++j) {
                        let x = data[i][k + 'Line'][j].time;
                        let y = data[i][k + 'Line'][j].value;
                        if (k == 'M1') {
                            y = (y - m1_range[0]) / (m1_range[1] - m1_range[0]);
                        } else if (k == 'M2') {
                            y = (y - m2_range[0]) / (m2_range[1] - m2_range[0]);
                        } else if (k == 'M3') {
                            y = (y - m3_range[0]) / (m3_range[1] - m3_range[0]);
                        } else if (k == 'IMP') {
                            y = (y - imp_range[0]) / (imp_range[1] - imp_range[0]);
                        }
                        tLineData.push({ x: x, y: y });
                        sData.push({ x: timeX(new Date(x)), y: lineScale(y), rx: x, ry: y, fill: this.axisColor[k] });
                    }
                    if (k != 'IMP')
                        lineData2.push({
                            d: lineGenerate(tLineData),
                            fill: this.axisColor[k],
                            type: k
                        })
                    if (k == 'IMP') {
                        scatter = sData;
                        // console.log(scatter);
                    }
                }
                // console.log(data[i])
                timeData.push({
                    name: nameData,
                    rectData: rectData,
                    l1Data: lineData1,
                    l2Data: lineData2,
                    scatter: scatter,
                    IMP: nameData['IMP'],
                    sumPeople: nameData['sumPeople'],
                    longevity: new Date(data[i]['create_time'])
                });
            }
            timeData.sort((a, b) => a.longevity - b.longevity);
            return timeData;

        },
        calcCorrelation (data, r, x, y, rectScale, holderScale, y1, y2, HighlightPath, r_color) {
            console.log(data)
            let tmpData = [];
            let innerSum = 0;
            let colorScale = scaleLinear([-1, 1], [0, 10]);
            for (let i in data.inner) {
                let outerName = i == 'holder' ? 'c1' : (i == 'buyer' ? 'c2' : 'c3');
                // innerSum += data.inner[i];
                innerSum = Math.max(data.inner[i], innerSum);
                tmpData.push({
                    type: i,
                    value: 1,
                    inner: data.inner[i],
                    raw: data.raw[i],
                    corr: data.outer[outerName]
                });
            }
            let pieData = pie().sort(null).value(d => d.value)(tmpData);
            let innerArc = [];
            for (let i in pieData) {
                innerArc.push({
                    data: pieData[i].data,
                    d: arc().innerRadius(0).outerRadius(r / 2 * (pieData[i].data.inner / innerSum))(pieData[i]),
                    dOut: arc().innerRadius(r / 2).outerRadius(r / 2 + r / 2 * parseFloat(Math.abs(pieData[i].data.corr)))(pieData[i]),
                    dLegend: arc().innerRadius(0).outerRadius(this.cvHeight * 0.15 / 2 * (pieData[i].data.inner / innerSum))(pieData[i]),
                    dLegendOut: arc().innerRadius(this.cvHeight * 0.15 / 2).outerRadius(this.cvHeight * 0.15 / 2 + this.cvHeight * 0.15 / 2 * parseFloat(Math.abs(pieData[i].data.corr)))(pieData[i]),
                    textTrans: (arc().innerRadius(0).outerRadius(this.cvHeight * 0.15 - 20)).centroid(pieData[i]),
                    fill: this.colorType[pieData[i].data.type],
                    fill2: this.colormap3[(colorScale(pieData[i].data.corr)).toFixed(0)],
                    text: pieData[i].data.raw
                })
                // console.log((arc().innerRadius(0).outerRadius(this.cvHeight * 0.15 - 20)).centroid(pieData[i]), pieData[i])
            }
            let outArc = [];
            let angle = 45;
            // console.log(data);
            let cnt = 0;
            for (let i in data.outer) {
                outArc.push({
                    d: arc().innerRadius(r - 2).outerRadius(r).cornerRadius(5)({
                        startAngle: ((cnt * 120) - data.outer[i] * 120 / 2) * Math.PI / 180,
                        endAngle: ((cnt * 120) + data.outer[i] * 120 / 2) * Math.PI / 180,
                        index: cnt,
                        padAngle: 0,
                        value: 1
                    }),
                    dLegend: arc().innerRadius(this.cvWidth * 0.15 - 5).outerRadius(this.cvWidth * 0.15).cornerRadius(5)({
                        startAngle: ((cnt * 120) - data.outer[i] * 120 / 2) * Math.PI / 180,
                        endAngle: ((cnt * 120) + data.outer[i] * 120 / 2) * Math.PI / 180,
                        index: cnt,
                        padAngle: 0,
                        value: 1
                    }),
                    fill: ((data.outer[i] * 10).toFixed(0) / 10).toFixed(1) > 0 ? this.colormap2[1] : ((data.outer[i] * 10).toFixed(0) / 10).toFixed(1) == 0 ? 'white' : this.colormap2[0],
                    type: i,
                    type_name: i == 'c1' ? 'Holder' : i == 'c2' ? 'Buyer' : 'Seller',
                    text: ((data.outer[i] * 10).toFixed(0) / 10).toFixed(1)
                });
                cnt++;
            }
            let rectData = [];
            rectData.push({
                x: 0,
                stroke: outArc[2].fill,
                rw: rectScale(data.raw.seller),
                y: y1 - 12.5,
                h: 25,
                text: ((data.label.p_1.seller * 100).toFixed(2)).toString() + '%'
            })
            rectData.push({
                x: this.ctWidth / 3,
                stroke: outArc[1].fill,
                rw: rectScale(data.raw.buyer),
                y: y1 - 12.5,
                h: 25,
                text: ((data.label.p_1.buyer * 100).toFixed(2)).toString() + '%'
            })
            rectData.push({
                x: this.ctWidth * 2 / 3,
                stroke: outArc[0].fill,
                rw: holderScale(data.raw.holder),
                y: y2 - 12.5,
                h: 25,
                text: ((data.label.p_1.holder * 100).toFixed(2)).toString() + '%'
            })
            rectData.push({
                x: 0,
                stroke: outArc[2].fill,
                rw: rectScale(data.raw.seller),
                y: y2 - 12.5,
                h: 25,
                text: ((data.label.p_2.seller * 100).toFixed(2)).toString() + '%'
            })
            rectData.push({
                x: this.ctWidth / 3,
                stroke: outArc[1].fill,
                rw: rectScale(data.raw.buyer),
                y: y2 - 12.5,
                h: 25,
                text: ((data.label.p_2.buyer * 100).toFixed(2)).toString() + '%'
            })
            rectData.push({
                x: this.ctWidth * 2 / 3,
                stroke: outArc[0].fill,
                rw: holderScale(data.raw.holder),
                y: y1 - 12.5,
                h: 25,
                text: ((data.label.p_2.holder * 100).toFixed(2)).toString() + '%'
            })
            return {
                x: x,
                y: y,
                outArc: outArc,
                innerArc: innerArc,
                lineData: rectData,
                circleData: {
                    x: x,
                    y: y,
                    r: r + 3,
                    stroke: r_color
                },
                opacity: 0,
                projectA: data.projectA,
                projectB: data.projectB,
                HighlightPath: HighlightPath
            }
        },
        calcLine (table_data, correlation_data, project_data, group_num) {
            const dataStore = useDataStore();
            this.timeSelectionText = dataStore.timeRange.start_format + '-' + dataStore.timeRange.end_format;
            let data = [];
            // console.log(logo_link_set);
            let logo_link_set = {};
            for (let i in project_data) {
                if (project_data[i]['Group'] == group_num) {
                    logo_link_set[project_data[i]['Project Name']] = project_data[i]['logo_link'];
                }
            }
            // console.log(logo_link_set);
            for (let i in table_data) {
                if (typeof (logo_link_set[table_data[i]['Project Name']]) != 'undefined') {
                    data.push(table_data[i]);
                }
            }
            let lineScaleY = scaleLinear([-1, data.length], [this.cvHeight - 10 - (this.cvWidth - 3 - 0), this.cvHeight - 10]);
            let lineScaleX = scaleLinear([-1, data.length], [0, this.cvWidth - 3]);
            let lineData = [];
            let textPlace = [];
            const lineGenerate = line()
                .x(d => lineScaleX(d[0]))
                .y(d => lineScaleY(d[1]));
            let max_people = 0;
            let max_holder = 0;
            let max_sum_people = 0;
            let min_holder = 100000000000000;
            for (let i = 0; i < data.length; ++i) {
                let seller = sum(data[i].Seller, d => d.value);
                let holder = (data[i].Holder[data[i].Holder.length - 1].value);
                let buyer = sum(data[i].Buyer, d => d.value);
                max_people = Math.max(max_people, seller, buyer);
                // min_sum_people = Math.min(min_sum_people, seller, buyer);
                max_holder = Math.max(max_holder, holder);
                min_holder = Math.min(min_holder, holder);
                // console.log(seller, holder, buyer);
                let sum_people = seller + holder + buyer;
                max_sum_people = Math.max(max_sum_people, sum_people);
                data[i].sum_people = sum_people;
            }
            data.sort((a, b) => b.sum_people - a.sum_people);
            // console.log(data);
            // console.log(max_sum_people, max_people);
            // console.log(min_holder, max_holder);
            this.max_holder = max_holder;
            this.max_people = max_people;
            let rectScale = scaleLinear([0, max_people], [0, this.ctWidth / 3 - 0]);
            let holderScale = scaleLinear([0, max_holder], [0, this.ctWidth / 3 - 0]);
            let projectPosition = {};
            for (let i = -1; i < data.length + 1; i++) {

                if (i < data.length && i > -1) {
                    data[i]['logo_link'] = logo_link_set[data[i]['Project Name']];
                    // console.log(data[i]['Project Name'], data[i]['logo_link']);
                    let cnt_len = 0;
                    let tableRect = []
                    let typeName = ['Seller', 'Buyer', 'Holder'];
                    // console.log(data[i]);
                    for (let j in typeName) {
                        // console.log(sum(data[i][typeName[j]], d => d.value));
                        let rw = 0;
                        if (j != 2)
                            rw = rectScale(sum(data[i][typeName[j]], d => d.value));
                        else rw = holderScale((data[i][typeName[j]][data[i][typeName[j]].length - 1].value));
                        tableRect.push({
                            x: cnt_len,
                            w: rw,
                            h: 25,
                            y: lineScaleY(i) - 12.5,
                            fill: this.colormap1[j]
                        })
                        cnt_len += this.ctWidth / 3;
                    }
                    //  console.log(tableRect);
                    projectPosition[data[i]['Project Name']] = {
                        pos: [lineScaleX(data.length - 1 - i), lineScaleY(i)],
                        value: {
                            seller: sum(data[i]['Seller'], d => d.value),
                            buyer: sum(data[i]['Buyer'], d => d.value),
                            holder: data[i].Holder[data[i].Holder.length - 1].value
                        }
                    }
                    textPlace.push({
                        rectData: tableRect,
                        name: data[i]['Project Name'],
                        link: data[i]['Project Name'] == "Moonbirds" ? 'https://i.seadn.io/gae/H-eyNE1MwL5ohL-tCfn_Xa1Sl9M9B4612tLYeUlQubzt4ewhr4huJIR5OLuyO3Z5PpJFSwdm7rq-TikAh7f5eUw338A2cy6HRH75?auto=format&w=256' : data[i]['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data[i]['logo_link'],
                        pos: [lineScaleX(data.length - 1 - i), lineScaleY(i)]
                    });
                }
                lineData.push(lineGenerate([
                    [i, data.length - 1 - i],
                    [i, data.length]
                ]));
                lineData.push(lineGenerate([
                    [data.length - i - 1, i],
                    [data.length, i]
                ]));
            }
            // console.log(projectPosition);
            let repeat_data = {};
            let max_co_people = 0;
            let min_co_people = 1000000000000;
            let co_data = [];

            for (let i in correlation_data) {
                if (typeof (logo_link_set[correlation_data[i]['Project Name B']]) == 'undefined' || typeof (correlation_data[i]['Project Name A']) == 'undefined') {
                    continue;
                }
                if ((repeat_data[correlation_data[i]['Project Name B'] + correlation_data[i]['Project Name A']]) == 1 ||
                    repeat_data[correlation_data[i]['Project Name A'] + correlation_data[i]['Project Name B']] == 1) {
                    continue;
                }

                repeat_data[correlation_data[i]['Project Name A'] + correlation_data[i]['Project Name B']] = 1;
                let sum_people = correlation_data[i].co_buyer_raw + correlation_data[i].co_holder_raw + correlation_data[i].co_seller_raw;
                max_co_people = Math.max(max_co_people, sum_people);
                min_co_people = Math.min(min_co_people, sum_people);
                correlation_data[i].co_sum = sum_people;
                co_data.push(correlation_data[i]);
            }
            let sizeScale = scaleLinear([min_co_people, max_co_people], [0.5, 0.9]);
            // console.log(co_data);
            let legend_data = null;
            let legend_tag = 0;
            if (0.9 * (lineScaleX(1) - lineScaleX(0)) / 2 > 25) {
                legend_tag = 1
            }
            let corr_res_data = [];
            for (let i = 0; i < co_data.length; i++) {
                // for (let j = co_data.length - i; j < co_data.length; j++) {
                // if (Math.random() > 0.8) {
                // let HighlightPath = ['M'];
                let project = [co_data[i]['Project Name A'], co_data[i]['Project Name B']];
                let x = projectPosition[co_data[i]['Project Name A']].pos[0];
                let y = projectPosition[co_data[i]['Project Name B']].pos[1];
                let y1 = y;
                let y2 = projectPosition[co_data[i]['Project Name A']].pos[1];

                if (projectPosition[co_data[i]['Project Name B']].pos[0] > x) {
                    x = projectPosition[co_data[i]['Project Name B']].pos[0];
                    y = projectPosition[co_data[i]['Project Name A']].pos[1];
                    y1 = y;
                    y2 = projectPosition[co_data[i]['Project Name B']].pos[1];
                    project = [co_data[i]['Project Name B'], co_data[i]['Project Name A']];
                }

                let HighlightPath = 'M' + projectPosition[co_data[i]['Project Name A']].pos[0] + ',' + projectPosition[co_data[i]['Project Name A']].pos[1] + 'L' + x + ',' + y + 'L' + projectPosition[co_data[i]['Project Name B']].pos[0] + ',' + projectPosition[co_data[i]['Project Name B']].pos[1];
                corr_res_data.push(this.calcCorrelation({
                    project: project,
                    projectA: co_data[i]['Project Name A'],
                    projectB: co_data[i]['Project Name B'],
                    raw: {
                        holder: co_data[i].co_holder_raw,
                        buyer: co_data[i].co_buyer_raw,
                        seller: co_data[i].co_seller_raw
                    },
                    inner: {
                        holder: co_data[i].co_holder_raw / co_data[i].co_sum,
                        buyer: co_data[i].co_buyer_raw / co_data[i].co_sum,
                        seller: co_data[i].co_seller_raw / co_data[i].co_sum
                    },
                    outer: {
                        c1: co_data[i].holder_correlation,
                        c2: co_data[i].buyer_correlation,
                        c3: co_data[i].seller_correlation
                    },
                    label: {
                        p_1: {
                            seller: projectPosition[project[1]].value.seller == 0 ? 0 : co_data[i].co_seller_raw / projectPosition[project[1]].value.seller,
                            buyer: projectPosition[project[1]].value.buyer == 0 ? 0 : co_data[i].co_buyer_raw / projectPosition[project[1]].value.buyer,
                            holder: projectPosition[project[1]].value.holder == 0 ? 0 : co_data[i].co_holder_raw / projectPosition[project[1]].value.holder,
                        },
                        p_2: {
                            seller: projectPosition[project[0]].value.seller == 0 ? 0 : co_data[i].co_seller_raw / projectPosition[project[0]].value.seller,
                            buyer: projectPosition[project[0]].value.buyer == 0 ? 0 : co_data[i].co_buyer_raw / projectPosition[project[0]].value.buyer,
                            holder: projectPosition[project[0]].value.holder == 0 ? 0 : co_data[i].co_holder_raw / projectPosition[project[0]].value.holder,
                        }
                    }
                }, sizeScale(co_data[i].co_sum) * (lineScaleX(1) - lineScaleX(0)) / 2, x, y, rectScale, holderScale, y1, y2, HighlightPath, this.group_colormap[group_num]))
                // }
                // }
                // break;
            }
            this.correlationData = corr_res_data;
            // console.log(this.correlationData);
            // this.legendData = corr_res_data[0];
            // console.log(this.legendData);
            // console.log(this.correlationData, this.legendData);
            // console.log(lineData);
            // console.log(textPlace)
            return [lineData, textPlace];

        },
        getDay () {
            const dataStore = useDataStore();
            let start_day = new Date(dataStore.timeRange.start_time);
            let end_day = new Date(dataStore.timeRange.end_time);
            let day = (end_day - start_day) / (1000 * 60 * 60 * 24);
            let margin = {
                left: 0,
                right: 0,
                bottom: -15,
            }
            let barWidth = 15
            if (day * 15 < this.pjWidth - margin.left - margin.right) {
                barWidth = (this.pjWidth - margin.left - margin.right) / day;
            }
            return [day, barWidth];
        }
    },
    created () { },

    watch: {
        selectGroupTag: {
            handler: function (newVal, oldVal) {
                if (newVal == -1) {
                    this.legendTag = 0;
                }
            },
            deep: true
        },
        sortValue: {
            handler: function (newVal, oldVal) {
                if (newVal == 'longevity') {
                    this.timeData.sort((a, b) => a.longevity - b.longevity);
                } else {
                    this.timeData.sort((a, b) => b[newVal] - a[newVal]);
                }
            },
            deep: true
        },
    },
    mounted () {
        this.cvHeight = this.$refs.correlationView.offsetHeight;
        this.cvWidth = this.$refs.correlationView.offsetWidth;
        this.ctHeight = this.$refs.correlationTable.offsetHeight;
        this.ctWidth = this.$refs.correlationTable.offsetWidth;
        // this.pjHeight = this.$refs.nameSpace.offsetHeight;
        // this.pjWidth = this.$refs.nameSpace.offsetWidth * .85 - 20;
        this.legendHeight = this.$refs.legendSpace.offsetHeight;
        this.nameWidth = this.$refs.nameSpace.offsetWidth;
        this.pjHeight = this.$refs.timeSpace.offsetHeight;
        this.pjWidth = this.$refs.timeSpace.offsetWidth;
        // this.dataprocess();
        // console.log(this.barHeight, this.barWidth)

        // console.log(data);
        [this.allDay, this.barWidth] = this.getDay();

        const dataStore = useDataStore();

        dataStore.$subscribe((mutations, state) => {
            console.log(dataStore.selectGroup);
            if (dataStore.selectGroup == -2) {
                this.selectGroupTag = -1;
            } else if (dataStore.selectGroup != -1) {
                this.selectGroupTag = dataStore.selectGroup;
                [this.lineData, this.textPlace] = this.calcLine(dataStore.allData.data.nft_project_table, dataStore.allData.data.correlation_data, dataStore.allData.cpData.data, dataStore.selectGroup);

                this.timeData = this.calcIndividualProject(dataStore.allData.data.nft_project_table, dataStore.allData.projectData, dataStore.allData.cpData.data, dataStore.selectGroup);
            }
        })

    },
}
</script>

<style>
#timeAxis_g .tick text {
    font-size: 14px;
}

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
}

#legendSpace::-webkit-scrollbar {
    display: none;
}
</style>
