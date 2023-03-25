<template>
    <div style="height: 100%;">
        <div class="frameworkTitle">
    
            <span class="title">
                                <svg t="1676053010318" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
                                    p-id="11810" width="20" height="20">
                                    <path
                                        d="M860.444444 298.666667h-384c-66.659556 0-120.888889-54.229333-120.888888-120.888889S409.784889 56.888889 476.444444 56.888889h384c66.659556 0 120.888889 54.229333 120.888889 120.888889S927.104 298.666667 860.444444 298.666667z m-384-184.888889c-35.285333 0-64 28.714667-64 64s28.714667 64 64 64h384c35.285333 0 64-28.714667 64-64S895.729778 113.777778 860.444444 113.777778h-384zM860.444444 967.111111h-384c-66.659556 0-120.888889-54.229333-120.888888-120.888889s54.229333-120.888889 120.888888-120.888889h384c66.659556 0 120.888889 54.229333 120.888889 120.888889S927.104 967.111111 860.444444 967.111111z m-384-184.888889c-35.285333 0-64 28.714667-64 64s28.714667 64 64 64h384c35.285333 0 64-28.714667 64-64S895.729778 782.222222 860.444444 782.222222h-384zM860.444444 640h-384c-66.659556 0-120.888889-54.229333-120.888888-120.888889s54.229333-120.888889 120.888888-120.888889h384c66.659556 0 120.888889 54.229333 120.888889 120.888889S927.104 640 860.444444 640z m-384-184.888889c-35.285333 0-64 28.714667-64 64s28.714667 64 64 64h384c35.285333 0 64-28.714667 64-64S895.729778 455.111111 860.444444 455.111111h-384z"
                                        p-id="11811" fill="#534f4f"></path>
                                    <path
                                        d="M177.777778 298.666667h-14.222222C96.896 298.666667 42.666667 244.437333 42.666667 177.777778S96.896 56.888889 163.555556 56.888889h14.222222c66.659556 0 120.888889 54.229333 120.888889 120.888889S244.437333 298.666667 177.777778 298.666667z m-14.222222-184.888889C128.270222 113.777778 99.555556 142.492444 99.555556 177.777778S128.270222 241.777778 163.555556 241.777778h14.222222c35.285333 0 64-28.714667 64-64S213.063111 113.777778 177.777778 113.777778h-14.222222zM177.777778 967.111111h-14.222222C96.896 967.111111 42.666667 912.881778 42.666667 846.222222S96.896 725.333333 163.555556 725.333333h14.222222c66.659556 0 120.888889 54.229333 120.888889 120.888889S244.437333 967.111111 177.777778 967.111111z m-14.222222-184.888889C128.270222 782.222222 99.555556 810.936889 99.555556 846.222222S128.270222 910.222222 163.555556 910.222222h14.222222c35.285333 0 64-28.714667 64-64S213.063111 782.222222 177.777778 782.222222h-14.222222zM177.777778 640h-14.222222C96.896 640 42.666667 585.770667 42.666667 519.111111S96.896 398.222222 163.555556 398.222222h14.222222c66.659556 0 120.888889 54.229333 120.888889 120.888889S244.437333 640 177.777778 640z m-14.222222-184.888889C128.270222 455.111111 99.555556 483.825778 99.555556 519.111111S128.270222 583.111111 163.555556 583.111111h14.222222c35.285333 0 64-28.714667 64-64S213.063111 455.111111 177.777778 455.111111h-14.222222z"
                                        p-id="11812" fill="#534f4f"></path>
                                </svg>
                
                                &nbsp; <span style="position: relative; top: 0px; font-weight: 600;">Propensity
                                    Analysis</span></span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
        </div>
        <div class="frameworkBody" id="controlPanel" ref="controlPanel">
            <div style="margin-top: 5px; height: calc(31% + 15px);">
                <div>[Control Panel]</div>
                <div style="font-size: 14px;">
                    <div>
                        <span style="position: relative; top: 4px;">TIME SLICE</span>
                        <span style="float: right; width: 65%;">
                                            <el-date-picker v-model="selectSlice" type="daterange" range-separator="To"
                                                start-placeholder="Start date" end-placeholder="End date" style="width: 100%"
                                                :default-value="new Date(2021, 5, 1)" />
                                        </span>
    
                    </div>
                    <div style="margin-top: 15px;">
                        <span style="position: relative; top: 4px;">ATTRIBUTES</span>

                        <span style="position: absolute; top: 158px; left: 0px">GROUPING BY</span>
                        <span style="float: right; width: 65%;">
                                            <div style="height: 25px;">
                                                <span style="position: relative; left: 0px;">
                                                    <el-checkbox v-model="formData.checked0" label="Ave Price" />
                                                </span>
                        <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-checkbox v-model="formData.checked1" label="Floor Price" />
                                                </span>
                    </div>

                    <div style="height: 25px;">
                        <span style="position: relative; left: 0px;">
                                                    <el-checkbox v-model="formData.checked2" label="Sales Volumes" />
                                                </span>
                        <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-checkbox v-model="formData.checked3" label="Liquidity" />
                                                </span>
                    </div>
                    <div style="height: 25px;">
                        <span style="position: relative; left: 0px;">
                                                    <el-checkbox v-model="formData.checked4" label="ETH_Volume" />
                                                </span>
                        <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-checkbox v-model="formData.checked5" label="Num_Holders" />
                                                </span>
                    </div>
                    <div style="height: 25px;">
                        <span style="position: relative; left: 0px;">
                                                    <el-checkbox v-model="formData.checked6" label="Num_Buyers" />
                                                </span>
                        <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-checkbox v-model="formData.checked7" label="Num_Sellers" />
                                                </span>
                    </div>
                    <div style="height: 25px;">
                        <span style="position: relative; left: 0px;">
                                                    <el-checkbox v-model="formData.checked8" label="Num_Whales" />
                                                </span>
                        <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-checkbox v-model="formData.checked9" label="Num_Transfers" />
                                                </span>
                    </div>
                    <div style="height: 25px;">
                        <span style="position: relative; left: 0px;">
                                                    <el-checkbox v-model="formData.checked10" label="Social Popularity" />
                                                </span>
                        <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-checkbox v-model="formData.checked11" label="Social Polarity" />
                                                </span>
                    </div>
                    <div style="height: 25px; margin-top: 3px;">

                        <span style="position: relative; left: 0px;">

                            <el-radio-group v-model="clusterRadio" class="ml-4">
                            <el-radio label="1" style="position: absolute;">Gaussian Mixture Model</el-radio>
                                                <!-- </span>
                        <span style="position: absolute; left: calc(51% + 20px);"> -->
                                                    
                            <el-radio label="2" style="position: absolute; left: 185px;">K-Means</el-radio>
                                            </el-radio-group>
                                                </span>
                    </div>
                    <div style="height: 25px; margin-top: 0px;">

