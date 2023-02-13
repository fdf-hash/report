<template>
    <div class="box">
        <!-- <img src="../static/img/caigou.png" alt=""> -->
        <div class="item">参数设置</div>
        <div class="item">采购过程配置</div>
        <div class="item">采购计划申请</div>
        <div class="item">采购计划变更</div>
        <div class="item">采购立项</div>
        <div class="item">采购申请</div>
        <div class="item">招标申请</div>
        <div class="item">中标管理</div>
        <div class="item">合同管理</div>
        <div class="item">合同变更</div>
        <div class="item">合同验收</div>

    </div>
</template>

<style lang="scss" scoped>
    *{
        margin: 0px;
        padding: 0px;
        box-sizing: border-box;
        font-family: sans-serif;
    }
    img{
       width: 550px;
       height: auto; 
       margin: 20px 0;
    }
    .box{
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: space-between;
        margin-top: 40px;
    }
    .item{
        padding: 10px;
        text-align: center;
        margin:24px 24px 60px 24px;
        box-shadow: 1px 1px rgb(230, 243, 213);
        border: 2px solid rgb(230, 243, 213);
        border-radius: 20px;
        font-size: 16px;
    }
</style>
