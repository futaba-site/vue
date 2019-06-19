<template>
  <div class="home">
    <div class="cover">
      <div class="cover__info">
        <div class="cover__avatar"><gravatar /></div>
        <div class="cover__hitokoto">
          <p class="hitokoto__content">{{hitokoto.hitokoto}}</p>
          <p class="hitokoto__from">From {{hitokoto.from}}</p>
        </div>
      </div>
    </div>
    <div class="section">
      <div class="posts">
        <div class="section__title">POSTS</div>
        <div class="post">
          <div class="post__image"></div>
          <div class="post__info">
            <div class="post__time"></div>
            <div class="post__title"></div>
            <div class="post__tag"></div>
            <div class="post__content"></div>
            <div class="post__more"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import gravatar from "@/components/gravatar";
import axios from "axios";
export default {
  name: "home",
  components: {
    gravatar
  },
  data: () => {
    return {
      hitokotoUrl: "https://v1.hitokoto.cn?c=a&&encode=json&&charset=utf-8",
      hitokoto: {
        hitokoto: "",
        from: ""
      }
    }
  },
  mounted() {
    const that = this;
    axios.get(that.hitokotoUrl).then((response)=> {
      console.log(response);
      that.hitokoto = {...response.data};
    }).catch((error) => {
      console.log(error);
    })
  }
};
</script>

<style <style lang="less">
.cover {
  width: 100%;
  height: 100vh;
  .cover__info {
    display: flex;
    flex-direction: column;
    align-items: center;
    .cover__avatar {
      width: 80px;
      height: 80px;
      border-radius: 40px;
      overflow: hidden;
    }
    .cover__hitokoto {
      display: inline-block;
      padding: 15px;
      border-radius: 4px;
      background-color: rgba(0,0,0,.3);

      p {
        margin: 0;
        line-height: 24px;
        font-size: 13px;
      }
      .hitokoto__from {
        text-align: right;
        font-size: 12px;
      }
    }
  }
}

.section {
  width: 1000px;
  margin: 0 auto;

  .posts {
    width: 100%;

    .post {
      
    }
    .post__odd {

    }
    .post__even {

    }
  }
}
</style>

