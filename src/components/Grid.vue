<template>
  <div>
    <b-container>
      <b-row>
          <application v-for="app in pages" 
          :key="app.name" 
          :name="app.name"
          :url="app.url"
          :imageUrl="app.imageUrl"
          :icon="app.icon"
          :iconType="app.iconType"
          :showName="app.showName"
          :source="app.source"
          />
      </b-row>
    </b-container>
  </div>
</template>
<script>
import pages from "../pages";
import Application from "./Application.vue";

export default {
  name: "Grid",
  components: {
    Application
  },
  data: function() {
    return {
      pages: pages.sort((a, b) => {
        if (a.name < b.name) {
          return -1;
        } else if (b.name < a.name) {
          return 1;
        }
        return 0;
      })
    };
  }
};
</script>
<style scoped></style>
