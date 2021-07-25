<template>
  <v-text-field
    :label="label"
    :prepend-icon="prependIcon"
    outlined
    :value="value"
    :required="required"
    @input="$emit('input', $event.target.value)"
    :ruleName="ruleName"
    :rules="
      ruleName == 'name'
        ? nameRules
        : ruleName == 'email'
        ? emailRules
        : noRules
    "
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

    required: {
      type: Boolean,
    },

    rules: { type: Array },

    ruleName: {},
  },

  data() {
    return {
      noRules: [],
      nameRules: [
        (v) => !!v || "Name is required",
        (v) => (v && v.length <= 10) || "Name must be less than 10 characters",
      ],
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => (v && v.length <= 10) || "Name must be less than 10 characters",
      ],
    };
  },
};
</script>
