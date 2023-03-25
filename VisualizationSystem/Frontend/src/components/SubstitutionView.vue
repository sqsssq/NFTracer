<!--
 * @Description: 
 * @Author: Qing Shi
 * @Date: 2023-02-11 23:40:58
 * @LastEditTime: 2023-03-24 02:46:58
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
                                                        </span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
        </div>
        <div class="frameworkBody">
            <div style="height: 100%; width: 100%; margin-top: 5px;" ref="distributionView">
    
                <div class="tooltip" style="opacity: 0; background-color: white; border: solid; border-width: 2px; border-radius: 5px; padding: 5px; position: absolute; z-index: 100; left: -1000px;">
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
                </div>


                <div class="tooltipFlow" style="opacity: 0; background-color: white; border: solid; border-width: 2px; border-radius: 5px; padding: 5px; position: absolute; z-index: 100; left: -1000px;">
                    <div>
                        <svg width="310" height="50">
                            <text x="150" y="25" stroke="#534f4f" text-anchor="middle" font-weight="400">{{ flowHoverVal }}</text>
                            <path d="M120,35L180,35" stroke="#534f4f" fill="none" marker-end="url(#arrow)" stroke-width="2"></path>
                                        <g v-for="(item, i) in flowHoverData" :transform="translate(75 + i * 160, 25, 0)">
                                                                <clipPath id="clipPath2">
                                                                    <circle :cx="20" :cy="20" :r="20"></circle>
                                                                </clipPath>
                                                                <g clip-path="url(#clipPath2)"
                                                                    :transform="translate(-20, -20, 0)">
                                                                    <image :href="item.logo_link" x="0" y="0" :height="40"
                                                                        :width="40" />
                                                                </g>
                                        </g>
                                    </svg>
                    </div>
                    <div v-for="(item, i) in flowHoverData" :style="{width: '150px', display: 'inline', float: i == 0 ? 'left' : 'right'}">
                        <!-- <div style="text-align: center;">#Project Name</div> -->
                        <div style="text-align: center;">{{ item.name }}</div>
                        <!-- <div style="text-align: center;">#Holder</div> -->
                        <!-- <div style="text-align: center;">{{ item.holder }}</div> -->
                    </div>
                </div>
                <span style="position: absolute; top: 0px; color: #ABACBE; font-size: 14px;z-index: 100;">Selecting
                                                                <span class="php">{{ select_project_num }} projects</span> from <span class="php">{{ allProject_num }} results</span>
                <span>
                                                                    <p style="cursor:pointer; margin-top: 10px; width: 30px; height: 30px;" @click="groupSelectBtn">
                                                                        <svg v-if="
                                                                        groupSelect == 0" t="1678613511201" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="5014" width="25" height="25"><path d="M580.76 908.62a53.366667 53.366667 0 0 1-46.28-26.666667L404.1 656.133333l-154.666667 148.586667A21.333333 21.333333 0 0 1 213.333333 789.333333V106.666667a21.333333 21.333333 0 0 1 6.706667-15.526667c5.333333-5.02 15.26-8.74 25.72-2.7l91.946667 53.086667 498.833333 288a21.333333 21.333333 0 0 1-4.733333 38.966666l-206 59.64 130.386666 225.826667a53.333333 53.333333 0 0 1-19.526666 72.86l-129.333334 74.666667a53.02 53.02 0 0 1-26.633333 7.133333zM408.953333 600.546667a20.666667 20.666667 0 0 1 3 0.213333 21.333333 21.333333 0 0 1 15.48 10.453333l144 249.413334a10.666667 10.666667 0 0 0 14.566667 3.906666l129.333333-74.666666a10.666667 10.666667 0 0 0 3.906667-14.633334l-144-249.413333a21.333333 21.333333 0 0 1 12.546667-31.16l184.053333-53.286667L256 143.62v595.633333l138.18-132.76a21.333333 21.333333 0 0 1 14.773333-5.946666z" fill="#5C5C66" p-id="5015"></path></svg>
                                                                        <svg v-else t="1679354194696" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3683" width="25" height="25"><path d="M630.63970569 637.6867208l110.35938764 236.66748681c6.20083831 13.29490805 0.44014302 29.08827497-12.84181964 35.28911328l-96.26186588 44.88164187c-13.29490805 6.20083831-29.08827497 0.45308839-35.28911329-12.84181965l-112.87079191-242.05276602-138.77450271 138.77450272c-10.36925155 10.36925155-27.17235831 10.36925155-37.54160987 0.01294537a26.56392533 26.56392533 0 0 1-7.78017501-18.78375032V147.18616969c0-14.66711861 11.88386133-26.55097995 26.55097995-26.55097996 6.60214518 0 12.97127348 2.45962272 17.86462814 6.89988899l494.18998519 449.26950715c10.84823072 9.86438163 11.65084445 26.65454302 1.78646281 37.50277374a26.56004172 26.56004172 0 0 1-17.6057205 8.6086795L630.63970569 637.6867208z" p-id="3684" fill="#5C5C66"></path></svg>
                                                                    </p>

                                                                    <p style="cursor:pointer; margin-top: 10px;width: 30px; height: 30px;" @click="projectSelectBtn">
                                                                            <svg v-if="projectSelectSta == 0" t="1679354394057" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="4906" width="25" height="25"><path d="M512 896C192 896 12.8 546.133333 4.266667 529.066667c-4.266667-12.8-4.266667-25.6 0-38.4C12.8 477.866667 192 128 512 128s499.2 349.866667 507.733333 366.933333c4.266667 12.8 4.266667 25.6 0 38.4-8.533333 12.8-187.733333 362.666667-507.733333 362.666667z m-422.4-384c38.4 68.266667 192 298.666667 422.4 298.666667s379.733333-230.4 422.4-298.666667c-38.4-68.266667-192-298.666667-422.4-298.666667s-379.733333 230.4-422.4 298.666667z" p-id="4907" fill="#5C5C66"></path><path d="M512 682.666667c-93.866667 0-170.666667-76.8-170.666667-170.666667s76.8-170.666667 170.666667-170.666667 170.666667 76.8 170.666667 170.666667-76.8 170.666667-170.666667 170.666667z m0-256c-46.933333 0-85.333333 38.4-85.333333 85.333333s38.4 85.333333 85.333333 85.333333 85.333333-38.4 85.333333-85.333333-38.4-85.333333-85.333333-85.333333z" p-id="4908" fill="#5C5C66"></path></svg>
                                                                            <svg v-else t="1679354463560" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="5146" width="25" height="25"><path d="M379.428571 512a128 128 0 1 0 256 0 128 128 0 1 0-256 0z m624.228572-29.485714C895.314286 254.285714 731.542857 139.428571 512 139.428571c-219.657143 0-383.314286 114.857143-491.657143 343.2a68.914286 68.914286 0 0 0 0 58.857143C128.685714 769.714286 292.457143 884.631429 512 884.631429c219.657143 0 383.314286-114.857143 491.657143-343.2 8.8-18.514286 8.8-40 0-58.857143zM507.428571 713.142857c-111.085714 0-201.142857-90.057143-201.142857-201.142857s90.057143-201.142857 201.142857-201.142857 201.142857 90.057143 201.142858 201.142857-90.057143 201.142857-201.142858 201.142857z" p-id="5147" fill="#5c5c66"></path></svg>
                                                                        </p>
                                                                        <p style="cursor:pointer; margin-top: 10px;width: 30px; height: 30px;" @click="zoomBtn">
                                                                            <svg t="1678908588773" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2763" width="25" height="25"><path d="M999.15093333 997.63321482H648.6546963v-77.6722963h272.82394073V648.41197037h77.6722963zM99.85137778 372.67531852h-77.6722963V23.63543703h350.49623704v77.6722963H99.85137778z" p-id="2764" fill="#777777"></path><path d="M53.30504059 108.18294518l54.92159526-54.92159526 353.64681956 353.64681956-54.92159526 54.92159527zM562.35349333 617.21440711l54.92159526-54.92280889L991.51720297 936.53492622l-54.92159527 54.92159526zM999.15093333 374.13167408h-77.6722963V101.30773333H650.11105185v-77.6722963h349.03988148zM371.21896297 997.63321482H22.17908148V647.07697778h77.6722963v272.82394074H371.21896297z" p-id="2765" fill="#777777"></path><path d="M60.58196385 908.09472948L406.73826133 562.23213037l54.8985363 54.94586785L115.48292741 963.04059733zM562.38019318 406.71277511l367.72006874-367.72128236 54.9228089 54.92280888L617.30178845 461.63437037z" p-id="2766" fill="#777777"></path></svg>
                                                                        </p>
                                                                        <p style="cursor:pointer; margin-top: 10px;width: 30px; height: 30px;" @click="refreshBtn">
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
                                            
                                                                        <g :transform="translate(0, 0, 180-6)">
                                                                            <path v-for="(arc_item, arc_i) in innerArc" :key="'arc' + arc_i" :d="arc_item"
                                                                                stroke="#C6BCBC" :fill="'none'" :opacity="innerArea[arc_i].cnt == 0 ? 0 : 1"></path>
                                                                        </g>
                                                                        <g>
                                                                            <path v-for="(arc_item, arc_i) in monthArc" :key="'select_time' + arc_i" :d="arc_item"
                                                                                fill="#C6BCBC" stroke="#C6BCBC"></path>
                                                                        </g>

                                                                <clipPath id="clipPathNetwork">
                                                                    <circle :cx="0" :cy="0" :r="distributionHeight * .63 / 2 + 10"></circle>
                                                                </clipPath>
                                            
                                                                        <g clip-path="url(#clipPathNetwork)">
                                                                            <circle cx="0" cy="0" :r="distributionHeight * .63 / 2" fill="none" stroke="#534F4F"
                                                                                stroke-width="1"></circle>
                                                                            <path v-for="item in 30" :key="'path' + item"
                                                                                :d="'M 0 0 L ' + (Math.sin(((item * 12 - 6) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2)) + ' ' + (Math.cos(((item * 12 - 6) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2))"
                                                                                stroke="#534F4F" stroke-width="0.5"></path>
                                                                            
                                                                        </g>
                                                                        <g :transform="translate(0, 0, 0)">
                                            
                                                                            <path v-for="(arc_item, arc_i) in outerArc" :key="'arc' + arc_i" :d="arc_item.d" stroke="none" :id="'GroupArc' + arc_item.group" :class="'groupArc'"
                                                                                :fill="arc_i == groupTag ? 'none' : colormap[arc_i]" @mouseenter="mouseoverGroup(arc_item.group)" @mouseout="mouseoutGroup()"
                                                                                @click="clickGroup(arc_item.group)"></path>
                                            
                                                                            <path v-for="(arc_item, arc_i) in groupArc" :key="'arc' + arc_i" :d="arc_item.arc" :id="'GroupArc' + arc_item.group"
                                                                                :fill="arc_item.group == groupTag ? 'white' : colormap[parseInt(arc_item.group)]" :class="'groupArc'"
                                                                                :stroke="arc_item.group == groupTag ? '#C6BCBC' : colormap[parseInt(arc_item.group)]" 
                                                                                stroke-width="1" @mouseenter="mouseoverProject($event, arc_item.project)" @mouseout="mouseoutProject()"
                                                                                @click="clickProject(arc_item.project)"></path>
                                        
                                                                            <!-- <g v-for="(item, i) in allGroupArc" :key="'all_arc' + i" @mouseenter="mouseoverGroup(item[0].group)" @mouseout="mouseoutGroup()"
                                                                                @click="clickGroup(arc_item.group)">
                                                                                <path v-for="(arc_item, arc_i) in item" :key="'arc' + arc_i " :d="arc_item.arc" :id="'GroupArc' + arc_item.group"
                                                                                :fill="arc_item.group == groupTag ? 'white' : colormap[parseInt(arc_item.group)]" :class="'groupArc'"
                                                                                :stroke="arc_item.group == groupTag ? '#C6BCBC' : colormap[parseInt(arc_item.group)]" :stroke-opacity="arc_item.tag"></path>
                                                                            </g> -->
                                                                        </g>
                                                                        <g>
                                                                            <g v-for="(a_item, a_i) in innerArea" :key="'ia' + a_i"
                                                                                :transform="translate(0, 0, a_i * 12)">
                                                                                <path :d="a_item[filterValue]" :fill="axisColorA[filterValue]" :stroke="axisColorA[filterValue]" :opacity="a_item.cnt == 0 ? 0 : 1"></path>
                                                                            </g>
                                                                        </g>
                                                                        <g clip-path="url(#clipPathNetwork)">
                                                                            
                                                                            <circle v-for="(c_item, c_i) in scatterData" :key="'gc' + c_i" :id="'pro_cir' + c_item.id_cnt" :class="'all_pro_cir'" :cx="c_item.cx"
                                                                                :cy="c_item.cy" :r="5" :fill="(selectGroup == -1 && ProjectClickSta == 0) ? colormap[c_item.group] : '#c0c0c0'" :opacity="(selectGroup == -1 && ProjectClickSta == 0) ?  1:  0.3" @mouseenter="ProjectClickSta == 0 ? mouseoverProject($event, c_item.data): null" @mouseout="mouseoutProject"
                                                                                @click="clickProject(c_item.data)">
                                                                            </circle>
                                                                        </g>
                                                                        <g  clip-path="url(#clipPathNetwork)">
                
                                                                            <circle v-for="(c_item, c_i) in projectSelect" :key="'gc' + c_i" :cx="c_item.x"
                                                                                :cy="c_item.y" :r="c_item.sel == 1 ? 8 : 5" :stroke-width="c_item.sel == 1 ? 3 : 0" :stroke="c_item.sel == 1 ? 'black' : 'none'" :fill="colormap[c_item.group]" :opacity="1" @mouseenter="mouseoverProject($event, c_item.data)" @mouseout="mouseoutProject"></circle>
                                                                        </g>
        
                                                                        <g>
                                                                            <defs>
            <!-- A marker to be used as an arrowhead -->
            <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
                <path d="M 0 0 L 10 5 L 0 10" stroke-width="100" />
            </marker>
        </defs>
            <path v-for="(p_item, p_i) in projectFlow" :key="'flow' + p_i" :d="p_item.d" :fill="'none'" :stroke="lineHover == p_i || lineHover == -1 ? (p_item.dir == 1 ? '#181CF7' : '#A50021') : (p_item.dir == 1 ? '#181CF7' : '#A50021') " :id="'flow_line' + p_i" :class="'all_flow_line'" :stroke-width="p_item.w" :marker-end="lineHover == p_i && p_item.dir == 1 ?'url(#arrow)':''" :marker-start="lineHover == p_i && p_item.dir == 0 ?'url(#arrow)':''" :opacity="lineHover == -1 ? 0.5 : (lineHover == p_i ? 1 : 0.1)" @mouseenter="mouseoverFlow($event, p_item, p_i)" @mouseout="mouseoutFlow()"></path>
        </g>
        <g v-show="showHSB">
            <path :d="'M ' + (Math.sin(((0) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2)) + ' ' + (-Math.cos(((0) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2)) + ' L' + (Math.sin(((120) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2)) + ' ' + (-Math.cos(((120) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2)) + ' L ' + (Math.sin(((240) * Math.PI) / 180) * (distributionHeight * .63 / 2 - 2)) + ' ' + (-Math.cos(((240) * Math.PI) / 180) * (distributionHeight * .56 / 2 - 2)) + ' Z'"
                                                                                stroke-dasharray="5.5" stroke="#C6BCBC" fill="none"></path>
                                            
                                                                            <text :x="(Math.sin(((0) * Math.PI) / 180) * (distributionHeight * .63 / 2 + 15))"
                                                                                :y="(-Math.cos(((0) * Math.PI) / 180) * (distributionHeight * .63 / 2 + 15))"
                                                                                font-size="14" dy="0.5em" text-anchor="middle" fill="#534F4F"
                                                                                font-weight="bold">H</text>
                                                                            <text :x="(Math.sin(((120) * Math.PI) / 180) * (distributionHeight * .63 / 2 + 15))"
                                                                                :y="(-Math.cos(((120) * Math.PI) / 180) * (distributionHeight * .63 / 2 + 15))"
                                                                                font-size="14" dy="0.5em" text-anchor="middle" fill="#534F4F"
                                                                                font-weight="bold">B</text>
                                                                            <text :x="(Math.sin(((240) * Math.PI) / 180) * (distributionHeight * .63 / 2 + 15))"
                                                                                :y="(-Math.cos(((240) * Math.PI) / 180) * (distributionHeight * .63 / 2 + 15))"
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
import { select, selectAll } from 'd3-selection';
import { arc, area, curveBasis, pie } from 'd3-shape';
import { useDataStore } from "../stores/counter";
import { extent } from 'd3-array';

