<template>
    <img class="gravatar" :src="url">
</template>

<script>
import md5 from "js-md5";
export default {
  name: "gravatar",
  data: () => {
    return {
      url: "",
      email: "MyCrown1234@hotmail.com"
    }
  },
  mounted() {
    const that = this;
    let email = md5(that.email.toLowerCase());
    that.url = "https://www.gravatar.com/avatar/" + email;
  }
}
</script>

<style lang="less">
.gravatar {
  width: 100%;
  height: 100%;
}
</style>
