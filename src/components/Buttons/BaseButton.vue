<template>
  <v-btn
    :color="color"
    :textBtn="textBtn"
    @click="
      $emit('click', $event.target.value);
      sayHi();
    "
    :to="to"
    :disabled="disabled"
    :loading="btnLoading"
  >
    {{ textBtn }}
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

    disabled: {
      type: Boolean,
    },
  },

  data() {
    return {
      btnLoading: false,
    };
  },

  methods: {
    sayHi() {
      console.log("Oiii !!!");
    },
  },

  created() {
    this.$root.$on("btnLoading::show", () => {
      this.btnLoading = true;
    });
    this.$root.$on("btnLoading::hide", () => {
      this.btnLoading = false;
    });
  },
};
</script>
