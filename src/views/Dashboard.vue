<template>
  <div class="container-fluid">
    <div class="row">
      <b-col cols="2">
        tes
      </b-col>
      <b-col>
        <ListBarang />
      </b-col>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import ListBarang from "@/components/ListBarang.vue";

export default {
  name: "Dashboard",
  components: {
    ListBarang,
  },
};
</script>
