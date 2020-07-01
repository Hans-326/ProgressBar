<style lang="scss" scoped>
.progress-bar{
  width:260px;
  display: flex;
  align-items: center;
  color: #909399;
  .p-line{
    position: absolute;
    z-index: 1;
    width:100%;
    height: 7px;
    border-radius: 4px;
    background-color: #EEEEEE;
  }
  .p-done{
    position: absolute;
    z-index: 2;
    height: 7px;
    border-radius: 4px;
    background: linear-gradient(45deg, #0c9a62 25%, #0c9a62 0, #0c9a62 50%, #0c9a62 0, #0c9a62 75%, #0c9a62 0);
    background-size: 30px 30px;
  }
  .bottom-num{
    width: 60px;
    text-align: left;
    color: #606266;
    margin-left: 5px;
  }
  .progresscon {
    flex-grow: 1;
    display: flex;
    align-items: center;
    margin-left: 5px;

    .lincon {
        width: 100%;
        height: 7px;
        position: relative;
    }
  }
}
</style>
<template>
  <div class="progress-bar">
     <div class="title">
         <span>{{title}}</span>
     </div>
     <div class="progresscon">
        <div class="lincon">
            <div class="p-line"></div>
            <div class="p-done" :style="{width:doneWidth}"></div>
        </div>
        <div class="bottom-num">
        <!-- <div style="float:left">0</div> -->
            <div>{{drugCost}}/{{totalCost}}</div>
        </div>
     </div>
  </div>
</template>
<script>
export default {
    props: {
      title: {
          type: String,
          value: ''
      },
      totalCost: {
          type: Number,
          value: 0
      },
      drugCost: {
          type: Number,
          value: 0
      }
    },
    data(){
        return{
        }
    },
    computed:{
        ratio(){
            const r = this.drugCost/this.totalCost
            return r
        },
        doneWidth(){
            return this.drugCost/this.totalCost*100 + '%'
        }
    },
    created(){},
    mounted(){
    },
    methods:{
    
    }
}
</script>