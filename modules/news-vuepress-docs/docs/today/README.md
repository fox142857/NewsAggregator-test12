---
title: 今日新闻
description: 查看今日人民日报新闻
sidebar: auto
---

# 今日新闻

::: tip 提示
以下是最新的人民日报新闻汇总
:::

## 最近更新
<div id="current-date">
- [2025年04月08日人民日报](./today-news.md)
</div>

<script>
export default {
  mounted() {
    this.updateCurrentDate();
  },
  methods: {
    updateCurrentDate() {
      // 获取北京时间
      const now = new Date();
      const beijingOffset = 8; // 北京时间为UTC+8
      const utc = now.getTime() + (now.getTimezoneOffset() * 60000);
      const beijingTime = new Date(utc + (3600000 * beijingOffset));
      
      // 格式化日期为"YYYY年MM月DD日"
      const year = beijingTime.getFullYear();
      const month = String(beijingTime.getMonth() + 1).padStart(2, '0');
      const day = String(beijingTime.getDate()).padStart(2, '0');
      
      const dateString = `${year}年${month}月${day}日`;
      
      // 更新链接文本中的日期部分
      const dateElement = document.getElementById('current-date');
      if (dateElement) {
        dateElement.innerHTML = `- [${dateString}人民日报](./today-news.md)`;
      }
    }
  }
}
</script>

## 历史存档
暂无历史存档。新的新闻将在系统自动抓取后在此处显示。 