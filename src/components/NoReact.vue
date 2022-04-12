<template>
  <div class="hello" @click="test">test {{list }} {{ myObj }}</div>
</template>
<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      list: [1, 2],
      myObj: { name: "Preetish" }
    };
  },
  watch: {
    list: {
      handler() {
        console.log("watcher triggered");
      },
      deep: true
    }
  },
  methods: {
    test() {
      this.list[2] = 4;
    //   this.myObj.last = "HS";
    //   delete this.myObj.name;
    }
  }
};
</script>