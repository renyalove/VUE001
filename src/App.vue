<template>
  <div class="app-container"> 

    
    <mt-header fixed title="我的vue项目--商城"></mt-header>
    <transition>
		<router-view></router-view>
	</transition>
    <nav class="mui-bar mui-bar-tab">
			<router-link class="mui-tab-item-llb " to="/home">
				<span class="mui-icon mui-icon-home"></span>
				<span class="mui-tab-label">首页</span>
			</router-link >
			<router-link  class="mui-tab-item-llb" to="/member">
				<span class="mui-icon mui-icon-contact"> </span> 
				<span class="mui-tab-label">会员</span>
			</router-link >
			<router-link  class="mui-tab-item-llb" to="/shopcar">
        <!-- 复制过来的没有mui-icon 需要手动加上，否则没有样式 -->
				<span class=" mui-icon  mui-icon-extra mui-icon-extra-cart"><span class="mui-badge">0</span></span> 
			 
      	<span class="mui-tab-label">购物车</span>
			</router-link >
			<router-link  class="mui-tab-item-llb" to="/search">
				<span class="mui-icon mui-icon-search"></span>
				<span class="mui-tab-label">搜索</span>
			</router-link >
		</nav>
  </div>
</template>

<script>
 

 
   
</script>
 <style lang="scss" scoped>
  .app-container{
    padding-top: 40px;
	//解决切换时顶部底部也跟着动的问题，因为有滚动条
	overflow-x: hidden
  }
  .v-enter{
	  opacity: 0;
	  transform: translateX(100%)

  }
    .v-leave-to{
	  opacity: 0;
	  transform: translateX(-100%);
	  position: absolute;//解决切换时的漂浮问题

  }
  .v-enter-active,
  .v-leave-active{
	  opacity: 0;
	  transition: all 0.3s ease;
  }

  * { touch-action: pan-y; } 
  // 该类名，解决 tabbar 点击无法切换的问题
.mui-bar-tab .mui-tab-item-llb.mui-active {
    color: #007aff;
}

.mui-bar-tab .mui-tab-item-llb {
    display: table-cell;
    overflow: hidden;
    width: 1%;
    height: 50px;
    text-align: center;
    vertical-align: middle;
    white-space: nowrap;
    text-overflow: ellipsis;
    color: #929292;
}

.mui-bar-tab .mui-tab-item-llb .mui-icon {
    top: 3px;
    width: 24px;
    height: 24px;
    padding-top: 0;
    padding-bottom: 0;
}

.mui-bar-tab .mui-tab-item-llb .mui-icon~.mui-tab-label {
    font-size: 11px;
    display: block;
    overflow: hidden;
    text-overflow: ellipsis;
}
 </style>
