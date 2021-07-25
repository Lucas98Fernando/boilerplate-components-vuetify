<template>
  <v-container>
    <v-form ref="form" v-model="valid" lazy-validation>
      <BaseInput
        label="Nome"
        class="mt-4"
        prepend-icon="mdi-account"
        ruleName=""
        v-model="nome"
        required
      ></BaseInput>
      <BaseInput
        label="E-mail"
        prepend-icon="mdi-email"
        ruleName="email"
        v-model="email"
        required
      ></BaseInput>
      <BaseInputPassword v-model="password"></BaseInputPassword>
      <BaseButton
        color="primary"
        @click="validate()"
        class="my-4"
        textBtn="Entrar"
        :disabled="!valid"
      ></BaseButton>
      <!-- <BaseButton
        color="red"
        @click="
          sayHello();
          validate();
        "
        class="my-4"
        textBtn="Excluir"
        to="/about"
      ></BaseButton> -->
    </v-form>
  </v-container>
</template>

<script>
import BaseButton from "./Buttons/BaseButton.vue";
import BaseInput from "./Input/BaseInput.vue";
import BaseInputPassword from "./Input/BaseInputPassword.vue";
export default {
  name: "HelloWorld",
  components: { BaseButton, BaseInput, BaseInputPassword },
  data() {
    return {
      valid: true,
      nome: "",
      email: "",
      password: "",
    };
  },
  methods: {
    validate() {
      this.$refs.form.validate();
      this.$root.$emit("btnLoading::show");
      setTimeout(() => this.$root.$emit("btnLoading::hide"), 3000);
    },
    sayHello() {
      alert("Olá !!!");
    },
  },
};
</script>
