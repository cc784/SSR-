<template>
  <div style="padding:100px;">

   <div class="button" >
       <span 
       v-for="(item,index) in ['新闻','娱乐','体育']" :key='index'
        @click="handleCilick(index)"
        :class="{active: current === index}"
        >
         {{item}}
        </span>
    
     
   </div>
   
   <div   v-if="current === 0" >
       <ul>
           <li>新闻1111</li>
           <li>新闻1111</li>
           <li>新闻1111</li>
       </ul>
   </div>
   <div v-if="current === 1">
       <ul>
           <li>体育222</li>
           <li>体育222</li>
           <li>体育222</li>
       </ul>
   </div>
   <div v-if='current === 2'>
       <ul>
           <li>财经333</li>
           <li>财经333</li>
           <li>财经333</li>
       </ul>
   </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            //默认等于0
            current:0,
        }
    },
      methods: {
        handleCilick(index){
            this.current = index;
        }
    }
}
</script>

<style  scoped>
.button span {
    /* 光标 */
    cursor: crosshair ;
    padding-right: 20px;
}
.active{
    color:red;
}
</style>