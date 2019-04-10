<template>
  <div>
    <p>props.name: {{ name }}</p>
    <p>props.info: {{ info }}</p>
    <p>props.list: {{ list }}</p>
    <p>data.a: {{ a }}</p>
    <p>
      <button @click="handleAChange">change data.a</button>
    </p>

    <p>data.b: {{ b }}</p>
    <p>
      <button @click="handleBChange">change data.b</button>
    </p>

  </div>
</template>
<script>
export default {
  name: "PropsAndData",
  props: {
    info: Object,
    name: String,
    list: Array
  },
  data() {
    this.b= "world"
    return {
      a: "hello"
    };
  },
  updated() {
    console.log("触发 PropsAndData updated");
  },
  methods: {
    handleBChange() {
      this.b = "vue" + Date.now();
      console.log("data.b 发生了变化，但是并没有触发组件更新", this.b);
    },

    handleAChange() {
      this.a = "a vue" + Date.now();
      console.log("data.a 发生了变化，会出发组件更新", this.a);
    }
  }
};
</script>
