<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ name }}
    <Alert></Alert>
    <Myform></Myform>
  </div>
</template>

<script>
import Alert from '@/components/AlertComponent.vue';
import Myform from '@/components/FormComponent.vue';

export default {
  data() {
    return {
      name: process.env.VUE_APP_NAME,
    };
  },
  components: {
    Alert,
    Myform,
  },
};
</script>
