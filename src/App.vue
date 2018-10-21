<template>
  <div id="hot-preview">
  <div>
    Select your template.
    <model-select :options="templates"
                                v-model="item"
                                placeholder="select item">
         </model-select>
  </div>

    <HotTable :settings="settings"></HotTable>
  </div>
</template>

<script>
  import { HotTable } from '@handsontable/vue';
  import { ModelSelect } from 'vue-search-select'

  import Vue from 'vue';

  let templateItem = {
          value: '',
          text: ''
        };
  let templateList = [
          { value: '1', text: 'aa' + ' - ' + '1' },
          { value: '2', text: 'ab' + ' - ' + '2' },
          { value: '3', text: 'bc' + ' - ' + '3' },
          { value: '4', text: 'cd' + ' - ' + '4' },
          { value: '5', text: 'de' + ' - ' + '5' }
        ];

  export default {
    data: function() {
      return {
        settings: {
          data: [
            ['', '', '', '', '', ''],
            ['', '', '', '', '', ''],
            ['', '', '', '', '', ''],
            
          ],
          colHeaders: [
            'ID',
            'Country',
            'Code',
            'Currency',
            'Level',
            'Units',
            'Date',
            'Change'
          ],
          rowHeaders: false,
          fixedRowsTop: 1,
          allowInsertRow: true,
        },
        templates: templateList,
        item: templateItem,
      };
    },
    components: {
      HotTable,
      ModelSelect
    }
  }
</script>

<style src="../node_modules/handsontable/dist/handsontable.full.css"></style>
<style>
  #test-hot {
    width: 600px;
    height: 400px;
    overflow: hidden;
  }
</style>