<template>
  <div>
    <input
      type="number"
      :autoFocus="true"
      v-on:keyup.enter="onKeyDown"
      placeholder="请输入13位时间戳"
    />
    <p v-if="parsedDate">{{ parsedDate }}</p>
  </div>
</template>

<script>
import dayjs from "dayjs";
import { debounce } from "../utils";

export default {
  name: "FormatTimestap",
  data() {
    return {
      parsedDate: 0
    };
  },
  methods: {
    onKeyDown: debounce(
      function(event) {
        try {
          const value = event?.[0]?.target.value;
          if (value) {
            this.parsedDate = dayjs(Number(value)).format(
              "YYYY年MM月DD日 HH:mm:ss SSS"
            );
          }
        } catch (err) {
          console.error(err);
        }
      },
      { delay: 300, immediate: true }
    )
  }
};
</script>