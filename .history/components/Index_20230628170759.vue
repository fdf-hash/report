<template>
  <div>
    <ul>
      <li>
        <strong>资产管理</strong> - 对资产进行管理、使用、维护、费用收取等功能
      </li>
      <li><strong>职员管理</strong> - 职员信息的录入和维护</li>
      <li class="fm">
        <strong>罚没管理</strong>
        <span
          @mousemove="showTooltip"
          @mouseleave="hideTooltip"
          style="position: relative; cursor: pointer"
        >
           - 维护和完善一些功能
        </span>
        <div
          v-if="showTooltipContent"
          class="tooltip"
          :style="{top: tooltipTop+'px', left: tooltipLeft+'px'}"
        >
		<strong>罚没3个版本</strong><br>吴中区、相城区、高新区

		<strong>主开发吴中区</strong>
			修改吴中区的首页布局
			对接U8红冲开票的功能
			下载票据PDF
			修改菜单栏，调整顺序，修改名称
			分页新增全选、单选、批量开票、选中合计、默认合计
			汇总缴款书增加账单状态范围列表
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showTooltipContent: true,
      tooltipTop: 0,
      tooltipLeft: 280,
    }
  },
  methods: {
    showTooltip(event) {
      this.showTooltipContent = true
    },
    hideTooltip() {
      this.showTooltipContent = false
    },
  },
}
</script>

<style lang="scss" scoped>
ul{
    padding-top: 30px;
}
li{
    margin-bottom: 14px;
}
.fm{
    position: relative;
}
.tooltip {
  position: absolute;
  z-index: 1;
  color: #000;
  padding: 5px;
  border-radius: 5px;
  font-size: 14px;
}
</style>
