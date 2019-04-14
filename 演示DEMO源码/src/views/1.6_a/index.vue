<template>
  <div>
    <Spike :start-time="startTime" :end-time="endTime" />
  </div>
</template>
<script>
import moment from "moment";
import Spike from "./Spike";
export default {
  components: {
    Spike
  },
  data() {
    return {
      startTime: moment("2019-04-14 08:00:00"),
      endTime: moment("2019-04-14 14:20:00")
    };
  }
};
</script>
