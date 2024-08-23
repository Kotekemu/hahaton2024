<template>
  <q-page class="q-pa-md">
    <div class="q-gutter-md">
      <q-input
        filled
        v-model="url"
        label="Введите URL сайта"
        placeholder="https://example.com"
        dense
      ></q-input>

      <q-btn
        label="Проверить"
        color="primary"
        @click="checkWebsiteSafety"
      ></q-btn>

      <q-banner v-if="result" :color="resultColor" class="q-mt-md">
        {{ result }}
      </q-banner>
    </div>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      url: "",
      result: "",
      resultColor: "grey-8",
    };
  },
  methods: {
    async checkWebsiteSafety() {
      const apiKey = "cc9a9714-8119-4e22-a640-fbadd17ff92b";
      const apiUrl =
        "https://safebrowsing.yandex.net/v4/threatMatches:find?key=cc9a9714-8119-4e22-a640-fbadd17ff92b";

      const requestBody = {
        client: {
          clientId: "yourclientid",
          clientVersion: "1.0",
        },
        threatInfo: {
          threatTypes: ["MALWARE", "SOCIAL_ENGINEERING"],
          platformTypes: ["ANY_PLATFORM"],
          threatEntryTypes: ["URL"],
          threatEntries: [{ url: this.url }],
        },
      };

      try {
        const response = await fetch(apiUrl, {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          body: JSON.stringify(requestBody),
        });

        const data = await response.json();

        if (data.matches && data.matches.length > 0) {
          this.result = "Вредоносный сайт";
          this.resultColor = "negative";
        } else {
          this.result = "Безопасный сайт";
          this.resultColor = "positive";
        }
      } catch (error) {
        console.error("Ошибка при проверке:", error);
        this.result = "Ошибка при проверке";
        this.resultColor = "negative";
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>
