
<template>
  <section class="content">
    <div class="container-fluid">
                <div class="mt-5">
                  <label>Our categories</label>
                  <div class="row">
                      <div class="col-md-6 card card-body bg-info mt-2" v-for="category in getAllCategory"
                            :value="category.id">
                           {{ category.name }}
                      </div>
                  </div>
                </div>
    </div>
  </section>
</template>

<script>
export default {
     name: "Category",
      mounted() {
        this.$store.dispatch("allCategoryFromDatabase")
      },
      computed: {
        getAllCategory(){ //final output from here
            return this.$store.getters.getCategoryFormGetters
        }
      },
};
</script>

<style scoped>

</style>
