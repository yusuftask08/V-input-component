<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="inputs">
      <Input size="large" placeholder="large ınput" />
      <Input size="medium" placeholder="medium ınput" />
      <Input size="small" placeholder="small ınput" />
    </div>
    <div class="inputs">
      <Input label="Large" size="large" placeholder="large ınput" />
      <Input label="Medium" size="medium" placeholder="medium ınput" />
      <Input label="small" size="small" placeholder="small ınput" />
    </div>
    <div class="inputs">
      <Input
        helper="Şifreniz 8 karakter olmalı"
        helperIcon="info"
        type="password"
        label="Large"
        size="large"
        placeholder="large ınput"
      />
      <Input
        helper="Şifreniz 8 karakter olmalı"
        helperIcon="info"
        type="password"
        label="Medium"
        size="medium"
        placeholder="medium ınput"
      />
      <Input
        helper="Şifreniz 8 karakter olmalı"
        helperIcon="info"
        type="password"
        label="small"
        size="small"
        placeholder="small ınput"
      />
    </div>
  </div>
</template>

<script>
import Input from "@/components/Input/index.vue";
export default {
  name: "App",
  components: {
    Input,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.inputs {
  display: flex;
  gap: 20px;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}
</style>