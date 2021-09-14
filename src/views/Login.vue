<template>
  <div class="container">
    <div class="login-wrapper componet">
      <div class="item">
        <h6 class="title">Welcome again</h6>
        <p class="sub-title">
          Get answers within minutes so you can finish your homework faster
        </p>
        <div class="login-form">
          <input
            type="text"
            class="input-pill"
            placeholder="Username or email"
          />
          <input
            type="password"
            class="input-pill"
            placeholder="Enter password"
          />
          <button class="button-pill">log in</button>
        </div>
        <div class="forgot-password cap2">
          <router-link :to="{ name: 'ForgotPassword' }"
            >FORGOT YOUR PASSWORD?</router-link
          >
        </div>
        <div class="or-hr cap2">
          <div>
            <span> OR </span>
          </div>
        </div>

        <div class="login-third-party">
          <div class="login-google button-pill flex-center">
            <div class="icon">
              <img :src="google_icon" alt="google icon" />
            </div>
            <div>
              google
            </div>
          </div>
          <div class="login-facebook button-pill flex-center">
             <div class="icon">
              <img :src="facebook_icon" alt="facebook icon" />
            </div>
            <div>
              google
            </div>
          </div>
        </div>

        <p class="promiss cap">We never share anything on your behalf</p>
      </div>
    </div>
  </div>
</template>

<script>
import facebook_icon from '../assets/icons/facebook.png';
import google_icon from '../assets/icons/google.png';

export default {
  data(){
    return {
      facebook_icon,
      google_icon
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/auth.scss";
</style>