<template>
    <div style="width: 100%">
        <el-row style="height: 0px; width: 100%; background-color: #8e8e8e">
            <div class="bottom-group">
<!--                <svg :width="iconSize" :height="iconSize" @click="toUnfoldMode"-->
<!--                     t="1630482904247" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"-->
<!--                     p-id="2517">-->
<!--                    <path-->
<!--                            d="M823.7 161.5H561.3v64h190L540.2 436.6l45.2 45.2 212.4-212.4v190h64V199.6c0-21-17.1-38.1-38.1-38.1zM437 544.1L224.6 756.4v-190h-64v259.8c0 21 17.1 38.1 38.1 38.1h262.4v-64h-190l211.1-211.1-45.2-45.1z"-->
<!--                            :fill="unfoldIconColor" p-id="2518"></path>-->
<!--                </svg>-->
<!--                <svg :width="iconSize" :height="iconSize" @click="toFoldMode"-->
<!--                     t="1630482931721" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"-->
<!--                     p-id="2658">-->
<!--                    <path-->
<!--                            d="M867.9 204.1l-45.3-45.3-212.4 212.5v-190h-64v259.9c0 21 17.1 38.1 38.1 38.1h262.5v-64H656.7l211.2-211.2zM442.7 547.8H180.3v64h190L159.2 823l45.3 45.3 212.4-212.4v190h64v-260c-0.1-21-17.2-38.1-38.2-38.1z"-->
<!--                            :fill="foldIconColor" p-id="2659"></path>-->
<!--                </svg>-->
                <svg :width="iconSize" :height="iconSize" @click="clickShowPerf"
                     t="1636033823264" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="998" >
                   <path :fill="showPerformance ?  '#539fff' : '#231815'"
                           d="M213.333333 426.666667h17213.333333v-170.666666z m42.666667 42.666666v85.333334h85.333333v-85.333334H256zM213.333333 213.333333h170.666667v170.666667H213.333333V213.333333z m42.666667 42.666667v85.333333h85.333333V256H256z m170.666667-42.666667h170.666666v170.666667h-170.666666V213.333333z m42.666666 42.666667v85.333333h85.333334V256h-85.333334z m-42.666666 170.666667h170.666666v170.666666h-170.666666v-170.666666z m42.666666 42.666666v85.333334h85.333334v-85.333334h-85.333334z m170.666667-256h170.666667v170.666667h-170.666667V213.333333z m42.666667 42.666667v85.333333h85.333333V256h-85.333333z m-42.666667 170.666667h170.666667v170.666666h-170.666667v-170.666666z m42.666667 42.666666v85.333334h85.333333v-85.333334h-85.333333z m-42.666667 170.666667h170.666667v170.666667h-170.666667v-170.666667z m42.666667 42.666667v85.333333h85.333333v-85.333333h-85.333333z m-256-42.666667h170.666666v170.666667h-170.666666v-170.666667z m42.666666 42.666667v85.333333h85.333334v-85.333333h-85.333334z m-256-42.666667h170.666667v170.666667H213.333333v-170.666667z m42.666667 42.666667v85.333333h85.333333v-85.333333H256z" p-id="5631"></path>
                </svg>
                <svg :width="iconSize" :height="iconSize" @click="clickShowProgress"
                     t="1636033823264" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="998" >
                    <path
                            :fill="showProgress ?  '#539fff' : '#231815'"
                            d="M667 198.3c17.1 0 31.1 14 31.1 31.1s-14 31.1-31.1 31.1H198v-62.2h469m0-70H128v202.2h539c55.8 0 101.1-45.3 101.1-101.1S722.8 128.3 667 128.3zM827.5 480.8c17.1 0 31.1 14 31.1 31.1s-14 31.1-31.1 31.1H198v-62.2h629.5m0-70H128V613h699.5c55.8 0 101.1-45.3 101.1-101.1s-45.3-101.1-101.1-101.1zM475 763.3c17.1 0 31.1 14 31.1 31.1s-14 31.1-31.1 31.1H198v-62.2h277m0-70H128v202.2h347c55.8 0 101.1-45.3 101.1-101.1S530.8 693.3 475 693.3z" p-id="2043"></path>
                </svg>
