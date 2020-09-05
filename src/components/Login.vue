<template>
  <div class="login">
    <h4 class="font-weight-bold mb-0">ÜYE GİRİŞİ</h4>
    <Input
      input_type="email"
      icon="fas fa-envelope"
      placeholder="E posta Adresiniz"
    />
    <Input input_type="password" icon="fas fa-key" placeholder="Şifreniz" />
    <div class="password-wrapper">
      <Checkbox label="Beni hatırla" />
      <a href="https://www.google.com" class="password-forget"
        >Şifremi Unuttum</a
      >
    </div>
    <Button text="Giriş Yap" />
    <div class="sign-up-wrapper">
      <small class="sign-up-or">veya</small>
      <p class="sign-up-text">
        Henüz üye değil misin?
        <a href="https://www.google.com" class="password-forget">Üye ol</a>
      </p>
    </div>
  </div>
</template>

<script>
import Input from "./Input";
import Checkbox from "./Checkbox";
import Button from "./Button";

export default {
  name: "Login",
  components: {
    Input,
    Checkbox,
    Button
  }
};
</script>
