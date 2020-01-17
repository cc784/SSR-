<template>
    <div class="container">
        <!-- 幻灯片 -->
      	<!-- 轮播图 -->
		<el-carousel height="700px" class="carousel">
			<el-carousel-item v-for="(item, index) in banners" :key="index">
				<div class="banner banner-image" :style="`background:url(${$axios.defaults.baseURL + item.url}) center center no-repeat;`"></div>
			</el-carousel-item>
		</el-carousel>
    <!--  -->
    
    </div>
</template>

<script>
export default {
    data(){
        return {
            // 轮播图数据
            banners: [],
        }
    },
  mounted(){
    // $axios是挂载个实例下的axios方法
    this.$axios({
      url: "/scenics/banners"
    }).then(res => {
      const {data} = res.data;
      // 服务器的轮播图数据
      this.banners = data;


      
    })
  }
}
</script>

<style scoped lang="less">
.container{
    min-width:1000px;
    margin:0 auto;
    position:relative;

    /deep/ .el-carousel__container{
        height:700px;
    }

    .banner-image{
        width:100%;
        height:100%;
    }
}
</style>