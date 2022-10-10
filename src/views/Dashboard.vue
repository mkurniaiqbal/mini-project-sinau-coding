<template>
  <div class="container-fluid">
    <div class="row">
      <HeaderComp />
    </div>
    <div class="row">
      <b-col cols="2">
        tes
      </b-col>
      <b-col>
        <!-- <ListBarang /> -->
        <ListSupplier />
      </b-col>
    </div>
    <div class="row">
      <FooterComp />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ListBarang from "@/components/ListBarang.vue";
import ListSupplier from "@/components/ListSupplier.vue";
import FooterComp from "@/components/FooterComp.vue";
import HeaderComp from "@/components/HeaderComp.vue";

export default {
  name: "Dashboard",
  components: {
    ListBarang,
    ListSupplier,
    FooterComp,
    HeaderComp,

  },
};
</script>
