<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>
      <a :class="{'active':activeStage==1}" @click="activeStage=1">Stage-1</a> ||
      <a :class="{'active':activeStage==2}" @click="activeStage=2">Stage-2</a>
    </h2>
    <stage1 @proceed-stage="activeStage=2" v-if="activeStage==1"></stage1>
    <stage2  v-if="activeStage==2" @backstage="activeStage=1"></stage2>
  </div>
</template>

<script>
import stage1 from "./stage1.vue";
import stage2 from "./stage2.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    stage1,
    stage2
  },
  data() {
    return {
      activeStage: 1
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.active {
  color: green;
  font-weight: bold;
}
</style>
