<template>
    <div>
        <div class="frameworkTitle">

            <span class="title">
                <svg t="1676053010318" class="icon" viewBox="0 0 1024 1024" version="1.1"
                    xmlns="http://www.w3.org/2000/svg" p-id="11810" width="20" height="20">
                    <path
                        d="M860.444444 298.666667h-384c-66.659556 0-120.888889-54.229333-120.888888-120.888889S409.784889 56.888889 476.444444 56.888889h384c66.659556 0 120.888889 54.229333 120.888889 120.888889S927.104 298.666667 860.444444 298.666667z m-384-184.888889c-35.285333 0-64 28.714667-64 64s28.714667 64 64 64h384c35.285333 0 64-28.714667 64-64S895.729778 113.777778 860.444444 113.777778h-384zM860.444444 967.111111h-384c-66.659556 0-120.888889-54.229333-120.888888-120.888889s54.229333-120.888889 120.888888-120.888889h384c66.659556 0 120.888889 54.229333 120.888889 120.888889S927.104 967.111111 860.444444 967.111111z m-384-184.888889c-35.285333 0-64 28.714667-64 64s28.714667 64 64 64h384c35.285333 0 64-28.714667 64-64S895.729778 782.222222 860.444444 782.222222h-384zM860.444444 640h-384c-66.659556 0-120.888889-54.229333-120.888888-120.888889s54.229333-120.888889 120.888888-120.888889h384c66.659556 0 120.888889 54.229333 120.888889 120.888889S927.104 640 860.444444 640z m-384-184.888889c-35.285333 0-64 28.714667-64 64s28.714667 64 64 64h384c35.285333 0 64-28.714667 64-64S895.729778 455.111111 860.444444 455.111111h-384z"
                        p-id="11811" fill="#534f4f"></path>
                    <path
                        d="M177.777778 298.666667h-14.222222C96.896 298.666667 42.666667 244.437333 42.666667 177.777778S96.896 56.888889 163.555556 56.888889h14.222222c66.659556 0 120.888889 54.229333 120.888889 120.888889S244.437333 298.666667 177.777778 298.666667z m-14.222222-184.888889C128.270222 113.777778 99.555556 142.492444 99.555556 177.777778S128.270222 241.777778 163.555556 241.777778h14.222222c35.285333 0 64-28.714667 64-64S213.063111 113.777778 177.777778 113.777778h-14.222222zM177.777778 967.111111h-14.222222C96.896 967.111111 42.666667 912.881778 42.666667 846.222222S96.896 725.333333 163.555556 725.333333h14.222222c66.659556 0 120.888889 54.229333 120.888889 120.888889S244.437333 967.111111 177.777778 967.111111z m-14.222222-184.888889C128.270222 782.222222 99.555556 810.936889 99.555556 846.222222S128.270222 910.222222 163.555556 910.222222h14.222222c35.285333 0 64-28.714667 64-64S213.063111 782.222222 177.777778 782.222222h-14.222222zM177.777778 640h-14.222222C96.896 640 42.666667 585.770667 42.666667 519.111111S96.896 398.222222 163.555556 398.222222h14.222222c66.659556 0 120.888889 54.229333 120.888889 120.888889S244.437333 640 177.777778 640z m-14.222222-184.888889C128.270222 455.111111 99.555556 483.825778 99.555556 519.111111S128.270222 583.111111 163.555556 583.111111h14.222222c35.285333 0 64-28.714667 64-64S213.063111 455.111111 177.777778 455.111111h-14.222222z"
                        p-id="11812" fill="#534f4f"></path>
                </svg>

                &nbsp; <span style="position: relative; top: 0px; font-weight: 600;">Propensity
                    Analysis</span></span>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
        </div>
        <div class="frameworkBody">
            <div style="margin-top: 5px;">
                <div>[Contol Panel]</div>
                <div style="font-size: 14px;">
                    <div>
                        <span style="position: relative; top: 4px;">TIME SLICE</span>
                        <span style="float: right; width: 65%;">
                            <el-date-picker v-model="selectSlice" type="monthrange" range-separator="To"
                                start-placeholder="Start month" end-placeholder="End month" style="width: 100%" />
                        </span>

                    </div>
                    <div style="margin-top: 15px;">
                        <span style="position: relative; top: 4px;">ATTRIBUTES</span>
                        <span style="float: right; width: 65%;">
                            <div style="height: 24px;">
                                <span style="position: relative; left: 0px;">
                                    <el-checkbox v-model="formData.checked0" label="Ave Price" />
                                </span>
                                <span style="position: absolute; left: calc(51% + 3px);">
                                    <el-checkbox v-model="formData.checked1" label="Floor Price" />
                                </span>
                            </div>
                            <div style="height: 24px;">
                                <span style="position: relative; left: 0px;">
                                    <el-checkbox v-model="formData.checked2" label="Sales Volumes" />
                                </span>
                                <span style="position: absolute; left: calc(51% + 3px);">
                                    <el-checkbox v-model="formData.checked3" label="Sentiment" />
                                </span>
                            </div>
                            <div style="height: 24px;">
                                <span style="position: relative; left: 0px;">
                                    <el-checkbox v-model="formData.checked4" label="Social Popularity" />
                                </span>
                                <span style="position: absolute; left: calc(51% + 3px);">
                                    <el-checkbox v-model="formData.checked5" label="Num_Holders" />
                                </span>
                            </div>
                            <div style="height: 24px;">
                                <span style="position: relative; left: 0px;">
                                    <el-checkbox v-model="formData.checked6" label="Num_buyers" />
                                </span>
                                <span style="position: absolute; left: calc(51% + 3px);">
                                    <el-checkbox v-model="formData.checked7" label="Liquidity" />
                                </span>
                            </div>
                            <div style="height: 24px;">
                                <span style="position: relative; left: 0px;">
                                    <el-checkbox v-model="formData.checked8" label="Num_Whales" />
                                </span>
                                <span style="position: absolute; left: calc(51% + 3px);">
                                    <el-checkbox v-model="formData.checked9" label="Num_Transfers" />
                                </span>
                            </div>
                        </span>
                    </div>
                    <div>
                        <span style="float: right; width: 65%; margin-bottom: 5px; margin-top: 10px;">
                            <div>
                                <span style="position: relative; left: 0px;">
                                    <el-button style="width:100px">RUN</el-button>
                                </span>
                                <span style="position: absolute; left: calc(51% + 3px);">
                                    <el-button style="width: 100px">CLEAR</el-button>
                                </span>
                            </div>
                        </span>
                    </div>
                </div>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
            <div style="font-size: 14px; margin-top: 5px;">
                <div style="margin-top: 0px;">
                    <span style="color: #ABACBE;">
                        Showing <span class="php">55 projects</span> from 70 results
                    </span>
                    <span style="float: right; position: relative; top: -4px;">
                        Group
                        <el-select v-model="groupValue" class="m-2" placeholder="Select"
                            style="width: 30px; --el-border-color: white;">
                            <el-option v-for="item in groupOptions" :key="item" :label="item" :value="item" />
                        </el-select>
                    </span>
                </div>
                <div>
                    <span>
                        Grouping by: Gaussian Mixed Model
                    </span>
                </div>
                <div>
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
                <div style="margin-top: 0px;">
                    <span style="">
                        Probability: [70%-95%]
                    </span>
                    <span style="float: right; position: relative; top: -4px;">
                        Rank by:
                        <el-select v-model="rankValue" class="m-2" placeholder="Select"
                            style="width: 130px; --el-border-color: white;">
                            <el-option v-for="item in rankOptions" :key="item" :label="item" :value="item" />
                        </el-select>
                    </span>
                </div>
            </div>
            <hr style="FILTER: alpha(opacity=100,finishopacity=0,style=3)" width="100%" color=#e0dede SIZE=1>
        </div>
    </div>
</template>
<script>
export default {
    name: 'APP',
    props: [''],
    data() {
        return {
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
            },
            selectSlice: [],
            groupValue: 6,
            groupOptions: [1, 2, 3, 4, 5, 6],
            rankValue: 'Propensity Value',
            rankOptions: ['Propensity Value'],
            colormap: ['#440154', '#46327e', '#365c8d', '#277f8e', '#1fa187', '#4ac16d', '#a0da39', '#fde725']
        }
    },
    methods: {
    },
    created() {
    },
    mounted() {
    },
}
</script>
<style>
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
</style>
