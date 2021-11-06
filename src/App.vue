<template>
  <div class="box">
    <h2>{{ title }}</h2>
    <div class="box__item-input shadow">
      <input
        class="input"
        type="text"
        v-model="url"
        placeholder="Sua Url/menssagem aqui"
      />
    </div>
    <div class="box__item-code shadow">
      <my-qr-code class="qr-code" :url="url" v-if="url" />
    </div>
  </div>
</template>

<script>
  import MyQrCode from "./components/Qrcode.vue";
  export default {
    components: {
      MyQrCode,
    },
    data() {
      return {
        title: "Gerador de QrCode automatico",
        url: "",
      };
    },
  };
</script>

<style scoped>
  .box {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    background: rgb(31, 175, 76);
    background: linear-gradient(
      90deg,
      rgba(31, 175, 76, 1) 0%,
      rgba(12, 164, 173, 1) 100%
    );
  }
  .box__item-input {
    box-sizing: border-box;
    width: 300px;

    background: rgba(0, 0, 0, 0.493);
    margin-bottom: 20px;

    border-radius: 10px;
    padding: 20px;
  }
  .input {
    width: 100%;
    height: 20px;
  }

  .box__item-code {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
    width: 300px;
    height: 300px;
  }
  .shadow {
    background-color: rgba(0, 0, 0, 0.493);
    box-shadow: 15px 15px 10px rgba(0, 0, 0, 0.411);
  }
</style>
