<template>
  <div><h1>Card</h1></div>
</template>

<script>
import { useRoute } from "vue-router";
import { watch, onMounted } from "vue";
export default {
  setup() {
    const route = useRoute();

    onMounted(() => {
      // const tipoModelo = route.params.tipoModelo
      const {
        params: { tipoModelo },
      } = route;
      getData(tipoModelo);
    });

    watch(
      () => route.params,
      (params, prevParams) => {
        const { tipoModelo } = params;
        getData(tipoModelo);
      }
    );

    const getData = (tipoModelo) => {
      console.log(tipoModelo);
      // this.$firebase
      //   .collection("modelos")
      //   .where("tipoModelo", "==", tipoModelo)
      //   .get()
      //   .then((docs) => {
      //     docs.forEach((doc) => {
      //       console.log(doc.data());
      //     });
    };

    return {
      getData,
    };

    // computed -> cache do valor, retorna algo
    // watch -> retorna nenhum valor
  },
};
</script>

<style></style>
