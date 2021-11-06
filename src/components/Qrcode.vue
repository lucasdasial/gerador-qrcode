<template>
  <qrcode-vue :value="url" :size="size" level="H" />
</template>
<script>
  import QrcodeVue from "qrcode.vue";

  export default {
    props: {
      url: {
        type: String,
      },
    },
    data() {
      return {
        size: 200,
      };
    },
    components: {
      QrcodeVue,
    },
  };
</script>
