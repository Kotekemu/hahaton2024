<template>
  <q-page padding>
    <q-form @submit.prevent="handleSubmit">
      <q-input
        v-model="password"
        type="text"
        label="Пароль"
        :rules="[validatePasswordRule]"
        lazy-rules
        @input="handleInput"
      />
      <q-btn type="submit" label="Отправить" />
      <q-banner v-if="message" :class="messageClass" class="q-mt-md">
        {{ message }}
      </q-banner>
    </q-form>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

function validatePassword(password) {
  const minLength = 8;
  if (password.length < minLength) {
    return {
      valid: false,
      message: "Пароль должен содержать минимум 8 символов.",
    };
  }

  const hasUppercase = /[A-Z]/.test(password);
  if (!hasUppercase) {
    return {
      valid: false,
      message: "Пароль должен содержать хотя бы одну большую букву.",
    };
  }

  const hasDigit = /\d/.test(password);
  if (!hasDigit) {
    return {
      valid: false,
      message: "Пароль должен содержать хотя бы одну цифру.",
    };
  }

  return { valid: true, message: "Ваш пароль надежный." };
}

export default defineComponent({
  data() {
    return {
      password: "",
      message: "",
      messageClass: "",
    };
  },
  methods: {
    validatePasswordRule(val) {
      const { valid, message } = validatePassword(val);
      return valid || message;
    },

    handleSubmit() {
      const { valid, message } = validatePassword(this.password);
      if (valid) {
        this.message = message;
        this.messageClass = "bg-green text-white";
      } else {
        this.message = message;
        this.messageClass = "bg-red text-white";
      }
    },
    handleInput() {
      const { valid } = validatePassword(this.password);
      if (!valid) {
        this.message = "";
      }
    },
  },
});
</script>
<style scoped></style>