export default {
    name: "APP",
    props: [],
    data() {
        return {
            lineHover: -1,
            flowHoverVal: 0,
            flowHoverData: [],
            cpData: {},
            showHSB: 1,
            groupSelect: 0,
            groupClick: 0,
            projectSelectSta: 0,
            ProjectClickSta: 0,
            ProjectClickName: '',
            zoomTag: 0,
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
            flow_data: {}
        };
    },
    methods: {
        mouseoutFlow() {

            select('.tooltipFlow').style('opacity', 0)
                .style('left', '-1000px')
                .style('top', '0px')
                this.lineHover = -1;
        },
        mouseoverFlow(event, data, cnt) {
            this.lineHover = cnt;
            // console.log(data)
            let s, t;
            if (data.dir == 1) {
                s = data.p1;
                t = data.p2;
            } else {
                s = data.p2;
                t = data.p1;
            }
            let sdata = {}, tdata = {};
            for (let i in this.cpData.data) {
                if (this.cpData.data[i]['Project Name'] == s) {
                    sdata['logo_link'] = this.cpData.data[i]['logo_link'];
                    sdata['name'] = s;
                    sdata['holder'] = this.cpData.data[i]['Holder'];
                    sdata['val'] = data.val;
                }
                if (this.cpData.data[i]['Project Name'] == t) {
                    
                    tdata['logo_link'] = this.cpData.data[i]['logo_link'];
                    tdata['name'] = t;
                    tdata['holder'] = this.cpData.data[i]['Holder'];
                    tdata['val'] = data.val;
                }
            }
            this.flowHoverVal = parseFloat(sdata.val).toFixed(2);
            this.flowHoverData = [sdata, tdata];
            // console.log(this.flowHoverData);

            select('.tooltipFlow')
                .style('opacity', 1)
                .style('left', event.layerX + 20 + 'px')
                .style('top', event.layerY - 15 + 'px')

            // select('.tooltipFlow')
            //     .style('opacity', 1)
            //     .style('right', 10 + 'px')
            //     .style('top', 10 + 'px')
        },
        refreshBtn() {
            const dataStore = useDataStore();
            dataStore.selectGroup = -2;
            this.selectGroup = -1;
            // this.zoomBtn();
            if (this.zoomTag == 1) {
                this.zoomTag = 0;
                this.showHSB = 1;

                [this.scatterData, this.innerArea] = this.calcScatter(this.cpData.data, 1, this.projectSelect);

            }
            this.groupSelect = 0,
                this.groupClick = 0,
                this.projectSelectSta = 0,
                this.ProjectClickSta = 0,
                this.ProjectClickName = '',
                // zoomTag=  0,
                this.select_project_num = 0,
                // allProject_num: 0,
                // all_group_num: 0,
                this.projectFlow = [];
            this.projectSelect = [];
            this.mouseoutGroup();
        },
        linkArc(d) {
            // console.log(d);
            const r = Math.hypot(d.target.x - d.source.x, d.target.y - d.source.y);
            return `M${d.source.x},${d.source.y}A${r},${r} 0 0,1 ${d.target.x},${d.target.y}`;
        },
        translate(x, y, d) {
            return `translate(${x}, ${y}) rotate(${d})`;
        },
        groupSelectBtn() {
            this.groupSelect = !this.groupSelect;
        },
        zoomBtn() {
            this.zoomTag = !this.zoomTag;
            if (this.zoomTag) {
                this.showHSB = 0;
                [this.scatterData, this.innerArea] = this.calcScatter(this.cpData.data, 2, this.projectSelect);
                if (this.ProjectClickSta) {

                    [this.projectFlow, this.projectSelect] = this.calcProjFlow(this.flow_data, this.ProjectClickName);
                }
                if (this.groupClick) {

                    this.calcFlowData(this.selectGroup);
                }
            } else {
                this.showHSB = 1;

                [this.scatterData, this.innerArea] = this.calcScatter(this.cpData.data, 1, this.projectSelect);
                if (this.ProjectClickSta) {

                    [this.projectFlow, this.projectSelect] = this.calcProjFlow(this.flow_data, this.ProjectClickName);
                }
                if (this.groupClick) {

                    this.calcFlowData(this.selectGroup);
                }
            }
        },
        projectSelectBtn() {
            this.projectSelectSta = !this.projectSelectSta;
        },
        clickGroup(group) {
            if (this.groupSelect == 0) return;
            this.groupClick = 1;
            this.selectGroup = group;
            // console.log(group);
            const dataStore = useDataStore();
            // if (dataStore.selectGroup != -1) {

            //     select('#sel_m1' + dataStore.selectGroup).attr('opacity', 0);
            //     select('#sel_m2' + dataStore.selectGroup).attr('opacity', 0);
            //     select('#sel_m3' + dataStore.selectGroup).attr('opacity', 0);
            // }
            // select('#sel_m1' + group).attr('opacity', 1);
            // select('#sel_m2' + group).attr('opacity', 1);
            // select('#sel_m3' + group).attr('opacity', 1);
            dataStore.selectGroup = group;
            let select_project_num = 0;
            for (let i in this.cpData.data) {
                if (this.cpData.data[i]['Group'] == group) {
                    select_project_num++;
                }
            }
            this.select_project_num = select_project_num;
            this.calcFlowData(this.selectGroup);
        },
        mouseoverGroup(group) {
            if (this.groupSelect == 0) return;
            if (this.groupClick == 1) return;
            selectAll('.groupArc').attr('opacity', 0.2);
            selectAll('#GroupArc' + group).attr('opacity', 1);
        },
        mouseoutGroup() {
            // if (this.groupSelect == 0) return;
            // if (this.groupClick == 1) return;
            selectAll('.groupArc').attr('opacity', 1);
        },
        calcIndividual(data, r, x, y) {
            // console.log(data);
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
                img_r: r / 2,
                name: data.name,
                time: data.time,
                IMP: data.outer['IMP'],
                holder: data.inner['holder'],
                sumPeople: data.inner.holder + data.inner.seller + data.inner.buyer,
            }
        },

        mouseoverProject(event, p_data) {
            // console.log(data, id);
            // console.log(p_data);
            let data = p_data;
            // if (this.projectSelectSta == 0) return;
            // if (this.ProjectClickSta == 1) return;

            this.glyphData = [{
                name: this.calcIndividual({
                    inner: {
                        holder: data['Holder'],
                        buyer: data['Buyer'],
                        seller: data['Seller']
                    },
                    outer: {
                        M1: (data['M1'] - this.valueRange.m1[0]) / (this.valueRange.m1[1] - this.valueRange.m1[0]),
                        M2: (data['M2'] - this.valueRange.m2[0]) / (this.valueRange.m2[1] - this.valueRange.m2[0]),
                        M3: (data['M3'] - this.valueRange.m3[0]) / (this.valueRange.m3[1] - this.valueRange.m3[0]),
                        IMP: (data['IMP'] - this.valueRange.imp[0]) / (this.valueRange.imp[1] - this.valueRange.imp[0])
                    },

                    link: data['Project Name'] == "Moonbirds" ? 'https://i.seadn.io/gae/H-eyNE1MwL5ohL-tCfn_Xa1Sl9M9B4612tLYeUlQubzt4ewhr4huJIR5OLuyO3Z5PpJFSwdm7rq-TikAh7f5eUw338A2cy6HRH75?auto=format&w=256' : data['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : data['logo_link'],
                    // link: data['logo_link'],
                    name: data['Project Name'],
                }, 40, 0, 0)
            }];
            select('.tooltip')
                .style('opacity', 1)
                .style('left', event.layerX + 20 + 'px')
                .style('top', event.layerY - 15 + 'px')
            let id_cnt = -1;
            for (let i in this.scatterData) {
                if (this.scatterData[i].name == data['Project Name']) {
                    id_cnt = this.scatterData[i].id_cnt;
                    break;
                }
            }
            select('#pro_cir' + id_cnt).attr('r', 15).attr('stroke', 'red');
            // selectAll('.groupArc').attr('opacity', d => {
            //     // console.log(d);
            //     return 0.2});
            // select('#pro_' + id).attr('opacity', 1);
        },
        mouseoutProject() {
            select('.tooltip').style('opacity', 0)
                .style('left', '-1000px')
                .style('top', '0px')

            selectAll('.all_pro_cir').attr('r', 5).attr('stroke', 'none');
            // if (this.projectSelectSta == 0) return;
            // if (this.ProjectClickSta == 1) return;
            // selectAll('.groupArc').attr('opacity', 1);
        },
        clickProject(data) {
            console.log(data);
            this.ProjectClickSta = 1;
            let name = data['Project Name'];
            let namespace = {};
            namespace[name] = 1;
            this.ProjectClickName = namespace;
            [this.projectFlow, this.projectSelect] = this.calcProjFlow(this.flow_data, namespace);
            // console.log(this.projectFlow, this.projectSelect);
        },
        calcProjFlow(data, sel_id) {
            console.log(sel_id);
            let repeat_data = {};
            let fl_data = data.data;
            let res_data = [];
            let new_sel = {};
            let select_name = '';
            for (let i in sel_id) {
                select_name = i;
            }
            for (let i in fl_data) {
                // if (sel_id[fl_data[i]['Project Name From']] == 1 || sel_id[fl_data[i]['Project Name To']] == 1) {
                if (sel_id[fl_data[i]['Project Name From']] == 1) {
                    if (repeat_data[fl_data[i]['Project Name From'] + fl_data[i]['Project Name To']] == 1 || repeat_data[fl_data[i]['Project Name To'] + fl_data[i]['Project Name From']] == 1) {
                        continue;
                    }
                    new_sel[fl_data[i]['Project Name From']] = 1;
                    new_sel[fl_data[i]['Project Name To']] = 1;
                    repeat_data[fl_data[i]['Project Name From'] + fl_data[i]['Project Name To']] = 1;
                    repeat_data[fl_data[i]['Project Name To'] + fl_data[i]['Project Name From']] = 1;
                    res_data.push({
                        p1: fl_data[i]['Project Name From'],
                        p2: fl_data[i]['Project Name To'],
                        v: fl_data[i]['SubstitutionFlow']
                    });
                }
            }
            let extentData = extent(res_data, d => Math.abs(d.v));
            // console.log(extentData);
            let wScale = scaleLinear(extentData, [0.1, 5]);
            let pos_data = {};
            // console.log(this.scatterData)
            let projectSelect = [];
            for (let i in this.scatterData) {
                pos_data[this.scatterData[i]['name']] = {
                    x: this.scatterData[i]['cx'],
                    y: this.scatterData[i]['cy'],
                    group: this.scatterData[i]['group'],
                    data: this.scatterData[i]['data'],
                    name: this.scatterData[i]['name'],
                    sel: 0
                }
            }
            for (let i in new_sel) {
                if (i == select_name)
                    pos_data[i].sel = 1;
                projectSelect.push(pos_data[i]);
            }
            // console.log(pos_data);
            for (let i in res_data) {
                res_data[i]['d'] = this.linkArc({
                    source: pos_data[res_data[i].p1],
                    target: pos_data[res_data[i].p2]
                });
                res_data[i]['w'] = wScale(Math.abs(res_data[i].v));
                res_data[i]['val'] = ((Math.abs(res_data[i].v) - extentData[0]) / (extentData[1] - extentData[0])).toFixed(2);
                res_data[i]['dir'] = res_data[i].v > 0 ? 1 : 0
            }
            // console.log(res_data);
            return [res_data, projectSelect];
        },
        calcFlowData(group) {

            let namespace = {};
            for (let i in this.cpData.data) {
                // console.log(this.cpData[i]['Group'])
                if (this.cpData.data[i]['Group'] == group) {
                    namespace[this.cpData.data[i]['Project Name']] = 1;
                }
            }

            [this.projectFlow, this.projectSelect] = this.calcFlow(this.flow_data, namespace);

        },
        calcFlow(data, sel_id) {
            console.log(data.data, sel_id);
            let repeat_data = {};
            let fl_data = data.data;
            let res_data = [];
            for (let i in fl_data) {
                if (sel_id[fl_data[i]['Project Name From']] == 1 && sel_id[fl_data[i]['Project Name To']] == 1) {
                    if (repeat_data[fl_data[i]['Project Name From'] + fl_data[i]['Project Name To']] == 1 || repeat_data[fl_data[i]['Project Name To'] + fl_data[i]['Project Name From']] == 1) {
                        continue;
                    }
                    repeat_data[fl_data[i]['Project Name From'] + fl_data[i]['Project Name To']] = 1;
                    repeat_data[fl_data[i]['Project Name To'] + fl_data[i]['Project Name From']] = 1;
                    res_data.push({
                        p1: fl_data[i]['Project Name From'],
                        p2: fl_data[i]['Project Name To'],
                        v: fl_data[i]['SubstitutionFlow']
                    });
                }
            }
            let extentData = extent(res_data, d => Math.abs(d.v));
            // console.log(extentData);
            let wScale = scaleLinear(extentData, [0.1, 5]);
            let pos_data = {};
            // console.log(this.scatterData)
            let projectSelect = [];
            for (let i in this.scatterData) {
                pos_data[this.scatterData[i]['name']] = {
                    x: this.scatterData[i]['cx'],
                    y: this.scatterData[i]['cy'],
                    group: this.scatterData[i]['group'],
                    data: this.scatterData[i]['data'],
                    name: this.scatterData[i]['name'],
                    sel: 0
                }
            }
            for (let i in sel_id) {
                projectSelect.push(pos_data[i]);
            }
            // console.log(pos_data);
            for (let i in res_data) {
                res_data[i]['d'] = this.linkArc({
                    source: pos_data[res_data[i].p1],
                    target: pos_data[res_data[i].p2]
                });
                res_data[i]['w'] = wScale(Math.abs(res_data[i].v));
                res_data[i]['dir'] = res_data[i].v > 0 ? 1 : 0
                res_data[i]['val'] = (Math.abs(res_data[i].v) - extentData[0]) / (extentData[1] - extentData[0]).toFixed(2);
            }
            // console.log(res_data);
            return [res_data, projectSelect];
        },
        msTest(data) {
            // console.log(data)
        },
        calcArc(data) {
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
        // calcScatter(data, powIndex) {
        //     let scatterData = [];
        //     // console.log(data)
        //     let max_m1 = 0,
        //         max_m2 = 0,
        //         max_m3 = 0,
        //         max_imp = 0;
        //     let min_m1 = 99999,
        //         min_m2 = 99999,
        //         min_m3 = 99999,
        //         min_imp = 99999;
        //     for (let i in data) {
        //         max_m1 = Math.max(max_m1, data[i].M1)
        //         max_m2 = Math.max(max_m2, data[i].M2)
        //         max_m3 = Math.max(max_m3, data[i].M3)
        //         max_imp = Math.max(max_imp, data[i].IMP);
        //         min_m1 = Math.min(min_m1, data[i].M1);
        //         min_m2 = Math.min(min_m2, data[i].M2);
        //         min_m3 = Math.min(min_m3, data[i].M3);
        //         min_imp = Math.min(min_imp, data[i].IMP);
        //     }
        //     let t_h = Math.abs((-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) - (-Math.cos(((0) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)));
        //     let areaData = [];
        //     for (let i = 0; i < 30; ++i) {
        //         areaData.push({
        //             project: [],
        //             m1Area: new Array(5).fill(0),
        //             m2Area: new Array(5).fill(0),
        //             m3Area: new Array(5).fill(0),
        //             impArea: new Array(5).fill(0)
        //         })
        //     }
        //     let m1_max = 0,
        //         m2_max = 0,
        //         m3_max = 0,
        //         imp_max = 0;
        //     let cnt = 0;
        //     let minx = 999,
        //         maxx = -1,
        //         miny = 999,
        //         maxy = -1;
        //     for (let i in data) {
        //         let sx = (parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer)) + parseFloat(data[i].Buyer) * 2 / (data[i].Holder + data[i].Seller + data[i].Buyer)) / Math.sqrt(3);
        //         let sy = parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer));
        //         minx = Math.min(minx, sx);
        //         maxx = Math.max(maxx, sx);
        //         miny = Math.min(miny, sy);
        //         maxy = Math.max(maxy, sy);
        //     }
        //     let xScale = scaleLinear([minx, maxx], [0.5 - Math.sqrt(2) / 4, 0.5 + Math.sqrt(2) / 4]);
        //     let yScale = scaleLinear([miny, maxy], [0.5 - Math.sqrt(2) / 4, 0.5 + Math.sqrt(2) / 4]);
        //     let pro_cnt = 0;
        //     for (let i in data) {
        //         // console.log(data[i]);
        //         let sx = (parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer)) + parseFloat(data[i].Buyer) * 2 / (data[i].Holder + data[i].Seller + data[i].Buyer)) / Math.sqrt(3);
        //         let sy = parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer));
        //         let ss = parseFloat(data[i].Seller / (data[i].Holder + data[i].Seller + data[i].Buyer));
        //         let sb = parseFloat(data[i].Buyer / (data[i].Holder + data[i].Seller + data[i].Buyer));
        //         if (powIndex == -1) {
        //             sx = xScale(sx);
        //             sy = yScale(sy);
        //         }
        //         // if (powIndex != 1) {
        //         //     if (sx > 0.5) {
        //         //         // if (cnt % 2 == 0) {
        //         //         // sx += (1 - ss) * ss * Math.sqrt(3) / 2;
        //         //         // sy += (1 - ss) * ss / 2;

        //         //         sx += (ss - Math.atan(ss)) * 12 * Math.sqrt(3) / 2;
        //         //         sy += (ss - Math.atan(ss)) * 12 * ss / 2;
        //         //     } else {
        //         //         // sx -= (1 - sb) * sb * Math.sqrt(3) / 2;
        //         //         // sy -= (1 - sb) * sb / 2;

        //         //         sx -= (sb - Math.atan(sb)) * 12 * Math.sqrt(3) / 2;
        //         //         sy -= (sb - Math.atan(sb)) * 12 * sb / 2;
        //         //     }
        //         //     cnt++;
        //         // }
        //         // console.log(sx, sy);
        //         // console.log(data[i])
        //         let tp = {
        //             name: data[i]['Project Name'],
        //             data: data[i],
        //             group: data[i].Group,
        //             x: sx,
        //             y: sy,
        //             rx: sx * t_h,
        //             ry: sy * t_h,
        //             t_h: t_h,
        //             center: {
        //                 x: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)),
        //                 y: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2))
        //             },
        //             cx: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) + sx * t_h,
        //             cy: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) - sy * t_h,
        //             id_cnt: pro_cnt++
        //         };
        //         // console.log(tp);
        //         scatterData.push(tp);

        //         let t_cnt = (Math.acos(tp.cy / (Math.sqrt(Math.pow(tp.cx, 2) + Math.pow(tp.cy, 2)))) / (Math.PI / 180))
        //         if (tp.cx > 0)
        //             t_cnt = 360 - t_cnt - 6;
        //         else
        //             t_cnt = t_cnt - 6;
        //         t_cnt = (Math.floor(t_cnt / 12) + 31) % 30
        //         // if (t_cnt == -1) t_cnt++;
        //         // console.log(Math.floor(t_cnt));

        //         let m11 = Math.floor((data[i]['M1'] - min_m1) / (max_m1 - min_m1) / (1 / 5));
        //         let m22 = Math.floor((data[i]['M2'] - min_m2) / (max_m2 - min_m2) / (1 / 5));
        //         let m33 = Math.floor((data[i]['M3'] - min_m3) / (max_m3 - min_m3) / (1 / 5));
        //         let impp = Math.floor((data[i]['IMP'] - min_imp) / (max_imp - min_imp) / (1 / 5));
        //         m1_max = Math.max(m1_max, m11);
        //         m2_max = Math.max(m2_max, m22);
        //         m3_max = Math.max(m3_max, m33);
        //         imp_max = Math.max(imp_max, impp);
        //         m11 = m11 == 5 ? m11 - 1 : m11;
        //         m22 = m22 == 5 ? m22 - 1 : m22;
        //         m33 = m33 == 5 ? m33 - 1 : m33;
        //         impp = impp == 5 ? impp - 1 : impp;
        //         areaData[Math.floor(t_cnt)].project.push(data[i]);
        //         areaData[Math.floor(t_cnt)].m1Area[m11]++;
        //         areaData[Math.floor(t_cnt)].m2Area[m22]++;
        //         areaData[Math.floor(t_cnt)].m3Area[m33]++;
        //         // if (i == 10)
        //         // break;
        //         areaData[Math.floor(t_cnt)].impArea[impp]++;
        //     }
        //     // console.log(scatterData)
        //     let ayScale = scaleLinear([0, 4], [this.distributionHeight * .63 / 2 + 15, this.distributionHeight * .71 / 2 - 2]);
        //     let m1Scale = scaleLinear([0, m1_max], [0, 4]);
        //     let m2Scale = scaleLinear([0, m2_max], [0, 4]);
        //     let m3Scale = scaleLinear([0, m3_max], [0, 4]);
        //     let impScale = scaleLinear([0, imp_max], [0, 4]);
        //     let ag1 = area()
        //         .curve(curveBasis)
        //         .x0(d => m1Scale(d))
        //         .x1(d => -m1Scale(d))
        //         .y((d, i) => ayScale(i));
        //     let ag2 = area()
        //         .curve(curveBasis)
        //         .x0(d => m2Scale(d))
        //         .x1(d => -m2Scale(d))
        //         .y((d, i) => ayScale(i));
        //     let ag3 = area()
        //         .curve(curveBasis)
        //         .x0(d => m3Scale(d))
        //         .x1(d => -m3Scale(d))
        //         .y((d, i) => ayScale(i));
        //     let ag4 = area()
        //         .curve(curveBasis)
        //         .x0(d => impScale(d))
        //         .x1(d => -impScale(d))
        //         .y((d, i) => ayScale(i));
        //     let res_area = [];
        //     for (let i in areaData) {
        //         res_area.push({
        //             m1d: ag1(areaData[i].m1Area),
        //             m2d: ag2(areaData[i].m2Area),
        //             m3d: ag3(areaData[i].m3Area),
        //             impd: ag4(areaData[i].impArea),
        //             cnt: areaData[i].project.length
        //         });
        //         // if (i == 2)
        //         // break;
        //     }


        //     return [scatterData, res_area];
        // },

        calcScatter(pre_data, powIndex, namespace) {
            let data = [];
            if (namespace.length == 0) {
                data = pre_data;
            } else {
                let namespaceX = {};
                for (let i in namespace) {
                    namespaceX[namespace[i]['name']] = 1;
                }
                for (let i in pre_data) {
                    if (namespaceX[pre_data[i]['Project Name']] == 1) {
                        data.push(pre_data[i]);
                    }
                }
            }
            console.log(data);
            let scatterData = [];
            // console.log(data)
            let max_m1 = 0,
                max_m2 = 0,
                max_m3 = 0,
                max_imp = 0;
            let min_m1 = 99999,
                min_m2 = 99999,
                min_m3 = 99999,
                min_imp = 99999;
            for (let i in data) {
                max_m1 = Math.max(max_m1, data[i].M1)
                max_m2 = Math.max(max_m2, data[i].M2)
                max_m3 = Math.max(max_m3, data[i].M3)
                max_imp = Math.max(max_imp, data[i].IMP);
                min_m1 = Math.min(min_m1, data[i].M1);
                min_m2 = Math.min(min_m2, data[i].M2);
                min_m3 = Math.min(min_m3, data[i].M3);
                min_imp = Math.min(min_imp, data[i].IMP);
            }
            let t_h = Math.abs((-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) - (-Math.cos(((0) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)));
            // console.log(t_h);
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
            let m1_max = 0,
                m2_max = 0,
                m3_max = 0,
                imp_max = 0;
            let cnt = 0;
            let minx = 999,
                maxx = -1,
                miny = 999,
                maxy = -1;
            for (let i in data) {
                let sx = (parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer)) + parseFloat(data[i].Buyer) * 2 / (data[i].Holder + data[i].Seller + data[i].Buyer)) / Math.sqrt(3);
                let sy = parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer));
                minx = Math.min(minx, sx);
                maxx = Math.max(maxx, sx);
                miny = Math.min(miny, sy);
                maxy = Math.max(maxy, sy);
            }
            let xScale = scaleLinear([minx, maxx], [0.5 - Math.sqrt(2) / 4, 0.5 + Math.sqrt(2) / 4]);
            let yScale = scaleLinear([miny, maxy], [0.5 - Math.sqrt(2) / 4, 0.5 + Math.sqrt(2) / 4]);
            let pro_cnt = 0;
            for (let i in data) {
                // console.log(data[i]);
                let sx = (parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer)) + parseFloat(data[i].Buyer) * 2 / (data[i].Holder + data[i].Seller + data[i].Buyer)) / Math.sqrt(3);
                let sy = parseFloat(data[i].Holder / (data[i].Holder + data[i].Seller + data[i].Buyer));
                let ss = parseFloat(data[i].Seller / (data[i].Holder + data[i].Seller + data[i].Buyer));
                let sb = parseFloat(data[i].Buyer / (data[i].Holder + data[i].Seller + data[i].Buyer));
                if (powIndex == 2) {
                    sx = xScale(sx);
                    sy = yScale(sy);
                }
                // if (powIndex != 1) {
                //     if (sx > 0.5) {
                //         // if (cnt % 2 == 0) {
                //         // sx += (1 - ss) * ss * Math.sqrt(3) / 2;
                //         // sy += (1 - ss) * ss / 2;

                //         sx += (ss - Math.atan(ss)) * 12 * Math.sqrt(3) / 2;
                //         sy += (ss - Math.atan(ss)) * 12 * ss / 2;
                //     } else {
                //         // sx -= (1 - sb) * sb * Math.sqrt(3) / 2;
                //         // sy -= (1 - sb) * sb / 2;

                //         sx -= (sb - Math.atan(sb)) * 12 * Math.sqrt(3) / 2;
                //         sy -= (sb - Math.atan(sb)) * 12 * sb / 2;
                //     }
                //     cnt++;
                // }
                // console.log(sx, sy);
                // console.log(data[i])
                let tp = {
                    name: data[i]['Project Name'],
                    data: data[i],
                    group: data[i].Group,
                    x: sx,
                    y: sy,
                    rx: sx * t_h,
                    ry: sy * t_h,
                    t_h: t_h,
                    center: {
                        x: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)),
                        y: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2))
                    },
                    cx: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) + sx * t_h,
                    cy: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) - sy * t_h,
                    // cx: sx * t_h,
                    // cy: sy * t_h,
                    rr: this.distributionHeight * .63,
                    id_cnt: pro_cnt++
                };
                // console.log(tp);
                scatterData.push(tp);

            }
            let allScatterData = [];
            if (powIndex == 2 || powIndex == 1) {

            for (let i in pre_data) {
                // console.log(data[i]);
                let sx = (parseFloat(pre_data[i].Holder / (pre_data[i].Holder + pre_data[i].Seller + pre_data[i].Buyer)) + parseFloat(pre_data[i].Buyer) * 2 / (pre_data[i].Holder + pre_data[i].Seller + pre_data[i].Buyer)) / Math.sqrt(3);
                let sy = parseFloat(pre_data[i].Holder / (pre_data[i].Holder + pre_data[i].Seller + pre_data[i].Buyer));
                if (powIndex == 2) {
                    sx = xScale(sx);
                    sy = yScale(sy);
                }
                // if (powIndex != 1) {
                //     if (sx > 0.5) {
                //         // if (cnt % 2 == 0) {
                //         // sx += (1 - ss) * ss * Math.sqrt(3) / 2;
                //         // sy += (1 - ss) * ss / 2;

                //         sx += (ss - Math.atan(ss)) * 12 * Math.sqrt(3) / 2;
                //         sy += (ss - Math.atan(ss)) * 12 * ss / 2;
                //     } else {
                //         // sx -= (1 - sb) * sb * Math.sqrt(3) / 2;
                //         // sy -= (1 - sb) * sb / 2;

                //         sx -= (sb - Math.atan(sb)) * 12 * Math.sqrt(3) / 2;
                //         sy -= (sb - Math.atan(sb)) * 12 * sb / 2;
                //     }
                //     cnt++;
                // }
                // console.log(sx, sy);
                // console.log(data[i])
                let tp = {
                    name: pre_data[i]['Project Name'],
                    data: pre_data[i],
                    group: pre_data[i].Group,
                    x: sx,
                    y: sy,
                    rx: sx * t_h,
                    ry: sy * t_h,
                    t_h: t_h,
                    center: {
                        x: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)),
                        y: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2))
                    },
                    cx: (Math.sin(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) + sx * t_h,
                    cy: (-Math.cos(((240) * Math.PI) / 180) * (this.distributionHeight * .63 / 2)) - sy * t_h,
                    // cx: sx * t_h,
                    // cy: sy * t_h,
                    rr: this.distributionHeight * .63,
                    id_cnt: pro_cnt++
                };
                // console.log(tp);
                allScatterData.push(tp);

            }
            } else {
                allScatterData = scatterData;
            }
            // console.log(scatterData)

            if (powIndex == -1) {
                let center = { x: 0, y: 0 };
                for (let i in scatterData) {
                    center.x += scatterData[i].cx;
                    center.y += scatterData[i].cy;
                }
                center.x /= scatterData.length;
                center.y /= scatterData.length;
                // center.x = scatterData[0].x;
                // center.y = scatterData[0].y;
                let maxLen = 0;
                for (let i in scatterData) {
                    let len = Math.sqrt((scatterData[i].cx - center.x) * (scatterData[i].cx - center.x) + (scatterData[i].cy - center.y) * (scatterData[i].cy - center.y));
                    let lenn = Math.pow(len, 1 / 2)

                    maxLen = Math.max(maxLen, len);
                }
                console.log(maxLen);
                let lenScale = scaleLinear([0, maxLen], [0, 30]);
                for (let i in scatterData) {
                    let len = Math.sqrt((scatterData[i].cx - center.x) * (scatterData[i].cx - center.x) + (scatterData[i].cy - center.y) * (scatterData[i].cy - center.y));
                    
                    if (len != 0) {
                    let lenn = Math.pow(len, 1 / 2)
                    // console.log(lenScale(lenn), scatterData[i].x - center.x)
                        scatterData[i].ax = (scatterData[i].cx - center.x) * lenScale(len);
                        scatterData[i].ay = (scatterData[i].cy - center.y) * lenScale(len);
                    } else {
                        scatterData[i].ax = (scatterData[i].cx - center.x);
                        scatterData[i].ay = (scatterData[i].cy - center.y);
                    }
                    scatterData[i].rx = scatterData[i].ax;
                    scatterData[i].ry = scatterData[i].ay;
                    scatterData[i].cx = scatterData[i].rx;
                    scatterData[i].cy = -scatterData[i].ry;
                    if (scatterData[i].cx == -0) {
                        scatterData[i].cx = 0;
                    }
                    if (scatterData[i].cy == -0) {
                        scatterData[i].cy = 0;
                    }

                }
                console.log(maxLen);
            }
            for (let i in scatterData) {
                let tp = scatterData[i];

                let t_cnt = (Math.acos(tp.cy / (Math.sqrt(Math.pow(tp.cx, 2) + Math.pow(tp.cy, 2)))) / (Math.PI / 180))
                if (tp.cx > 0)
                    t_cnt = 360 - t_cnt - 6;
                else
                    t_cnt = t_cnt - 6;
                t_cnt = (Math.floor(t_cnt / 12) + 31) % 30
                if (isNaN(t_cnt)) t_cnt = 0;
                // if (t_cnt == -1) t_cnt++;
                // console.log(Math.floor(t_cnt));

                let m11 = Math.floor((data[i]['M1'] - min_m1) / (max_m1 - min_m1) / (1 / 5));
                let m22 = Math.floor((data[i]['M2'] - min_m2) / (max_m2 - min_m2) / (1 / 5));
                let m33 = Math.floor((data[i]['M3'] - min_m3) / (max_m3 - min_m3) / (1 / 5));
                let impp = Math.floor((data[i]['IMP'] - min_imp) / (max_imp - min_imp) / (1 / 5));
                m1_max = Math.max(m1_max, m11);
                m2_max = Math.max(m2_max, m22);
                m3_max = Math.max(m3_max, m33);
                imp_max = Math.max(imp_max, impp);
                m11 = m11 == 5 ? m11 - 1 : m11;
                m22 = m22 == 5 ? m22 - 1 : m22;
                m33 = m33 == 5 ? m33 - 1 : m33;
                impp = impp == 5 ? impp - 1 : impp;
                // console.log(tp, t_cnt);
                areaData[Math.floor(t_cnt)].project.push(data[i]);
                areaData[Math.floor(t_cnt)].m1Area[m11]++;
                areaData[Math.floor(t_cnt)].m2Area[m22]++;
                areaData[Math.floor(t_cnt)].m3Area[m33]++;
                // if (i == 10)
                // break;
                areaData[Math.floor(t_cnt)].impArea[impp]++;
            }
            let ayScale = scaleLinear([0, 4], [this.distributionHeight * .63 / 2 + 10, this.distributionHeight * .71 / 2 ]);
            let m1Scale = scaleLinear([0, m1_max], [0, 4]);
            let m2Scale = scaleLinear([0, m2_max], [0, 4]);
            let m3Scale = scaleLinear([0, m3_max], [0, 4]);
            let impScale = scaleLinear([0, imp_max], [0, 4]);
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
                    impd: ag4(areaData[i].impArea),
                    cnt: areaData[i].project.length
                });
                // if (i == 2)
                // break;
            }


            // return [scatterData, res_area];
            return [allScatterData, res_area];
        },
        mainDataProcess() {
            let arcs = pie().padAngle(0.005)(this.monthStep);
            let innerArc = [];
            let innerData = [];
            for (let i = 0; i < 30; i++) {
                innerData.push(20);
            }
            let innerArcData = pie().padAngle(0.007)(innerData);
            // let cnt = 0;
            for (let d of innerArcData) {
                d.innerRadius = this.distributionHeight * .71 / 2 + 5;
                d.outerRadius = this.distributionHeight * .63 / 2 + 7;
                let darcs = arc()(d);
                innerArc.push(darcs);
                // // break
                // cnt++;
                // if (cnt == 2) break;
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
        outerArcProgress: function(data) {
            let group = {};
            let maxGroup = 0;
            for (let i in data) {
                if (typeof(group[data[i].Group]) == 'undefined') {
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
                group[data[i].Group].len.push(parseInt(data[i].Holder));
            }
            this.all_group_num = maxGroup + 1;
            let all_group_array = [];
            for (let i = 0; i < maxGroup + 1; i++) {
                all_group_array.push(i);
            }
            this.all_group_array = all_group_array;
            // console.log(data.length)
            if (data.length < 70) {
                group[maxGroup + 1] = {
                    sum_len: 70 - data.length,
                    len: [data.length],
                    group: maxGroup + 1,
                    project: [{
                        Holder: data.length
                    }]
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
            let allGroupArc = [];
            for (let d of outerArcData) {
                // console.log(d)
                let all_group = []
                let darcs = arc().innerRadius(this.distributionHeight * 0.99 / 2 - 5).outerRadius(this.distributionHeight * 0.99 / 2).cornerRadius(3)(d);
                outerArc.push({ d: darcs, group: d.data.group });
                all_group.push({
                    group: d.data.group,
                    arc: darcs,
                    tag: 0
                })

                let groupArcData = pie().padAngle(0.005).startAngle(d.startAngle).endAngle(d.endAngle).value(d => d.Holder)(d.data.project.sort((a, b) => b.Holder - a.Holder));
                for (let g of groupArcData) {
                    // console.log(g);
                    let gArcs = arc().innerRadius(this.distributionHeight * 0.98 / 2 - 25).outerRadius(this.distributionHeight * 0.98 / 2 - 5)(g);
                    groupArc.push({
                        group: d.data.group,
                        arc: gArcs,
                        project: g.data
                    });
                    all_group.push({
                        group: d.data.group,
                        arc: gArcs,
                        tag: '1'
                    });
                }
                allGroupArc.push(all_group);
            }
            // console.log(groupArc);
            return [outerArc, groupArc, allGroupArc];
        }
    },
    created() {},
    mounted() {
        this.elWidth = this.$refs.distributionView.offsetWidth;
        this.distributionHeight = this.$refs.distributionView.offsetHeight;

        // console.log(this.elWidth);


        const dataStore = useDataStore();

        
        // this.showTag = 1;
        // this.cpData = cpData;
        // // this.showTag = 1;
        //         // this.cpData = dataStore.allData.cpData;

        //         let max_m1 = 0,
        //             max_m2 = 0,
        //             max_m3 = 0,
        //             max_imp = 0;
        //         let min_m1 = 99999,  
        //             min_m2 = 99999,
        //             min_m3 = 99999,
        //             min_imp = 99999;
        //         let data33 = this.cpData.data;
        //         for (let i in data33) {
        //             max_m1 = Math.max(max_m1, data33[i].M1)
        //             max_m2 = Math.max(max_m2, data33[i].M2)
        //             max_m3 = Math.max(max_m3, data33[i].M3)
        //             max_imp = Math.max(max_imp, data33[i].IMP);
        //             min_m1 = Math.min(min_m1, data33[i].M1);
        //             min_m2 = Math.min(min_m2, data33[i].M2);
        //             min_m3 = Math.min(min_m3, data33[i].M3);
        //             min_imp = Math.min(min_imp, data33[i].IMP);
        //         }
        //         this.valueRange = {
        //             m1: [min_m1, max_m1],
        //             m2: [min_m2, max_m2],
        //             m3: [min_m3, max_m3],
        //             imp: [min_imp, max_imp]
        //         }
        // // console.log(this.cpData);
        // this.allProject_num = this.cpData.data.length;
        // let timeRange = dataStore.timeRange;
        // // console.log(timeRange);

        // this.monthArc = this.calcArc(timeRange);
        // [this.mainArc, this.mainInnerArc, this.innerArc] = this.mainDataProcess();
        // // console.log(this.innerArc)
        // // console.log(this.cpData);
        // [this.outerArc, this.groupArc, this.allGroupArc] = this.outerArcProgress(this.cpData.data);
        // [this.scatterData, this.innerArea] = this.calcScatter(this.cpData.data, 1, this.projectSelect);

        // console.log(this.projectFlow);
        dataStore.$subscribe((mutations, state) => {
            if (dataStore.allData.tag == 1) {
                this.showTag = 1;
                this.cpData = dataStore.allData.cpData;
                this.flow_data = dataStore.allData.flow_data;

                let max_m1 = 0,
                    max_m2 = 0,
                    max_m3 = 0,
                    max_imp = 0;
                let min_m1 = 99999,
                    min_m2 = 99999,
                    min_m3 = 99999,
                    min_imp = 99999;
                let data33 = this.cpData.data;
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
                this.valueRange = {
                    m1: [min_m1, max_m1],
                    m2: [min_m2, max_m2],
                    m3: [min_m3, max_m3],
                    imp: [min_imp, max_imp]
                }
                this.allProject_num = dataStore.allData.cpData.data.length;
                let timeRange = dataStore.timeRange;
                this.monthArc = this.calcArc(timeRange);
                [this.mainArc, this.mainInnerArc, this.innerArc] = this.mainDataProcess();
                [this.outerArc, this.groupArc, this.allGroupArc] = this.outerArcProgress(dataStore.allData.cpData.data);
                [this.scatterData, this.innerArea] = this.calcScatter(dataStore.allData.cpData.data, 1, this.projectSelect);

            }
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

.tooltip {
    /* background-color: gray; */
    /* height: 70px; */
    /* position: relative;
  width: 150px; */
    /* border-radius: 15px; */
}

/*chrome--------------------------------------------end*/
</style>
