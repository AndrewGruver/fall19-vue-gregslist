<template>
  <div id="create-house-modal" class="modal" tabindex="-1" role="dialog">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Create A House!</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <form @submit.prevent="addHouse()">
            <div class="form-group">
              <label for="make">Year</label>
              <input
                type="number"
                class="form-control"
                id="year"
                placeholder="Enter year"
                v-model="newHouse.year"
              />
            </div>
            <div class="form-group">
              <label for="bedrooms">Bedrooms</label>
              <input
                type="number"
                class="form-control"
                id="bedrooms"
                placeholder="Enter number of bedrooms"
                v-model="newHouse.bedrooms"
              />
            </div>
            <div class="form-group">
              <label for="bathrooms">Bathrooms</label>
              <input
                type="number"
                class="form-control"
                id="bathrooms"
                placeholder="Enter number of bathrooms"
                v-model="newHouse.bathrooms"
              />
            </div>
            <div class="form-group">
              <label for="levels">Levels</label>
              <input
                type="number"
                class="form-control"
                id="levels"
                placeholder="Enter price"
                v-model="newHouse.levels"
              />
            </div>
            <div class="form-group">
              <label for="price">Price</label>
              <input
                type="number"
                class="form-control"
                id="price"
                placeholder="Enter price"
                v-model="newHouse.price"
              />
            </div>
            <div class="form-group">
              <label for="imgurl">Image Url</label>
              <input
                type="text"
                class="form-control"
                id="imgurl"
                placeholder="Enter imgurl"
                v-model="newHouse.imgUrl"
              />
            </div>
            <div class="form-group">
              <label for="description">Description</label>
              <input
                type="text"
                class="form-control"
                id="description"
                placeholder="Enter description"
                v-model="newHouse.description"
              />
            </div>
            <button type="submit" class="btn btn-primary">List House</button>
          </form>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "create-house-modal",
  data() {
    return {
      newHouse: {}
    };
  },
  computed: {},
  methods: {
    addHouse() {
      this.$store.dispatch("addHouse", this.newHouse);
      this.newHouse = {};
    }
  },
  components: {}
};
</script>


<style scoped>
</style>