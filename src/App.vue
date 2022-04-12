<template>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <GreetWorld name="xxx" />
  <GreetWorld :name="name1" />
  <button @click="showPopup = true"></button>
  <PopupItem v-show="showPopup" @close="closePopup" />
  <div ref="example-element">{{ counter }}</div>
  <input type="text" ref="inputRef" id="vaite" />
  <CompositeApi/>
  <NonCompositeApi/>
  <Vue3ErrorCapture/>
  <NoReact/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import GreetWorld from './components/GreetWorld.vue'
import PopupItem from "./components/PopupItem.vue";
import CompositeApi from "./components/CompositeApi.vue"
import NonCompositeApi from "./components/NonCompositeApi.vue"
import Vue3ErrorCapture from "./components/Vue3ErrorCapture.vue"
import NoReact from "./components/NoReact.vue"
export default {
  name: "App",
  components: {
    HelloWorld,
    GreetWorld,
    PopupItem,
    CompositeApi,
    NonCompositeApi,
    Vue3ErrorCapture,
    NoReact
  },
  data() {
    return {
      name1: "pham duy dong",
      showPopup: false,
      property: "Example property.",
      counter: 0,
    };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log("name", name);
    },
  },

  // beforeCreate() {
  //   console.log("At this point, events and lifecycle have been initialized.");
  // },
  // computed: {
  //   propertyComputed() {
  //     return this.property;
  //   },
  // },

  // created() {
  //   console.log(
  //     "At this point, this.property is now reactive and propertyComputed will update."
  //   );
  //   this.property = "Example property updated.";
  //   setInterval(() => {
  //     this.counter++;
  //   }, 1000);
  // },
  // beforeMount() {
  //   console.log(`At this point, vm.$el has not been created yet.`);
  // },
  // mounted() {
  //  // this.$refs.inputRef.focus();
  //   // document.getElementById("vaite").focus();
  //   console.log(
  //     `At this point, vm.$el has been created and el has been replaced.`
  //   );
  //   console.log(this.$el.textContent); // Example component.
  // },

  // updated() {
  //   console.log(`At this point, Virtual DOM has re-rendered and patched.`);
  //   // Fired every second, should always be true
  //   console.log(+this.$refs["example-element"].textContent === this.counter);
  // },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
