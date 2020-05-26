<template>
  <div class="hello">
    <Rate @on-change="changes" show-text allow-half v-model="stars">
      <span style="color: #f5a623">{{ stars }}</span>
    </Rate>
  </div>
</template>

<script>
export default {
  props: ["id", "star"],
  data() {
    return {
      value: "",
      stars: ""
    };
  },
  created() {
    this.stars = this.star;
  },
  methods: {
    changes() {
      this.$emit("event", {
        id: this.id,
        star: this.stars
      });
      console.log("id", this.id);
      console.log("env", this.stars);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
