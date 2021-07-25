<template>
  <v-btn
    :color="color"
    v-text="textBtn"
    @click="$emit('click', $event.target.value) && sayHi()"
    :to="to"
  >
  </v-btn>
</template>

<script>
export default {
  name: "BaseButton",

  props: {
    color: {
      type: String,
    },

    textBtn: {
      type: String,
    },

    to: {
      type: String,
    },
  },

  methods: {
    sayHi() {
      console.log("Oiii !!!");
    },
  },
};
</script>
