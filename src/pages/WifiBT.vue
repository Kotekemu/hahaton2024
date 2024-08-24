<template>
    <q-layout>
      <q-header>
      </q-header>
      <q-page-container>
        <network-checker /> 
        
      </q-page-container>
    </q-layout>
  </template>
  
  <script>
  import NetworkChecker from 'src/components/NetworkChecker.vue';
  
  export default {
    components: {
      NetworkChecker
    }
  };
  </script>
  
  <style>
  </style>