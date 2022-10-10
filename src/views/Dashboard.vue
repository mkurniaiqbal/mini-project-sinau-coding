<template>
  <div class="container-fluid">
    <div class="row">
      <b-col cols="2">
        tes
      </b-col>
      <b-col>
        <!-- <ListBarang /> -->
        <ListSupplier />
      </b-col>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ListBarang from "@/components/ListBarang.vue";
import ListSupplier from "@/components/ListSupplier.vue";


export default {
  name: "Dashboard",
  components: {
    ListBarang,
    ListSupplier,
  },
};
</script>
