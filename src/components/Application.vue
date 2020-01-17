<template>
  <div>
    <a :href="url">
    <b-container>
      <div id="app">
      <b-row>
        <b-col>
          <p v-if="showName">
            {{ name }}
          </p>
        </b-col>
      </b-row>
      <b-row>
      <b-col>
        <font-awesome-icon
        size="4x"
        :icon="[iconType, icon]"
        v-if="icon"
        fixed-width
        />
        <img 
        :src="imageUrl"
        v-else-if="imageUrl"
        />
      </b-col>
      </b-row>
      </div>
    </b-container>
    </a>
  </div>
</template>
<script>
export default {
  name: "Application",
  props: {
    name: {
      type: String,
      default: "",
      required: true,
    },
    url: {
      type: String,
      default: "",
      required: true,
    },
    imageUrl: {
      type: String,
      default: "",
      required: false,
    },
    icon: {
      type: String,
      default: "",
      required: false,
    },
    iconType: {
      type: String,
      default: "fa",
      required: false,
    },
    showName: {
      type: Boolean,
      default: true,
      required: false,
    },
  }
};
</script>
<style scoped>
#app {
  border: 1px solid #9e9e9e;
  background: #e0e0e0;
  width: 20%;
  height: 20%;
  min-width: 20vh;
  min-height: 20vh;
  max-height: 20vh;
  padding: 5vh;
  margin: 3vh;
}
img {
  width: 8vh;
  height: 8vh;
}
a {
  color: black;
}
p {
  color: #616161;
}
a:hover {
  color: black;
  text-decoration: none;
}
</style>
