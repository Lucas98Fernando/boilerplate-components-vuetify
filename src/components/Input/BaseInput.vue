<template>
  <v-text-field
    :label="label"
    :prepend-icon="prependIcon"
    outlined
    :value="value"
    @input="$emit('input', $event.target.value)"
  ></v-text-field>
</template>

<script>
export default {
  name: "BaseInput",
  props: {
    label: {
      type: String,
    },

    prependIcon: {
      type: String,
    },

    value: {
      type: String,
    },
  },
};
</script>
