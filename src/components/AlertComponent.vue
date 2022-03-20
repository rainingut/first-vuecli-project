<template>
   <div class="alert alert-danger" role="alert">
     {{ content }}
   </div>
</template>

<script>
export default {
  data() {
    return { content: '這是個警示' };
  },
};
</script>
