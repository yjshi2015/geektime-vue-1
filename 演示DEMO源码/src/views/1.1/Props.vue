<template>
  <div>
    name: {{ name }}
    <br />
    type: {{ type }}
    <br />
    list: {{ list }}
    <br />
    isVisible: {{ isVisible }}
    <br />
    <button @click="handleClick">change type</button>
    <br />
    info: {{ info.id }}========{{ info.name }}
    <br />
    myInfo: {{ myInfo.id }}========{{ myInfo.name }}
    <br />
    myName: {{ myName }}
  </div>
</template>

<script>
export default {
  name: "PropsDemo",
  // inheritAttrs: false,
  // props: ['name', 'type', 'list', 'isVisible'],
  props: {
    name: {
      type: String,
      default: ""
    },
    type: {
      validator: function(value) {
        // 这个值必须匹配下列字符串中的一个
        return ["success", "warning", "danger"].includes(value);
      }
    },
    list: {
      type: Array,
      // 对象或数组默认值必须从一个工厂函数获取
      default: () => []
    },
    info: {
      type: Object,
      default: () => {}
    },
    isVisible: {
      type: Boolean,
      default: false
    },
    onChange: {
      type: Function,
      default: () => {}
    }
  },
  data: function() {
    return {
      myInfo: {
        id: "",
        name: ""
      },
      myName: ""
    };
  },
  watch: {
    info: {
      handler(val) {
        console.log("info=============");
      },
      immediate: true,
      deep: true
    },
    myInfo: {
      handler(val) {
        console.log(this.myInfo.id + " ==========");
      },
      deep: true
    },
    name(val) {
      console.log("name new: name ===============");
      this.myName = this.name;
    }
  },
  methods: {
    handleClick() {
      console.log("new: , old: ");
      // 不要这么做、不要这么做、不要这么做
      // this.type = "warning";

      // 可以，还可以更好
      this.onChange(this.type === "success" ? "warning" : "success");
      this.myInfo.id = "22" + Date.now();
      this.myInfo.name = "lisi" + Date.now();
    }
  }
};
</script>
