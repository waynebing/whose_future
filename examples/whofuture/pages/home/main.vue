<template>
  <div class="container">
	  这里是首页
      <!-- 图片引用的两种方式 -->
      <!-- <img class="girl" :src="imgSrc +'/girl.png'" alt=""> -->
      <!-- <img class="logo" src="../../assets/logo.png" alt=""> -->
    <!-- <card :text="motto"></card> -->
    <form class="form-container">
      <input type="text" class="form-control" v-model="motto" placeholder="v-model" />
      <input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy" />
    </form>
  </div>
</template>

<script>
// 组件引用

export default {
  data () {
    return {
      motto: 'Hello World'
    }
  },
  components: {
    
  },
  methods: {
     
  }
}
</script>

<style>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128/7.5vw;
  height: 128/7.5vw;
  margin: 20/7.5vw;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
  height:25px;
    text-overflow:clip;
    overflow:hidden;
    white-space:nowrap;
    -webkit-tap-highlight-color: rgba(255, 255, 255, 0);
  -webkit-user-select: none;
  -moz-user-focus: none;
  -moz-user-select: none;
  -webkit-appearance:none;
  outline: none;
}

.counter {
  display: inline-block;
  margin: 10px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
.container .girl{
    width: 275px;
    height: 400px;
}
.container .logo{
    width: 200px;
    height: 200px;
}

</style>
