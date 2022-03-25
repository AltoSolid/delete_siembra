<template>
  <div>
    <Element
      v-for="element in plantingInformation"
      @click.native="deleteElement(element)"
      :key="element.id"
      class="center"
    >
      Se sembró {{ element.semilla }} el dia {{ element.fechaSiembra.slice(0,10) }}
    </Element>
  </div>
</template>

<script>
import Element from "./Element";

export default {
  data() {
    return {
      hora: '',
    }
  },
  props: ["plantingInformation"],
  methods: {
    deleteElement(plantingInformation, index) {
      console.log(plantingInformation._id);
      this.hora = plantingInformation.fechaSiembra;
      console.log(this.hora);
      this.$emit("deletedId", plantingInformation._id);
    },
  },
  components: {
    Element
  }
};
</script>

<style scoped>
  .center {
    margin: auto;
    width: 50%;
    padding: 10px;
  }
</style>
