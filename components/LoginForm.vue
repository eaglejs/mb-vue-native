<template>
  <view class="flex-wrapper">
    <mb-card class="max-width-container">
      <mb-text-field id="username" label="Username" type="outlined" 
        v-model="loginModel.username" />
      <view class="input-wrapper">
        <mb-text-field id="password" label="Password" type="outlined" 
          v-model="loginModel.password" />
      </view>
      <view class="input-wrapper">
        <mb-select id="language" label="Language" type="outlined"
          menuItems="languages" v-model="loginModel.language" />
      </view>
      <view class="button-wrapper">
        <mb-button text="Login" type="contained" @press="goToEvent" />
      </view>
    </mb-card>
  </view>
</template>

<script>
export default {
  data: function() {
    return {
      loginModel: {
        username: "",
        password: "",
        language: ""
      },
      languages: ['English', 'Spanish', 'Japanese', 'French', 'German']
    };
  },
  props: {
    navigation: {
      type: Object
    }
  },
  methods: {
    goToEvent: function() {
      console.alert(this);
      this.navigation.navigate("Event");
    },
    showAlert: function () {
      console.alert('I am an alert!');
    }
  }
};
</script>

<style scoped lang="scss">
.max-width-container {
  margin-top: 50px;
  min-width: 300px;
  padding: 20px;
}
.flex-wrapper {
  align-items: center;
  display: flex;
  justify-content: center;
}
.input-wrapper {
  margin-top: 20px;
}
.button-wrapper {
  align-content: center;
  display: flex;
  justify-content: center;
  margin-top: 20px;
}
</style>