<template>
  <div>
    <p>- [{{ currentDate }}人民日报](./today-news.md)</p>
  </div>
</template>

<script>
export default {
  name: 'CurrentDate',
  data() {
    return {
      currentDate: '2025年04月08日' // 默认值，在客户端渲染时会被替换
    }
  },
  mounted() {
    // 获取北京时间
    const now = new Date()
    const beijingOffset = 8 // 北京时间为UTC+8
    const utc = now.getTime() + (now.getTimezoneOffset() * 60000)
    const beijingTime = new Date(utc + (3600000 * beijingOffset))
    
    // 格式化日期为"YYYY年MM月DD日"
    const year = beijingTime.getFullYear()
    const month = String(beijingTime.getMonth() + 1).padStart(2, '0')
    const day = String(beijingTime.getDate()).padStart(2, '0')
    
    this.currentDate = `${year}年${month}月${day}日`
  }
}
</script> 