<span style="position: relative; left: 0px;">
                        </span>
<span style="position: absolute; left: calc(51% + 20px);">
                            
    GROUP
                                        <el-select v-model="groupValue" class="m-2" placeholder="Select"
                                            style="width: 30px; --el-border-color: white;">
                                            <el-option v-for="item in groupOptions" :key="item" :label="item" :value="item" />
                                        </el-select>
                                    </span>
</div>
                    </span>
                </div>
    
                <div>
                    <span style="float: right; width: 65%; margin-bottom: 5px; margin-top: 2px;">
                                            <div>
                                                <span style="position: relative; left: 0px;">
                                                    <el-button style="width:100px" @click="run()">RUN</el-button>
                                                </span>
                    <span style="position: absolute; left: calc(51% + 20px);">
                                                    <el-button style="width: 100px">CLEAR</el-button>
                                                </span>
                </div>
                </span>
            </div>
        </div>
    </div>
    <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
    <div style="font-size: 14px; margin-top: 5px; height: calc(10% + 0px);">
        <div style="margin-top: 0px;">
            <span style="color: #ABACBE;">
                                        Showing <span class="php">{{ select_project_num }} projects</span> from 70 results
            </span>
            <!-- <span style="float: right; position: relative; top: -4px;">
                                        Group
                                        <el-select v-model="groupValue" class="m-2" placeholder="Select"
                                            style="width: 30px; --el-border-color: white;">
                                            <el-option v-for="item in groupOptions" :key="item" :label="item" :value="item" />
                                        </el-select>
                                    </span> -->
        </div>
        <!-- <div> -->
            <!--<div style="height: 25px; margin-top: 5px;">
    
                <!~~ <span style="float: left; position: relative; top: 0px;">
                
                                            Grouping by:
                    <span style="position: absolute; left: 100px; top: -4px;">
                                                <el-radio-group v-model="clusterRadio" class="ml-4">
                                                    <el-radio label="1" style="position: absolute;">Gaussian Mixture Model</el-radio>
                                                    <el-radio label="2" style="position: absolute; left: 200px;">K-Means</el-radio>
                                                </el-radio-group>
                                            </span>
                </span> ~~>
            </div>-->
        <!-- </div> -->
        <div style="margin-top: 5px;">
            <span>
                                        Recency scale:
                                        <span>
                                            <svg width="160" height="12" transform="translate(0,1)">
                                                <rect v-for="(item, i) in colormap" :key="'lr' + i" :x="0 + i * 20" :y="0" :height="12"
                                                    :width="20" :fill="item"></rect>
                                            </svg>
                                        </span>
            </span>
        </div>
        <div style="margin-top: 7px;">
            <!-- <span style="">
                                        Probability: [70%-95%]
                                    </span> -->
            <span style="float: left; position: relative; top: -4px;">
                                        Rank by:
                                        <el-select v-model="rankValue" class="m-2" placeholder="Select"
                                            style="width: 130px; --el-border-color: white;">
                                            <el-option v-for="item in rankOptions" :key="item" :label="item.label" :value="item.value" />
                                        </el-select>
                                    </span>
            <span style="float: right; position: relative; top: -4px;">
                                        Filter:
                                        <el-select v-model="attributeValue" class="m-2" placeholder="Select"
                                            style="width: 130px; --el-border-color: white;">
                                            <el-option v-for="item in attributeOption" :key="item" :label="item.label"
                                                :value="item.value" />
                                        </el-select>
                                    </span>
        </div>
    </div>
    <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#c6bcbc SIZE=2>
    <div style="overflow-y: auto; height: calc(50% - 10px); margin-top: 10px; margin-bottom: 10px;">
        <el-table class="customer-no-border-table" :data="tableData" :show-header="false" style="height: calc(100% + 0px); width: 100%;" :row-style="{
                                        height: elHeight / 6 + 'px',
                                        'font-size': '14px',
                                        border: '0px'
                                    }">
            <el-table-column type="expand" width="25" fixed>
                <template #default="props">
                                            <div m="4">
                                                <div style="margin-left: 112px; height: 120px;">
                                                    <svg height="100%" :width="elWidth - 24">
                                                        <g v-for="(item, i) in props.row.group" :key="'plg' + i">
                                                            <!-- <g v-for="(l_item, l_i) in item.line" :key="'pllg' + l_i"> -->
                                                            <path :d="item.line[attributeValue].d" :class="item.line[attributeValue].class" :id="item.line[attributeValue].id" :fill="'none'" :stroke="item.line[attributeValue].color"></path>
                                                            <!-- </g> -->
                
                                                        </g>
                                                    </svg>
                                                </div>
                                            </div>
