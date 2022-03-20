<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Alert></Alert>
    <Myform></Myform>
  </div>
</template>

<script>
import Alert from '@/components/AlertComponent.vue';
import Myform from '@/components/FormComponent.vue';

export default {
  components: {
    Alert,
    Myform,
  },
};
</script>
