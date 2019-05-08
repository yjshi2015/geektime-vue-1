<template>
  <div>
    {{ log("render") }}
    {{ now }}
    <button @click="start = !start">{{ start ? "停止" : "开始" }}</button>
  </div>
</template>
<script>
import moment from "moment";
export default {
  data: function() {
    console.log("data");
    this.moment = moment;
    this.log = window.console.log;
    return {
      now: moment(new Date()).format("YYYY-MM-DD HH:mm:ss"),
      start: false
    };
  },
  watch: {
    start() {
      this.startClock();
    }
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  created() {
    console.log("created");
  },
  beforeMount() {
    console.log("beforeMount");
  },
  mounted() {
    console.log("mounted");
    this.startClock();
  },
  beforeUpdate() {
    console.log("syj==============beforeUpdate");
  },
  updated() {
    console.log("syj==============updated");
  },
  beforeDestroy() {
    console.log("syj--------------beforeDestroy");
    //销毁的时候要把计时器clear掉，否则会导致内存泄漏
    clearInterval(this.clockInterval);
  },
  destroyed() {
    console.log("syj--------------destroyed");
  },
  methods: {
    startClock() {
      clearInterval(this.clockInterval);
      if (this.start) {
        this.clockInterval = setInterval(() => {
          this.now = moment(new Date()).format("YYYY-MM-DD HH:mm:ss");
        }, 1000);
      }
    }
  }
};
</script>