<!--                <svg :width="iconSize" :height="iconSize" @click="clickShowProgress"-->
<!--                     t="1636033823264" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="998" >-->
<!--                    <path d="M469.333333 85.333333c211.968 0 384 172.032 384 384s-172.032 384-384 384S85.333333 681.301333 85.333333 469.333333 257.365333 85.333333 469.333333 85.333333z m0 682.666667c164.992 0 298.666667-133.674667 298.666667-298.666667 0-165.034667-133.674667-298.666667-298.666667-298.666666-165.034667 0-298.666667 133.632-298.666666 298.666666 0 164.992 133.632 298.666667 298.666666 298.666667z m362.026667 3.029333l120.704 120.661334-60.373333 60.373333-120.661334-120.704 60.330667-60.330667z" fill="#000000" p-id="999">-->
<!--                    </path>-->
<!--                </svg>-->
                <svg :width="iconSize" :height="iconSize" @click="changeShowStepView"
                     t="1630570653155" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"
                     p-id="3778">
                    <path
                            d="M960 160v704H497.312l128.192-352L497.28 160H960zM433.056 160l128.512 352-128.512 352H64V160h369.056zM296.64 346.88H243.36c-2.4 22.08-10.56 39.84-48 39.84v54.72h37.44V704H296.64V346.88z m497.6-4.32h-12.96c-48.96 0-65.28 33.12-65.28 66.72v62.88h60V416.96c0-11.52 2.88-16.32 12-16.32 8.64 0 12 4.8 12 16.32v21.6c0 12.96-0.48 23.04-17.76 51.84l-30.72 50.88-9.28 15.68c-28.48 49.216-33.472 69.184-33.92 105.056V704h161.76v-61.92h-107.04v-4.32c0.416-7.296 4.576-20.416 37.44-63.84l26.72-34.496 8.32-11.104c26.688-34.72 30.56-53.376 31.104-84l0.096-33.12c0-46.08-27.36-68.64-72.48-68.64z"
                            :fill="stepViewIconColor" p-id="3779"></path>
                </svg>
            </div>
        </el-row>
        <el-row v-if="showPerformance">
            <PerformanceMatrix style="left: 5px; width: calc(100% - 10px);"
                               :perData="app.diagnoseMatrix"
                               :app="app"
                               :nodes="nodes"
            ></PerformanceMatrix>
        </el-row>
        <el-row v-show="showProgress" style="height: 100%; width: 100%" >
            <!--            <svg style="height: 100%; width: 100%;" class="tdag-container">-->
            <svg style="height: 300px; width: calc(100% - 10px)" class="tdag-container svgContainer">
                <defs>
                    <linearGradient v-for="[nodeId, colorTicks] in Array.from(colorPropMap.entries())"
                                    :key="nodeId"
                                    :id="'grad-' + app.appName.replace(' ', '-') + '-' + nodeId.replace(' ', '-')"
                                    x1="0" x2="1" y1="0" y2="0">
                        <stop v-for="(colorTick, i) in colorTicks" :key="i"
                              :offset="colorTick.percent + '%'" :stop-color="colorTick.color"/>
                    </linearGradient>
                    <linearGradient :id="'grad-' + app.appName + '-legend'">
                        <stop offset="0%" :stop-color="minTaskNoColor"></stop>
                        <stop offset="100%" :stop-color="maxTaskNoColor"></stop>
                    </linearGradient>
                </defs>
                <g>
                    <g>
                        <g v-if="loaded" class="progressContainer">
                            <VertexProgress  v-for="(node) in nodes" v-bind:key="node.id" :node="node"
                                             :layoutConfig="layoutConfig"
                                             :app="app"
                                             :colorSchema="colorSchema"
                                             :showStepView="showStepView"
                                             :stepNames="stepNames">
                            </VertexProgress>
                            <g class="edgeContainer">
                                <path v-for="({path, edge}, i) in pathModels" :key="i"
                                      :d="path" fill="none"
                                      stroke="rgb(125, 125, 125)"
                                      :stroke-width="getEdgeStrokeWidth(edge)"></path>
                            </g>
                        </g>
                    </g>
                    <g class="timeAxis" transform="translate(0, 20)">
                        <rect y=-20 fill="white" :width="width" height="20" opacity="1"></rect>
                    </g>
                </g>

                <g v-if="!loaded">
                    <text :x="containerWidth/2 - 100" :y="containerHeight/2" font-size="30" opacity="0.3">
                        No data selected
                    </text>
                </g>
                <g class="detailStructure"></g>
                <g class="legend-container-0" v-show="loaded && !showStepView"
                   :transform="'translate(' + [8, containerHeight-20] + ')'">
                    <rect :x="0" :y="2.5"
                          :stroke="'gray'" :stroke-width="0"
                          :width="60" :height="10"
                          :fill="'url(#grad-' + app.appName + '-legend)'"></rect>
                    <text :dx="65" :dy="12">Task No.</text>
                </g>
                <g class="legend-container-1" v-show="loaded && showStepView"
                   :transform="'translate(' + [8, containerHeight-102] + ')'">
                    <rect v-for="(color, i) in layoutConfig.stepColors" :key="'rect-' + i"
                          :x="0" :y="16 * i" rx="2" ry="2"
                          :stroke="color" :stroke-width="1" :fill="color"
                          :width="10" :height="10"></rect>
                    <text v-for="(stepName, i) in stepNames" :key="'label' + i" style="font-size: 12px"
                          :dx="14" :dy="9 + 16 * i">{{stepName}}</text>
                </g>

            </svg>
            <div v-if="!showStepView" style="background-color: #ffffff; justify-content: left; text-align: left;margin-left:5px">
                <el-radio-group v-model="ratioName">
                    <el-radio :label="stepSelector[0]">{{stepSelector[0]}}</el-radio>
                    <el-radio :label="stepSelector[1]">{{stepSelector[1]}}</el-radio>
                    <el-radio :label="stepSelector[2]">{{stepSelector[2]}}</el-radio>
                    <el-radio :label="stepSelector[3]">{{stepSelector[3]}}</el-radio>
                    <el-radio :label="stepSelector[4]">{{stepSelector[4]}}</el-radio>
                    <el-radio :label="stepSelector[5]">{{stepSelector[5]}}</el-radio>
                </el-radio-group>
            </div>
        </el-row>
    </div>
