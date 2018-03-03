<template>
    <div class="row">
      <div class="col-md-12">
        <div>
        <button type="button" style="margin-bottom=10px" v-on:click="notHidden">Create Product</button>
        <button v-if="notHidden" v-on:click="notHidden=!notHidden" type="button" style="margin-bottom=10px">Create Product</button>
        </div>
      <div v-if="!notHidden" id="creating">
        <p>
        </p>

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
//  import axios from 'axios'
//  import VueResource from 'vue-resource'
  const tableColumns = ['Product ID', 'Name', 'Price', 'Created At', 'Updated At', 'Seller Name']
  const tableData = [{
  }]

// Vue.use(VueResource)

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
  //       intoTable: {
  //         id: '',
  //         name: '',
  //         price: '',
  //         sellerName: ''
  //       }
  // //      postBody: '',
  //      errors: []

      }
    }
    // methods:
    // function callback (error, response, body) {
    //   if (!error && response.statusCode === 200) {
    //     var info = JSON.parse(body)
    //     console.log(this.table1)
    //   }
    // }
  // createProduct() {
  //   axios.post(`http://localhost:8080/#/admin/product-list`) {
  //     body: this.postBody
  //   })
  //   .then(response => {})
  //   .catch(e => {
  //     this.errors.push(e)
  //   })
}

  var creating = new Vue({
    el: '#creating',
    data: {
      notHidden: true
    }
  })
/*
  methods: {
    intoTable() {
      id: this.intoTable.id,
      name: this.intoTable.name,
      price: this.intoTable.price,
      sellerName: this.intoTable.sellerName
    }
    console.log(this.intoTable)
  addToAPI() {
      let newProduct = {
        id: this.intoTable.id,
        name: this.intoTable.name,
        price: this.intoTable.price,
        sellerName: this.intoTable.sellerName
      }
      console.log(this.newProduct)
    }
  }
*/
</script>
<style>

</style>
