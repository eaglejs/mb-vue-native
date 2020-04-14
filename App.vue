<template>
  <!-- <status-bar background-color="#3f51b5"></status-bar>
  <mb-appbar color="#3f51b5"></mb-appbar> -->
  <AppNavigator></AppNavigator>
</template>

<script>
import Vue from "vue-native-core";
import { VueMaterialBread } from "material-bread";
import {
  createAppContainer,
  createStackNavigator,
  createDrawerNavigator
} from "vue-native-router";

import LoginScreen from "./screens/Login.screen.vue";
import EventScreen from "./screens/Event.screen.vue";
import LoginForm from "./components/LoginForm.vue";

const DrawerNavigator = createDrawerNavigator(
  {
    Login: LoginScreen,
    Event: EventScreen
  },
  {
    initialRouteName: "Login"
  }
);
const StackNavigator = createStackNavigator({
  Drawer: DrawerNavigator,
  Login: LoginScreen,
  Event: EventScreen
});
const AppNavigator = createAppContainer(StackNavigator);

// registering all components to the global scope of the Vue
Vue.use(VueMaterialBread);
export default {
  components: { AppNavigator }
};
</script>
