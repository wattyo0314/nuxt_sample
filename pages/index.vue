<template>
  <div>
    <sample :title="title" :age="age">
      <div slot="red">
        彼女募集中
      </div>
      <div>
        絶賛
      </div>
    </sample>
    <nuxt-link to="/about">about</nuxt-link>
  </div>
</template>

<script>
import Sample from "~/components/Sample.vue";
export default {
  components: {
    Sample
  },
  data() {
    return {
      title: "vue.js",
      age: 31
    };
  }
};
</script>

<style></style>
