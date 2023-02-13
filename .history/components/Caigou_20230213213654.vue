<template>
    <div class="box">
        <!-- <img src="../static/img/caigou.png" alt=""> -->
        <div class="item" style="background: #fb051e;">参数设置</div>
        <div class="item" style="background: #fb051e;">采购过程配置</div>
        <div class="item" style="background: #fb051e;">采购计划申请</div>
        <div class="item" style="background: #fb051e;">采购计划变更</div>
        <div class="item" style="background: #fb051e;">采购立项</div>
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
        padding: 6px 10px;
        text-align: center;
        margin:24px 24px 40px 24px;
        box-shadow:0px 0px 6px rgb(0, 0, 0,0.5);
        border: 0px solid rgb(230, 243, 213);
        border-radius: 10px;
        font-size: 16px;
        background-color: rgb(55, 124, 250);
        color: #fff;
    }
</style>
