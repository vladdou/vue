<template>
    <JqxChart :theme="'material'" style="width: 90%; height: 500px"
              :title="'Stacked waterfall series with logarithmic axis'"
              :description="'Logarithmic base 2'" :padding="padding"
              :titlePadding="titlePadding" :source="sampleData" :xAxis="xAxis"
              :valueAxis="valueAxis" :seriesGroups="seriesGroups">
    </JqxChart>
</template>

<script>
    import JqxChart from "jqwidgets-scripts/jqwidgets-vue/vue_jqxchart.vue";

    export default {
        components: {
            JqxChart
        },
        data: function () {
            return {
                sampleData: [
                    { a: 35, b: 40 },
                    { a: 10, b: 25 },
                    { a: 20, b: 20 },
                    { a: 30, b: 25 },
                    { a: 40, b: 17 },
                    { a: 45, b: 20 },
                    { a: 20, b: 30 }
                ],
                padding: { left: 5, top: 5, right: 5, bottom: 5 },
                titlePadding: { left: 0, top: 0, right: 0, bottom: 10 },
                xAxis: {
                    gridLines: { visible: true },
                    tickMarks: { visible: true }
                },
                valueAxis: {
                    logarithmicScale: true,
                    logarithmicScaleBase: 2,
                    title: { text: 'Value<br>' },
                    labels:
                        {
                            formatSettings: { decimalPlaces: 0 },
                            horizontalAlignment: 'right'
                        }
                },
                seriesGroups: [
                    {
                        type: 'stackedwaterfall',
                        columnsMaxWidth: 50,
                        series: [
                            { dataField: 'a', displayText: 'A' },
                            { dataField: 'b', displayText: 'B', summary: 'c' }
                        ]
                    }
                ]
            }
        }
    };
</script>

<style>
  
  
</style>