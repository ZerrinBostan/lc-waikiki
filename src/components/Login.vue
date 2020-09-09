<template>
  <form class="login" @submit.prevent="loginUser">
    <h4 class="font-weight-bold mb-0">ÜYE GİRİŞİ</h4>
    <Input
      name="email"
      type="email"
      icon="fas fa-envelope"
      placeholder="E posta Adresiniz"
      :callback="handleChangeEmail"
      @validate="validate('email')"
      :error="errors.email"
    />
    <Input
      name="password"
      type="password"
      icon="fas fa-key"
      placeholder="Şifreniz"
      :callback="handleChangePassword"
      @validate="validate('password')"
      :error="errors.password"
    />
    <div class="password-wrapper">
      <Checkbox label="Beni hatırla" />
      <a
        href="https://www.lcwaikiki.com/tr-TR/TR/sifremi-unuttum"
        class="password-forget"
        >Şifremi Unuttum</a
      >
    </div>
    <Button text="Giriş Yap" />
    <div class="sign-up-wrapper">
      <small class="sign-up-or">veya</small>
      <p class="sign-up-text">
        Henüz üye değil misin?
        <a
          href="https://www.lcwaikiki.com/tr-TR/TR/uye-ol"
          class="password-forget"
          >Üye ol</a
        >
      </p>
    </div>
  </form>
</template>

<script>
import { Input, Checkbox, Button } from "./index";
import { string, object } from "yup";

const loginFormSchema = object().shape({
  email: string()
    .email()
    .required(),
  password: string().required()
});

export default {
  name: "Login",
  components: {
    Input,
    Checkbox,
    Button
  },
  data: function() {
    return {
      values: {
        email: "",
        password: ""
      },
      errors: {
        email: "",
        password: ""
      }
    };
  },
  methods: {
    loginUser() {
      loginFormSchema
        .validate(this.values, { abortEarly: false })
        .then()
        .catch(err => {
          err.inner.forEach(error => {
            const customMessage = {
              email: "Lütfen e-posta adresinizi giriniz.",
              password: "Lütfen şifrenizi giriniz."
            };
            this.errors[error.path] = customMessage[error.path];
          });
        });
    },
    validate(field) {
      loginFormSchema
        .validateAt(field, this.values)
        .then(() => {
          this.errors[field] = "";
        })
        .catch(err => {
          switch (err.path) {
            case "email":
              this.errors.email = "Lütfen e-posta adresinizi giriniz.";
              break;
            case "password":
              this.errors.password = "Lütfen şifrenizi giriniz.";
              break;
            default:
              this.errors[err.path] = err.message;
          }
        });
    },
    handleChangeEmail(e) {
      this.values.email = e.target.value;
      console.log(this.values.email);
    },
    handleChangePassword(e) {
      this.values.password = e.target.value;
      console.log(this.values.password);
    }
  }
};
</script>
