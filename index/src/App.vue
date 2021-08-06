<template>
  <div id="app">
    <el-row :gatter="10" style="height:100%">
      <!--top-menu-small-->
      <el-col :xs="24" :sm="24" :md="5"  :lg="5" style="background-color:#545c64;min-height:40px" class="hidden-md-and-up">
        <h1 style="color:white;text-align:center;padding:5px;margin:0"><i class="el-icon-s-custom" style="color:#67C23A"></i> Admin<el-button type="primary" icon="el-icon-menu" style="font-size: 16px;float:right" ></el-button></h1>
        
      </el-col>
      <!--left-menu-normal-->
      <el-col :xs="24" :sm="24" :md="5" :lg="5" style="background-color:#545c64; min-height:900px" class="hidden-sm-and-down">
        <h1 style="color:white;text-align:center;"><i class="el-icon-s-custom" style="color:#67C23A"></i> Admin</h1>
        
           <el-image v-if="userInfo.userAvatar" shape="square" fit="fill" :src="userInfo.userAvatar"></el-image>
          
      <el-menu
      default-active="1"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b"
      router="true">
         <el-menu-item index="1" route="/">
          <i class="el-icon-s-home"></i>
          <span>HOME</span>
        </el-menu-item>
        <el-menu-item index="2" route="/Explore">
        <i class="el-icon-guide"></i>
        <span slot="title">EXPLORE</span>
      </el-menu-item>
        <el-menu-item index="3" route="/Editor">
        <i class="el-icon-suitcase-1"></i>
        <span slot="title">EDITOR</span>
      </el-menu-item>
        <el-menu-item index="4" route="/Demo">
        <i class="el-icon-cpu"></i>
        <span slot="title">DEMO</span>
      </el-menu-item>
        <el-menu-item index="5" route="/Notes">
        <i class="el-icon-collection"></i>
        <span slot="title">NOTES</span>
      </el-menu-item>
            <el-menu-item index="6" route="/Documents">
        <i class="el-icon-reading"></i>
        <span slot="title">DOCUMENTS</span>
      </el-menu-item>
      <el-menu-item index="7" route="/FeedBack">
        <i class="el-icon-s-comment"></i>
        <span slot="title">FEEDBACK</span>
      </el-menu-item>
      <el-menu-item index="8">
        <i class="el-icon-caret-top" route="/Login"></i>
        <span slot="title">SIGN OUT</span>
      </el-menu-item>
    </el-menu>
      </el-col>
      <!--index view-->
      <el-col :xs="24" :sm="24" :md="19" :lg="19" style="background-color:#efefef;min-height:850px;padding:50px;display:block">
        <router-view/>
        </el-col>
    </el-row>
  </div>
</template>

<script>
import userAvatar from './assets/profile-photo.jpg'
export default {
  name: 'App',
  data() {
    return {
        userInfo:{
          userAvatar:require('./assets/profile-photo.jpg')
        }
    }
  }
}
</script>

<style>
body{
 margin:0;
 padding:0;
}
</style>

