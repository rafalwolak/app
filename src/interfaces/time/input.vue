<template>
  <v-input
    type="time"
    class="input"
    :readonly="readonly"
    @input="emitValue"
    :value="value"
  ></v-input>
</template>

<script>
import mixin from "@directus/extension-toolkit/mixins/interface";

export default {
  mixins: [mixin],
  methods: {
    emitValue(value) {
      if (value.length !== 8) value = value + ":00";

      this.$emit("input", value);
    }
  }
};
</script>

<style lang="scss" scoped></style>
