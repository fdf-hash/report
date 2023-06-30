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
          对罚没进行管理、维护和完善相关功能
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
      tooltipLeft: 0,
    }
  },
  methods: {
    showTooltip(event) {
      this.showTooltipContent = true
      console.log(event);
      this.tooltipTop = event.offsetY + "px"
      this.tooltipLeft = event.offsetX + "px"
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
  background-color: #000;
  color: #fff;
  padding: 5px;
  border-radius: 5px;
  font-size: 14px;
}
</style>
