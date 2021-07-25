<template>
  <div>
    <BaseInput
      label="Nome"
      class="mt-4"
      prepend-icon="mdi-account"
      v-model="nome"
    ></BaseInput>
    <BaseInput
      label="Senha"
      prepend-icon="mdi-mail"
      v-model="email"
    ></BaseInput>
    <BaseButton
      color="primary"
      @click="sayHello()"
      class="my-4"
      textBtn="Entrar"
    ></BaseButton>
    <BaseButton
      color="red"
      @click="sayHello()"
      class="my-4"
      textBtn="Excluir"
      to="/about"
    ></BaseButton>
  </div>
</template>

<script>
import BaseButton from "./Buttons/BaseButton.vue";
import BaseInput from "./Input/BaseInput.vue";
export default {
  name: "HelloWorld",
  components: { BaseButton, BaseInput },
  data() {
    return {
      nome: "Esse é o v-model funcionando",
      email: "",
    };
  },
  methods: {
    sayHello() {
      alert("Olá !!!");
    },
  },
};
</script>
