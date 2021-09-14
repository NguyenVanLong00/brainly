<template>
  <div class="container">
    <div class="login-wrapper componet">
      <div class="item">
        <h6 class="title">Let's find out</h6>
        <p class="sub-title">
          Find your account with email
        </p>
        <div class="login-form">
          <input
            type="text"
            class="input-pill"
            placeholder="Username or email"
          />
          <button class="button-pill">send email</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/auth.scss";

.or-hr {
  margin-top:24px;
}
</style>