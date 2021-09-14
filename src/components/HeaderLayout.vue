 <template>
  <header class="header">
    <div class="container">
      <div class="logo">
        <router-link :to="{ name: 'Home' }">
          <img :src="logo" alt="brainly logo" />
        </router-link>
      </div>
      

      <div class="search flex-center" v-if="isLogin">
        
        <div class="searchbar">
          <input type="text" class="input" />
        </div>
        
        <div class="icon">
          <img :src="search" />
        </div>

      </div>

      <div class="chat " v-if="isLogin">
        <div class="icon">
          <img :src="chat" />
        </div>
      </div>

      <div class="noti " v-if="isLogin">
        <div class="icon">
          <img :src="bell" />
        </div>
      </div>


      <div class="auth" v-if="!isLogin">
        <div class="login button" :class="{ active: currentRoute == 'Login' }">
          <router-link :to="{ name: 'Login' }">log in</router-link>
        </div>
        <div class="line"></div>
        <div
          class="signup button"
          :class="{ active: currentRoute == 'Signup' }"
        >
          <router-link :to="{ name: 'Signup' }">sign up</router-link>
        </div>
      </div>
      <div v-else class="auth logined">
        <div class="avatar">
          <img :src="user.img" />
        </div>
        <h6 class="user-name m-0">{{ user.name }}</h6>
      </div>
    </div>
  </header>
</template>

<script>
import logo from "../assets/images/logo_brainly.png";
import search from "../assets/icons/search.png";
import bell from "../assets/icons/bell.png";
import chat from "../assets/icons/chat.png";

export default {
  props: ["user"],
  data() {
    return {
      logo: logo,
      search: search,
      bell: bell,
      chat: chat,
    };
  },
  computed: {
    currentRoute() {
      return this.$route.name;
    },
    isLogin() {
      return this.user != null;
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  grid-template-rows: 68px;
}
.logo {
  grid-column-start: 1;
  grid-column-end: 2;
  img {
    object-fit: cover;
    height: 100%;
  }
}
.auth {
  grid-column-end: -1;
  grid-column-start: 10;
  display: flex;
  justify-content: flex-end;
  align-items: center;
}
.logined {
  grid-column-start: 11;
}
.avatar {
  margin-right: 14px;
  height: 32px;
  width: 32px;
  img {
    border-radius: 50%;
    width: 100%;
  }
}
.chat, .noti {
  align-self: center;
  justify-self: center;
}
.search {
  grid-column-start: 6;
  grid-column-end: 9;
  .input{
    display: inline-block;
  }
  .icon {
    margin-left: 12px;
    width: fit-content;
    height: 32px;
  }
}
.searchbar {
  flex:1;
  input {
    width: 100%;
    transition: 0.3s;
  }
}

</style>