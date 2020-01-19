<template>
  <div>
    <a :href="url">
    <b-container>
      <div :class="['app', sourceClass]">
        <b-row v-if="source">
          <b-col lg="1" offset-lg="9">
            <a :href="source">
              <font-awesome-icon
                size="1x"
                :icon="['fas', 'code-branch']"
                fixed-width
              />
            </a>
          </b-col>
        </b-row>
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
    source: {
      type: String,
      default: "",
      required: false,
    }
  },
  computed: {
    sourceClass: function() {
      return this.source != "" ? "source" : "no-source"
    }
  }
};
</script>
<style scoped>
.app {
  border: 1px solid #9e9e9e;
  background: #e0e0e0;
  width: 20%;
  height: 20%;
  min-width: 20vh;
  min-height: 20vh;
  max-height: 20vh;
  padding: 2vh;
  margin: 3vh;
}
.app.no-source {
  padding: 4vh;
}
img {
  width: 8vh;
  height: 8vh;
}
a,a:hover {
  color: #212121;
  text-decoration: none;
}
p {
  color: #616161;
}
</style>
