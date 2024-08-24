<template>
    <q-page padding>
    </q-page>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    data() {
      return {
        bluetoothConnected: false,
        wifiConnected: false,
      };
    },
    mounted() {
      document.addEventListener('deviceready', this.checkConnections, false);
    },
    methods: {
      checkConnections() {
        // Проверка Bluetooth
        bluetoothle.isEnabled((result) => {
          this.bluetoothConnected = result.isEnabled;
          if (!this.bluetoothConnected) {
            this.showNotification('Bluetooth не включен. Включите его для корректной работы приложения.');
          }
        }, (error) => {
          console.error('Ошибка проверки Bluetooth:', error);
        });
  
        // Проверка Wi-Fi
        cordova.plugins.wifiManager.isWifiEnabled((result) => {
          this.wifiConnected = result.isWifiEnabled;
          if (!this.wifiConnected) {
            this.showNotification('Wi-Fi не включен. Включите его для корректной работы приложения.');
          }
        }, (error) => {
          console.error('Ошибка проверки Wi-Fi:', error);
        });
      },
      showNotification(message) {
        this.$q.dialog({
          title: 'Внимание',
          message: message,
          ok: {
            label: 'Ок',
            color: 'primary'
          },
          cancel: {
            label: 'Отмена',
            color: 'negative'
          },
        }).onOk(() => {
          console.log('Пользователь уведомлен.');
        }).onCancel(() => {
          console.log('Пользователь отменил уведомление.');
        });
      }
    }
  });
  </script>
  
  <style scoped>
  </style>