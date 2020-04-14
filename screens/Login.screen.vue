<template>
  <view>
    <LoginForm></LoginForm>
  </view>
</template>

<script>
import LoginForm from "../components/LoginForm.vue";

export default {
  data: function() {
    return {
      title: "Login"
    };
  },
  components: {
    LoginForm
  }
};
</script>
