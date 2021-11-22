<template>
  <div class="header">
    <Header title= "RoDev Market"/>
  </div>
  <div class="signup">
    
    <Button text="Sign Up!" color="green" />
  </div>
</template>

<script>
import Header from "../components/Header.vue"
import Button from "../components/Button.vue"

export default {
  name: 'SignUp',
  data() {
    return {
      username: "",
      password: "",
      userType: "",
    }
  },
  methods: {
    createUser() {
      if (this.username && this.password && this.userType != "") {
        console.log("New user")
      }
    },
  },
  components: {
    Header,
    Button,
  },
}
</script>
