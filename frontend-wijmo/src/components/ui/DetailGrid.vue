<template>
    <wj-flex-grid
        ref="flexGridDetails"
        :autoGenerateColumns="false"
        :allowAddNew="false"
        :allowDelete="true"
        :allowPinning="'SingleColumn'"
        :newRowAtTop="false"
        :showMarquee="true"
        :selectionMode="'MultiRange'"
        :validateEdits="false"
        :itemsSource="selectedGrid"
        :initialized="flexDetailsInitialized"
        style="margin-top:10px; max-height:65vh;"
    >
        <wj-flex-grid-cell-template cellType="RowHeader" v-slot="cell">{{cell.row.index + 1}}</wj-flex-grid-cell-template>
    </wj-flex-grid>
</template>

<script>
import '@grapecity/wijmo.touch';
import '@grapecity/wijmo.vue2.grid';

export default {
    name: 'companyIdDetailGrid',
    props: {
        selectedGrid: {
            type: Array,
            required: true
        }
    },
    methods: {
        flexDetailsInitialized(flexGridDetails) {
            this.$refs.flexGridDetails = flexGridDetails;
        },
    },
}
</script>