</template>

<script>
/* eslint-disable */
import * as d3 from "d3";
import {mapState} from "vuex";
import {TDAGCursorMode} from "@/utils/const/TDAGCursorMode";
import {Application} from "@/utils/entities/Application";
import VertexProgress from "@/component-element/VertexProgress";
import PerformanceMatrix from "@/components-new/PerformanceMatrix/PerformanceMatrix";
import {arrayFindIndex} from "element-ui/src/utils/util";

const curveGen = d3.line().x(p => p[0]).y(p => p[1]).curve(d3.curveBasis)


// FIXME compute bar color
const colorGen = d3.interpolateBlues


/**
 * @param nodeId
 * @param trend
 * @param timeInterval in ms
 * @param globalMaxCount
 * @returns {{percent:number, color:string}[]}
 */

function generateScale(newXScale) {
    let axis = d3.axisTop(newXScale)
    axis.ticks(15).tickFormat(d => (d) / 1000 + 's').tickSize(3)
    return axis
}

export default {
    name: "TlAggrView",
    props: {
        app: Application
    },
    components: {
        PerformanceMatrix,
        VertexProgress
    },
    data() {
        return {
            iconSize: 18,   // px
            containerWidth: 0,
            containerHeight: 0,
            mergeCount: 0,
            maxMergeCount: 10,
            showStepView: false,
            testTransform: '',
            staticXScaleCopy: undefined,
            newXScale: undefined,
            width: 0,
            zoom: null,
            domain: null,
            stepNames: [
                'Initialization',
                'Input/Shuffle',
                'Processor',
                'Sink',
                'Spill',
            ],
            overallExtend: new Map(),
            showPerformance: false,
            showProgress: true,
            stepSelectorIndex: 0,
            ratioName: "Overall"
        }
    },
    mounted() {
        let width = this.$el.clientWidth;
        let height = this.$el.clientHeight;
        // console.log(width, height, this.$el)
        this.width = width
        this.containerHeight = height;
        this.containerWidth = width;
        this.$store.commit('comparison/updateTDAGScale', {app: this.app, width, height});
    },
    watch: {
        loaded() {
            if (this.loaded == true) {
                let _this = this

                // d3.select('.testCircle').attr('cx', this.newXScale(start))

                // console.log('= d3.min(taskList, task => task.start_time', start, end, (end - start), (end - start) / 1000)

                let width = this.$el.clientWidth;
                let height = this.$el.clientHeight;

                this.svg = d3.select(this.$el).select('.tdag-container');
                this.zoom = d3.zoom()
                    .scaleExtent([-3, 8])
                    .extent([[20, 20], [width - 20, height - 20]])
                    .on('zoom', function () {
                        _this.svg.select('.progressContainer').attr('transform', d3.event.transform);
                        _this.newXScale = d3.event.transform.rescaleX(_this.staticXScaleCopy);
                        _this.updateAxis()
                        _this.$store.commit('comparison/changeTDAGTransform',
                            {app: _this.app, transform: d3.event.transform})
                    });
                this.svg.call(this.zoom);
                this.clusterNumber = this.maxMergeCount = Math.max(1, this.graph.nodes.length)
            }
        },
        tdagTransform() {
            if (!this.tdagTransform) return
            this.svg.select('.progressContainer').attr('transform', this.tdagTransform);
            this.newXScale = this.tdagTransform.rescaleX(this.staticXScaleCopy);
            this.zoom.transform = this.tdagTransform
            this.updateAxis()
        },
        renderAxis() {
            const domain = this.stateXScale.domain()
            let start = d3.min(this.taskList, task => task.start_time)
            let end = d3.max(this.taskList, task => task.end_time)
            domain[0] -= start
            domain[1] -= start
            this.staticXScaleCopy = d3.scaleLinear().domain(domain).range(this.stateXScale.range())
            this.newXScale = d3.scaleLinear().domain(domain).range(this.stateXScale.range())

            this.updateAxis()
        },
        ratioName(){
            this.stepSelectorIndex = this.getIndex(this.stepSelector, this.ratioName)
            this.generateColorPropMap()
        }
    },
    methods: {
        getTrend(taskList) {
            let usage = [];
            let trend = [];
            let count = 0;
            if (this.stepSelectorIndex !== 0){
                taskList.forEach(task => {
                    //TODO modify here
                    usage.push({'type': 'start', 'time': task.step_info[this.stepSelectorIndex * 2 - 2], "taskId":task.task_id});
                    usage.push({'type': 'end', 'time': task.step_info[this.stepSelectorIndex * 2 - 1], "taskId":task.task_id});
                })
            }else{
                taskList.forEach(task => {
                    //TODO modify here
                    usage.push({'type': 'start', 'time': task.start_time, "taskId":task.task_id});
                    usage.push({'type': 'end', 'time': task.end_time, "taskId":task.task_id});
                })
            }
            usage.sort((a, b) => (a.time > b.time) ? 1 : -1);
            let lastTaskId = ""
            usage.forEach(u => {
                if (u.type === 'start') {
                    count += 1;
                }else if (u.type === 'end') {
                    count -= 1;
                } else{
                    console.log('error type')
                }
                if (trend.length > 0 && trend[trend.length - 1].time === u.time) {
                    trend[trend.length - 1].count = count;
                } else {
                    if (trend.length == 0) {
                        trend.push({'time': u.time, 'count': 1})
                    }
                    // console.log('count', count)
                  // trend.push({'time': u.time, 'count': count === 0 && u.taskId === lastTaskId ? 1 : count})
                  // lastTaskId = u.task
                  trend.push({'time': u.time, 'count': count})

                }

            })

            return trend
        },

        getColorTicks(nodeId, trend, timeInterval, globalMaxCount) {
            if (trend.length === 0) {
                return []
            }
            let timeExtent = d3.extent(trend, u => u.time)
            if (this.stepSelectorIndex === 0 ){
                if (!this.overallExtend.has(nodeId)) {
                    this.overallExtend.set(nodeId, timeExtent)
                }
            }
            //   if (nodeId === "Map 23" ){
            //     console.log(trend)
            // }
            timeExtent = this.overallExtend.get(nodeId);
            const getTimePercent = function getTimePercent(time) {
                if (time === timeExtent[0]) {
                    return 0
                }

                return (time - timeExtent[0]) / (timeExtent[1] - timeExtent[0]) * 100
            }
            const colorTicks = []

            // remove last one (as it must be 0)
            for (let i = 0; i < trend.length - 1; ++i) {
                const t0 = trend[i], t1 = trend[i + 1]
                let color
                if (t0.count === 0) {
                    color = 'gray'
                } else {
                    color = colorGen(t0.count / (globalMaxCount + 5 ))
                }
                //TODO verify here
                colorTicks.push({percent: getTimePercent(t0.time) , color})
                colorTicks.push({percent: getTimePercent(t1.time), color})
            }
            let color = "grey"
            colorTicks.push({percent: getTimePercent(trend[trend.length - 1].time), color})

            // let maxTime = d3.max(trend, t => t.time)
            // for (;maxTime<timeExtent[1];maxTime++){
            //
            // }
            //         let color = 'gray'
            // colorTicks.push({percent: getTimePercent(maxTime), color})

            return colorTicks
        },

        getIndex(ary, val){
            let index = null;
            ary.every(function (value, i){
                if (val === value){
                    index = i;
                    return false;
                }
                return true;
            });
            return index;
        },
        clickShowProgress(){
            this.showProgress = !this.showProgress
        },
        clickShowPerf(){
            this.showPerformance = !this.showPerformance
        },
        changeMergeCount(mergeCount) {
            if (this.loaded) {
                this.$store.commit('comparison/changeMergeCount', mergeCount)
                this.$store.commit('comparison/updateLayout')
            }
        },
        toUnfoldMode() {
            console.log('unfold', this.tdagCursorMode)
            if (this.tdagCursorMode === TDAGCursorMode.UNFOLD) {
                this.$store.commit('comparison/changeTDAGCursorMode',
                    {app: this.app, mode: TDAGCursorMode.NORMAL})
            } else {
                this.$store.commit('comparison/changeTDAGCursorMode',
                    {app: this.app, mode: TDAGCursorMode.UNFOLD})
            }
        },
        toFoldMode() {
            console.log('fold', this.tdagCursorMode)
            if (this.tdagCursorMode === TDAGCursorMode.FOLD) {
                this.$store.commit('comparison/changeTDAGCursorMode',
                    {app: this.app, mode: TDAGCursorMode.NORMAL})
            } else {
                this.$store.commit('comparison/changeTDAGCursorMode',
                    {app: this.app, mode: TDAGCursorMode.FOLD})
            }
        },
        changeShowStepView() {
            this.showStepView ^= true
        },

        getEdgeStrokeWidth(edge) {
            const srcLayout = edge.src.data.layout,
                dstLayout = edge.dst.data.layout
            const toBold = [srcLayout, dstLayout].every(layout => {
                return layout.selectCurrent || layout.selectAsProvider || layout.selectAsConsumer
            })
            return 0.2
            // return toBold ? 2.5 : 0.5
        },
        updateAxis() {
            d3.select(this.$el).select('.timeAxis').call(generateScale(this.newXScale));
            d3.select(this.$el).select('.timeAxis').selectAll('text').style('font-size', 10)
        },
        generateColorPropMap(){
            const ret = new Map()

            // cluster tasks by vertex
            const vertexTasksMap = new Map()
            this.taskList.forEach(task => {
                if (!vertexTasksMap.has(task.vec_name)) {
                    vertexTasksMap.set(task.vec_name, [])
                }
                vertexTasksMap.get(task.vec_name).push(task)
            })
            // console.log('vertexTasksMap', vertexTasksMap)

            const taskListMap = new Map()   // layout node -> tasks
            this.nodes.forEach(node => {
                const tasks = []
                node.data.vertexIdList.forEach(vertexName => {
                    tasks.push(...vertexTasksMap.get(vertexName))
                })
                taskListMap.set(node.id, tasks)
            })
            // console.log('taskListMap', taskListMap)

            const trendMap = new Map()
            Array.from(taskListMap.entries()).forEach(entry => {
                const [nodeId, tasks] = entry
                const trend = this.getTrend(tasks)
                trendMap.set(nodeId, trend)
            })
            const maxCount = d3.max(Array.from(trendMap.values()), trend => d3.max(trend, t => t.count))
            // console.log(maxCount)
            Array.from(trendMap.entries()).forEach(entry => {
                const [nodeId, trend] = entry
                ret.set(nodeId, this.getColorTicks(nodeId, trend, 100, maxCount))
            })
            return ret
        }
    },
    computed: {
        stepSelector(){
            return this.app.stepNames
        },
        graph() {
            return this.app.visGraph
        },
        loaded() {
            return !!this.graph
        },
        ...mapState('comparison', {
            colorSchema: state => state.colorSchema,
            layoutConfig: state => state.layoutConfig,
            gapPixel: state => state.gapPixel,
            tdagTransform: state => state.tdagTransform,
            lastMove: state => state.lastMove,
        }),
        taskList() {
            return this.app.taskList
        },
        dagRoot() {
            return this.app.dagRoot
        },
        tdagCursorMode() {
            return this.app.tdagCursorMode
        },
        stateXScale() {
            return this.app.xScale
        },
        // tdagTransform() {
        //   return this.app.tdagTransform
        // },
        renderAxis() {
            return this.app.renderAxis
        },
        orderMap() {
            const originOrderMap = this.app.orderMap
            let orderMap = new Map()
            Object.keys(originOrderMap).forEach(vertexName => {
                orderMap.set(vertexName, originOrderMap[vertexName])
            })
            return orderMap
        },
        nodes() {
            return this.graph ? this.graph.nodes : []
        },
        edges() {
            return this.graph ?
                [...this.graph.edges].sort((e1, e2) => e2.data - e1.data) : []
        },
        pathModels() {
            return this.edges.map(e => {
                let offsetY = this.layoutConfig.vertexHeight / 2
                let sx = e.src.data.layout.x1,
                    sy = e.src.data.layout.y + offsetY,
                    dx = e.dst.data.layout.x0,
                    dy = e.dst.data.layout.y + offsetY
                if (dx <= sx) {
                    dx = Math.min(e.dst.data.layout.x1, sx + 20)
                    dy += ((sy < dy) ? -1 : 1) * offsetY
                }
                dx = Math.max(sx, dx)
                let points = [
                    [sx, sy],
                    [(sx + dx) / 2, sy],
                    [(sx + dx) / 2, dy],
                    [dx, dy]
                ]
                return {path: curveGen(points), edge: e}
            })
        },

      colorPropMap() {
            return this.generateColorPropMap()
        },
        unfoldIconColor() {
            return this.tdagCursorMode === TDAGCursorMode.UNFOLD ? '#539fff' : '#231815'
        },
        foldIconColor() {
            return this.tdagCursorMode === TDAGCursorMode.FOLD ? '#539fff' : '#231815'
        },
        stepViewIconColor() {
            return this.showStepView ? '#539fff' : '#231815'
        },
        stateXScaleRage() {
            return this.stateXScale?.range()
        },
        minTaskNoColor() {
            return colorGen(0)
        },
        maxTaskNoColor() {
            return colorGen(1)
        }
    }
}
</script>

<style scoped>
.bottom-group {
    /*position: absolute;*/
    /*left: 0;*/
    /*bottom: 0;*/
    /*margin: 10px;*/
    /*padding: 2px;*/
    /*float: right;*/
    /*border-radius: 4px;*/
    /*background: rgba(241, 241, 241, 0.62);*/

    position: absolute;
    right: 30px;
    top: -25px;
}

.icon {
    float: left;
    cursor: pointer;
    margin: 2px;
    border: rgba(255, 255, 255, 0) solid 1px;
    border-radius: 3px;
    transition: border 0.4s
}

.icon:hover {
    border: rgb(206, 206, 206) solid 1px;
}

.vertex-rect {
    cursor: pointer;
}
.svgContainer{
    border-style: solid;
    border-color: #d9d8d8;
    border-width: 0.2px;
    border-radius: 3px;
    width: calc(100% - 10px);
    /*height: calc(50% - 12px);*/
}
</style>
