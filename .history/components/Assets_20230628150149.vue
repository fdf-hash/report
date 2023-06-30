<template>
    <div class="menu">
      <h2>资产管理</h2>
      <ul>
        <li>资产明细</li>
        <li>资产记录</li>
        <li>资产入库</li>
        <li>资产领用</li>
        <li>资产盘点</li>
        <li>资产调入</li>
        <li>资产调出</li>
        <li>资产注销</li>
        <li>资产出借</li>
      </ul>
  
      <h2>经营性资产管理</h2>
      <ul>
        <li>部位管理</li>
        <li>经营性资产合同</li>
        <li>租金减免</li>
        <li>收租管理</li>
        <li>退租管理</li>
      </ul>
  
      <h2>抄表管理</h2>
      <ul>
        <li>总表管理</li>
        <li>抄表-总表</li>
        <li>抄表-子表</li>
      </ul>
  
      <h2>费用管理</h2>
      <ul>
        <li>杂费管理</li>
        <li>物业公司管理</li>
        <li>物业费管理</li>
      </ul>
  
      <h2>租客管理</h2>
      <ul>
        <li>租客管理</li>
      </ul>
  
      <h2>维修管理</h2>
      <ul>
        <li>维修申请</li>
        <li>维修费用报销</li>
      </ul>
  
      <h2>职员管理</h2>
      <ul>
        <li>职员信息</li>
      </ul>
    </div>
  </template>
  
  <style lang="scss">
  .menu {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  
    h2 {
      width: 100%;
      margin-bottom: 10px;
      font-size: 18px;
    }
  
    ul {
      list-style: none;
      padding: 0;
      margin: 0;
  
      li {
        padding: 10px;
        background-color: #f2f2f2;
        border-radius: 4px;
        cursor: pointer;
  
        &:hover {
          background-color: #e6e6e6;
        }
      }
    }
  }
  </style>
  