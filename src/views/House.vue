<template>
  <div class="house">
    <h5>Year: {{house.year}}</h5>
    <h5>Bedrooms: {{house.bedrooms}}</h5>
    <h5>Bathrooms: {{house.bathrooms}}</h5>
    <h5>Levels: {{house.levels}}</h5>
    <h5>Price: {{house.price}}</h5>
    <img :src="house.imgUrl" />
    <h5>{{house.description}}</h5>
    <button class="btn btn-danger" @click="delort">Delort</button>
  </div>
</template>


<script>
export default {
  name: "house",
  data() {
    return {};
  },
  mounted() {
    let payload = { houseId: this.$route.params.houseId };
    this.$store.dispatch("getHouseById", payload);
  },
  computed: {
    house() {
      return this.$store.state.activeHouse;
    }
  },
  methods: {
    delort() {
      this.$store.dispatch("delortHouse", this.house._id);
    }
  },
  components: {}
};
</script>


<style scoped>
img {
  height: 30vh;
  /* height: 500px; */
}
</style>