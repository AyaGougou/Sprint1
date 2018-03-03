<template>
    <div class="row">
      <div class="col-md-12">
        <div>
        <button type="button" style="margin-bottom=10px" v-on:click="notHidden">Create Product</button>
        <p> hi i work </p>
        <button v-if="notHidden" v-on:click="notHidden=!notHidden" type="button" style="margin-bottom=10px">Create Product</button>
        </div>
      <div v-if="!notHidden" id="creating">

      </div>
        <div class="card">
          <paper-table :title="table2.title" :sub-title="table2.subTitle" :data="table2.data" :columns="table2.columns">
          </paper-table>
        </div>
      </div>
    </div>
</template>
<script>
  import PaperTable from 'components/UIComponents/PaperTable.vue'
  import Vue from 'vue'
  const tableColumns = ['Product ID', 'Name', 'Price', 'Created At', 'Updated At', 'Seller Name']
  const tableData = [{
  }]
  export default {
    components: {
      PaperTable
    },
    data () {
      return {
        table1: {
          title: 'Stripped Table',
          subTitle: 'Here is a subtitle for this table',
          columns: [...tableColumns],
          data: [...tableData]
        },
        table2: {
          title: 'Product List Table',
          subTitle: 'Here is a subtitle for this table',
          columns: [...tableColumns],
          data: [...tableData]
        }
      }
    }
}
  var creating = new Vue({
    el: '#creating',
    data: {
      notHidden: true
    }
  })
</script>
<style>

</style>
