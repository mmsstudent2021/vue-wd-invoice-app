<template>
  <div class="container">
      <div class="row my-5 justify-content-center">
        <div class="col-lg-8">
            <AppTitle text="Invoice Application" />
            <InputForm />
            <ItemTable />
        </div>
      </div>
  </div>
</template>

<script>
import AppTitle from "@/components/AppTitle";
import InputForm from "@/components/InputForm";
import ItemTable from "@/components/ItemTable";
export default {
  components: {ItemTable, InputForm, AppTitle}
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200;300;400;500&family=Padauk:wght@400;700&display=swap');

@import "bootstrap-icons/font/bootstrap-icons.css";
@import "bootstrap/dist/css/bootstrap.min.css";



*{
  font-family: 'Montserrat', sans-serif;;
}

</style>