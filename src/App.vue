<template>
  <div class="container-fluid">
      <div class="row my-5 justify-content-center">
        <div class="col-md-10">
            <AppTitle text="Invoice Application" />

            <InputForm @add-list="addInvoiceList"  />
            <ItemTable :lists="invoiceLists" @delete-list="del" />
            <div class="" v-show="invoiceLists.length">
              <button class="btn btn-outline-primary d-print-none" @click="toPrint">Print</button>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
import AppTitle from "@/components/AppTitle";
import InputForm from "@/components/InputForm";
import ItemTable from "@/components/ItemTable";
export default {
  components: {ItemTable, InputForm, AppTitle},
  data() {
    return {
      invoiceLists: [

      ]
    }
  },
  methods: {
    addInvoiceList(quantity,selectedItem) {
      this.invoiceLists = [...this.invoiceLists,{
        itemName:selectedItem.name,
        price : selectedItem.price,
        quantity,
        cost : selectedItem.price * quantity
      }]
    },
    del(index){
      this.invoiceLists.splice(index,1)
    },
    toPrint(){
      print()
    }
  },
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;300;400;500&family=Padauk:wght@400;700&display=swap');

@import "bootstrap-icons/font/bootstrap-icons.css";
@import "animate.css/animate.min.css";
@import "bootstrap/dist/css/bootstrap.min.css";




*{
  font-family: 'Montserrat', sans-serif;;
}

</style>