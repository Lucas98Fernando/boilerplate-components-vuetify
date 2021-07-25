<template>
  <v-text-field
    :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
    :rules="[rules.required, rules.min]"
    :type="show ? 'text' : 'password'"
    name="input-10-2"
    label="Visible"
    hint="At least 8 characters"
    :value="value"
    @input="$emit('input', $event.target.value)"
    class="input-group--focused"
    prepend-icon="mdi-lock"
    outlined
    @click:append="show = !show"
  ></v-text-field>
</template>

<script>
export default {
  name: "BaseInputPassword",
  props: {
    value: {
      type: String,
    },
  },
  data() {
    return {
      show: false,
      rules: {
        required: (value) => !!value || "Required.",
        min: (v) => v.length >= 8 || "Min 8 characters",
      },
    };
  },
};
</script>