</template>
                    </el-table-column>
                    <el-table-column label="Date" prop="groupNum" width="75" fixed />
                    <el-table-column label="Name" :width="410">
<template #default="scope">
    <div class="tableRow" :style="{
                                                height: (elHeight / 6 - 16) + 'px',
                                                width: '100%',
                                                'overflow-x': 'auto',
                                                overflowY: 'hidden'
                                            }">
        <svg :width="scope.row.group.length * (elWidth / 6)" height="100%">
                                                    <g v-for="(item, i) in scope.row.group" :key="'glyP' + i"
                                                        :transform="translate(i * elWidth / 6, 0, 0)">
                                                        <g :transform="translate(elWidth / 12, (elHeight / 6 - 16) / 2, 0)">
                                                            <path v-for="(a_item, a_i) in item.outStroke" :key="'corr_out_' + a_i"
                                                                :d="a_item.d" :fill="'none'" :stroke="'#534f4f'"></path>
                                                            <path v-for="(a_item, a_i) in item.outArc" :key="'corr_out_' + a_i"
                                                                :d="a_item.d" :fill="a_item.fill" :stroke="a_item.fill"></path>
                                                            <path v-for="(a_item, a_i) in item.innerArc" :key="'corr_out_' + a_i"
                                                                :d="a_item.d" :fill="a_item.fill"></path>
                
                                                            <clipPath id="clipPath3">
                                                                <circle :cx="item.img_r" :cy="item.img_r" :r="item.img_r">
                                                                </circle>
                                                            </clipPath>
                                                            <g clip-path="url(#clipPath3)"
                                                                :transform="translate(-item.img_r, -item.img_r, 0)">
                                                                <image :href="item.link" x="0" y="0" :height="item.img_r * 2"
                                                                    :width="item.img_r * 2"  @mouseenter="overGlyph(item.line[attributeValue].id, item.line[attributeValue].class, item.line[attributeValue].color)" @mouseout="outGlyph(item.line[attributeValue].group)" />
                                                            </g>
                                                        </g>
                
                                                    </g>
                                                </svg>
    </div>
</template>
                    </el-table-column>
                </el-table>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3); margin-top: -10px;" width="100%" color=#c6bcbc
                SIZE=2>
            <div style="height: 6%;">
                <div style="margin-top: 10px; float: left;">
                    Unreleased projects:
                </div>
                <div style="overflow-x: auto; overflow-y: hidden; height: 100%;">
                    <img v-for="(item, i) in unreleasedProject" :src="item.logo_link" :style="{
                        position: 'absolute',
                        top: '6px', left: (i * 40 + 10) + 'px',
                        'border-radius': '50%'
                    }" height="35" >
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { arc, line, pie } from 'd3-shape';
import { scaleLinear } from 'd3-scale';
import { useDataStore } from "../stores/counter";
import { extent, max, min } from 'd3-array';
import { interpolateViridis } from 'd3';
import { select, selectAll } from 'd3-selection';
// import star from 'd3-shape/src/symbol/star';

export default {
    name: 'APP',
    props: [],
    data() {
        return {
            elHeight: 100,
            elWidth: 100,
            select_project_num: 0,
            formData: {
                checked0: false,
                checked1: false,
                checked2: false,
                checked3: false,
                checked4: false,
                checked5: false,
                checked6: false,
                checked7: false,
                checked8: false,
                checked9: false,
                checked10: false,
                checked11: false,
            },
            clusterRadio: '0',
            selectSlice: [],
            unreleasedProject: [],
            groupValue: 6,
            groupOptions: [1, 2, 3, 4, 5, 6],
            attributeOption: [],
            attributeValue: '',
            rankValue: 'M3',
            rankOptions: [{ label: 'Recency', value: 'M1' }, { label: 'Preferential attachment', value: 'M2' }, { label: 'Propensity', value: 'M3' }, { label: 'Impact dynamic', value: 'IMP' }],
            // colormap: ['#440154', '#46327e', '#365c8d', '#277f8e', '#1fa187', '#4ac16d', '#a0da39', '#fde725'],
            colormap: ["#f6cba2", "#f2b67d", "#eea158", "#eb8c33", "#e98120", "#d7771d", "#b46318", "#905014"],

            axisColor: { 'M1': '#EA7C16', 'M3': '#61bad6', 'IMP': '#d77a78', 'M2': '#53ad92' },
            tableData: [],
            colorType: {
                seller: '#b69acb',
                buyer: '#6f319b',
                holder: '#c9c9c9'
            },
            monthName: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'],
            attributeMap: {
                'polarity': 'Social Polarity',
                'popularity': 'Social Popularity',
                'floor_price': 'Floor Price',
                'average_price': 'Ave Price',
                'eth_volume': 'ETH_Volume',
                'whale_num': 'Num_Whales',
                'holder_num': 'Num_Holders',
                'buyer_num': 'Num_Buyers',
                'seller_num': 'Num_Sellers',
                'transfer_num': 'Num_Transfers',
                'liquidity': 'Liquidity',
                'ales': 'Sales Volume'
            },
            maxGroupNum: 0,
            selectMonth: -1
        }
    },
    methods: {
        run() {
            const dataStore = useDataStore();

            let selectMonth = this.selectMonth;
            let importData = '';
            let selectFile = 0;
            if (selectMonth == 1) {
                selectFile = 1;
                importData =
                    import.meta.globEager('../assets/NFT_data/1/*.json');
            }
            if (selectMonth == 4) {
                selectFile = 1;
                importData =
                    import.meta.globEager('../assets/NFT_data/4/*.json');
            }
            if (selectMonth == 7) {
                selectFile = 1;
                importData =
                    import.meta.globEager('../assets/NFT_data/7/*.json');
            }
            if (selectMonth == 8) {
                selectFile = 1;
                importData =
                    import.meta.globEager('../assets/NFT_data/8/*.json');
            }
            if (selectMonth == 12) {
                selectFile = 1;
                importData =
                    import.meta.globEager('../assets/NFT_data/12/*.json');
            }
            // console.log(importData)
            // let multiDataSet = []
            if (selectFile == 1) {
                let file_cnt = 0;
                for (let i in importData) {
                    if (file_cnt == 0) {
                        dataStore.allData.cpData = importData[i]['default'];
                    } else if (file_cnt == 1) {
                        dataStore.allData.projectData = importData[i]['default'];
                    } else if (file_cnt == 2) {
                        dataStore.allData.data = importData[i]['default'];
                    } else if (file_cnt == 3) {
                        dataStore.allData.flow_data = importData[i]['default'];
                    }
                    file_cnt++;
                    // multiDataSet.push(importData[i]['default'])
                    // console.log(importData[i], i)
                }
                dataStore.allData.tag = 1;

                this.tableData = this.calcTable(dataStore.allData.cpData.data);
                this.unreleasedProject = this.calcUnreleasedProject(dataStore.allData.cpData.unClusterProject);
            }
        },
        overGlyph(sel_id, sel_class, sel_color) {
            selectAll('.' + sel_class).attr('stroke', '#777').attr('opacity', 0.1);
            select('#' + sel_id).attr('stroke', sel_color).attr('opacity', 1)
        },
        outGlyph(cnt) {
            for (let i in this.tableData[cnt].group) {
                select('#' + this.tableData[cnt].group[i].line[this.attributeValue].id).attr('stroke', this.tableData[cnt].group[i].line[this.attributeValue].color).attr('opacity', 1)
            }
        },
        translate(x, y, deg) {
            return `translate(${x}, ${y}) rotate(${deg})`;
        },
        calcUnreleasedProject(data) {
            let res_data = [];
            for (let i in data) {
                res_data.push(data[i]);
            }
            return res_data;
        },
        calcTable(data) {
            this.select_project_num = data.length;
            // console.log(data[0])
            let lineDataRange = {};
            for (let i in data[0].attributeLine) {
                lineDataRange[i] = [];
                this.attributeOption.push({ label: this.attributeMap[i], value: i });
            }
            this.attributeValue = this.attributeOption[0].value;
            // console.log(this.attributeValue);

            let group = {};
            let max_m1 = 0,
                max_m2 = 0,
                max_m3 = 0,
                max_imp = 0;
            let min_m1 = 99999,
                min_m2 = 99999,
                min_m3 = 99999,
                min_imp = 99999;
            for (let i in data) {
                if (typeof(group[data[i].Group]) === 'undefined') {
                    group[data[i].Group] = {
                        project: [],
                        group: [],
                        groupNum: 'Group ' + data[i].Group.toString()
                    };
                }
                max_m1 = Math.max(max_m1, data[i].M1)
                max_m2 = Math.max(max_m2, data[i].M2)
                max_m3 = Math.max(max_m3, data[i].M3)
                max_imp = Math.max(max_imp, data[i].IMP);
                min_m1 = Math.min(min_m1, data[i].M1);
                min_m2 = Math.min(min_m2, data[i].M2);
                min_m3 = Math.min(min_m3, data[i].M3);
                min_imp = Math.min(min_imp, data[i].IMP);
                group[data[i].Group].project.push(data[i]);
                this.maxGroupNum = Math.max(this.maxGroupNum, group[data[i].Group].project.length);
            }
            // for (let i in data) {
            //     max_imp = Math.max(max_imp, ((data[i].M1- min_m1) / (max_m1 - min_m1)) * ((data[i].M2 - min_m2) / (max_m2 - min_m2)) * ((data[i].M3 - min_m3) / (max_m3 - min_m3)) * data[i].Holder);
            //     min_imp = Math.min(min_imp, ((data[i].M1- min_m1) / (max_m1 - min_m1)) * ((data[i].M2 - min_m2) / (max_m2 - min_m2)) * ((data[i].M3 - min_m3) / (max_m3 - min_m3)) * data[i].Holder);
            // }

            for (let i in group) {
                for (let j in group[i].project) {
                    // console.log(group[i].project[j]);
                    group[i].group.push(this.calcIndividual({
                        inner: {
                            holder: group[i].project[j].Holder,
                            buyer: group[i].project[j].Buyer,
                            seller: group[i].project[j].Seller
                        },
                        outer: {
                            M1: (group[i].project[j].M1 - min_m1) / (max_m1 - min_m1),
                            M2: (group[i].project[j].M2 - min_m2) / (max_m2 - min_m2),
                            M3: (group[i].project[j].M3 - min_m3) / (max_m3 - min_m3),
                            IMP: (group[i].project[j].IMP - min_imp) / (max_imp - min_imp)
                            // IMP: ((group[i].project[j].M1 - min_m1) / (max_m1 - min_m1) * (group[i].project[j].M2 - min_m2) / (max_m2 - min_m2) * (group[i].project[j].M3 - min_m3) / (max_m3 - min_m3) * group[i].project[j].Holder - min_imp) / (max_imp - min_imp)
                        },
                        link: group[i].project[j]['logo_link'] == 'https://storage.opensea.io/files/397bdae98431df0a88659333a82a8c89.jpg' ? 'https://i.seadn.io/gae/ZRDm3mVwUwMPyfx3NzXJG-Vq1vt9YCVMcnTLiXkRLqBAFBNUxPp0MRjstkHi_59M3FLpOm7LPTBbPzDFNpg_wN-C0hk356TyGICRJQ?auto=format&w=384' : group[i].project[j]['logo_link'],
                        name: group[i].project[j]['Project Name'],
                        time: 'Jan. 20 - Feb. 05'
                    }, (this.elHeight / 6 - 16) * 0.9 / 2, 0, 0))
                }
                // console.log(group[i].group);
                for (let j in lineDataRange) {
                    lineDataRange[j] = [0, 0, 0];
                }
                for (let j in group[i].group) {
                    // console.log(group[i].project[j]);
                    group[i].group[j]['attributeLine'] = group[i].project[j]['attributeLine'];
                    for (let k in group[i].project[j]['attributeLine']) {
                        lineDataRange[k][0] = Math.min(lineDataRange[k][0], min(group[i].project[j]['attributeLine'][k], d => d.value));
                        lineDataRange[k][1] = Math.max(lineDataRange[k][1], max(group[i].project[j]['attributeLine'][k], d => d.value));
                        lineDataRange[k][2] = Math.max(lineDataRange[k][2], group[i].project[j]['attributeLine'][k].length);
                        // console.log(lineDataRange)
                    }
                    // group[i].group[j]['line'] = {};
                    // group[i].group[j]['line']['data'] = [];
                    // for (let k = 0; k < 12; ++k)
                    //     group[i].group[j]['line']['data'].push(Math.random());
                    // group[i].group[j]['line']['d'] = lineGenerate(group[i].group[j]['line']['data']);
                }
                let colorScale = interpolateViridis;
                for (let j in group[i].group) {
                    group[i].group[j]['line'] = {};
                    for (let k in group[i].group[j]['attributeLine']) {
                        let xScale = scaleLinear([0, lineDataRange[k][2] - 1], [0, this.elWidth]);
                        let yScale = scaleLinear([lineDataRange[k][0], lineDataRange[k][1]], [100, 0]);
                        let lineGenerate = line().x((d, i) => xScale(i)).y((d) => yScale(d.value));
                        group[i].group[j]['line'][k] = {
                            d: lineGenerate(group[i].group[j]['attributeLine'][k]),
                            color: this.colormap[Math.floor((group[i].group[j].M1 * 8) == 8 ? 7 : Math.floor((group[i].group[j].M1 * 8)))],
                            id: 'sel' + j + '_' + i,
                            class: 'group' + i,
                            group: i
                        }
                    }
                }
            }
            // console.log(group);
            let res_data = [];
            console.log(group);
            for (let i in group) {
                group[i].group.sort((a, b) => {
                    return b.M3 - a.M3
                });

                res_data.push(group[i]);
            }
            // console.log(res_data);
            return res_data;
        },

        calcIndividual(data, r, x, y) {
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
                    d: arc().innerRadius(0).outerRadius(r - 6)(pieData[i]),
                    fill: this.colorType[pieData[i].data.type]
                })
            }
            let outArc = [];
            let angle = 45;
            let colorScale = scaleLinear([-1, 1], [0, 10]);
            let cnt = 0;
            let cOrder = ['M1', 'M3', 'IMP', 'M2'];
            let outStroke = [];
            // console.log(data);
            for (let i in cOrder) {
                outStroke.push({
                    d: arc().innerRadius(r - 4).outerRadius(r)({
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
                outArc.push({
                    d: arc().innerRadius(r - 3).outerRadius(r)({
                        startAngle: ((cnt * 90) - 90) * Math.PI / 180,
                        endAngle: ((cnt * 90) - 90 + data.outer[cOrder[i]] * 90) * Math.PI / 180,
                        index: cnt,
                        padAngle: 0,
                        value: 1
                    }),
                    fill: this.axisColor[cOrder[i]],
                    type: i,
                    stroke: 0
                });
            }
            return {
                x: x,
                y: y,
                outArc: outArc,
                outStroke: outStroke,
                innerArc: innerArc,
                link: data.link,
                img_r: r / 2,
                name: data.name,
                time: data.time,
                data: data,
                M1: data.outer.M1,
                M2: data.outer.M2,
                M3: data.outer.M3,
                IMP: data.outer.IMP
            }
        },
    },
    created() {},
    mounted() {
        // console.log(this.groupData);
        // console.log(this.cpData)
        this.elHeight = this.$refs.controlPanel.offsetHeight * 0.50;
        this.elWidth = this.$refs.controlPanel.offsetWidth - 112;

        // this.tableData = this.calcTable(this.cpData.data);
        // this.unreleasedProject = this.calcUnreleasedProject(this.cpData.unClusterProject);
    },
    watch: {
        rankValue: {
            handler: function(newVal, oldVal) {
                console.log(newVal, oldVal);
                console.log(this.tableData);
                for (let i in this.tableData) {
                    this.tableData[i].group.sort((a, b) => {
                        return b[newVal] - a[newVal];
                    })
                }
            },
            deep: true
        },
        selectSlice: {
            handler: function(newVal, oldVal) {
                console.log(newVal[0].getUTCDate(), newVal[0].getUTCMonth(), newVal[0].getUTCFullYear(), newVal);
                let startDate = newVal[0];
                let endDate = newVal[1];
                const dataStore = useDataStore();
                let selectMonth = startDate.getUTCMonth() + 1;
                this.selectMonth = selectMonth;
                let timeSelection = {
                    'start_time': startDate.getUTCFullYear() + '-' + (startDate.getUTCMonth() + 1) + '-' + (startDate.getUTCDate() + 1),
                    'end_time': endDate.getUTCFullYear() + '-' + (endDate.getUTCMonth() + 1) + '-' + (endDate.getUTCDate() + 1),
                    'start_format': this.monthName[startDate.getUTCMonth()] + '.' + ((startDate.getUTCDate() + 1) >= 10 ? '' : '0') + (startDate.getUTCDate() + 1) + '.' + startDate.getUTCFullYear(),
                    'end_format': this.monthName[endDate.getUTCMonth()] + '.' + (endDate.getUTCDate() + 1) + '.' + endDate.getUTCFullYear(),
                    'start': {
                        day: '',
                        month: '',
                        year: ''
                    },
                    'end': {
                        day: '',
                        month: '',
                        year: ''
                    },
                }
                console.log(timeSelection);
                dataStore.timeRange = timeSelection;

                // dataStore.$subscribe((mutations, state) => {
                //     data
                // })
            }
        }
    }
}
</script>

<style>
.el-radio__label {
    padding-left: 3px;
}

.tableRow::-webkit-scrollbar {
    display: none;
}

.el-table .el-table__cell {
    padding: 0px;
}

.el-checkbox__label {
    padding-left: 3px;
}

.el-button {
    padding-top: 3px;
    padding-bottom: 3px;
}

.php {
    text-decoration: underline;
    color: #534F4F;
}

.el-input__suffix-inner i {
    border: 1px solid #dcdfe6;
}

.el-table__expand-icon i {
    border: 1px solid #dcdfe6;
}

.el-input__inner {
    text-decoration: underline;
}

.el-input__wrapper {
    padding-left: 0px;
    padding-right: 0px;
}

.el-button {
    padding-top: 0px;
    padding-bottom: 0px;
    height: 25px;
}

.el-table th.is-leaf {
    /* 去除上边框*/
    border: none;
}

.el-table::before {
    /* 去除下边框 */
    height: 0;
}

.el-table__row td {
    /* 去除表格线 */
    /* border: 10px solid white; */
}

.el-button {
    border-color: #534F4F;
}

.el-checkbox__inner {
    border-color: #534F4F;
}

.el-radio__inner {
    border-color: #534F4F;
}

el-checkbox__label {
    color: #94a7c7;
}

.el-checkbox {
    --el-checkbox-checked-bg-color: #94a7c7;
    --el-checkbox-checked-input-border-color: #94a7c7;
    --el-checkbox-checked-text-color: #94a7c7;
}

.el-radio__input.is-checked+.el-radio__label {
    color: #94a7c7;
}

.el-radio__input.is-checked .el-radio__inner {
    border-color: #94a7c7;
    background-color: #94a7c7;
}
</style>
