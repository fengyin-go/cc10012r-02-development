<template>
  <div class="app-shell">
    <aside class="app-side">
      <h1 class="app-title">多维数据探查分析工具</h1>
      <nav class="nav-list">
        <RouterLink v-for="item in navItems" :key="item.path" :to="item.path" class="nav-item">
          {{ item.label }}
        </RouterLink>
      </nav>
    </aside>
    <main class="app-main">
      <header class="app-head">
        <span class="head-desc">离线版多维数据探查分析工具，涵盖数据源接入、交互查询、聚合统计、图表看板、预警通知与数据导出，所有分析配置与结果持久化到浏览器本地存储。</span>
        <span class="head-user">当前值班：{{ store.operator }} · {{ store.shiftLabel }}</span>
      </header>
      <RouterView />
    </main>
  </div>
</template>

<script setup lang="ts">
import { useSessionStore } from '@/stores/session'

const store = useSessionStore()

const navItems = [{ label: "运营概览", path: "/" }, { label: "交互查询", path: "/query" }, { label: "可视化图表", path: "/chart" }, { label: "数据源接入", path: "/source" }, { label: "聚合计算", path: "/aggregate" }, { label: "数据筛选", path: "/filter" }, { label: "报告生成", path: "/reportgen" }, { label: "异常检测", path: "/anomaly" }, { label: "多维下钻", path: "/drill" }, { label: "对比分析", path: "/compare" }, { label: "分析流水线", path: "/pipeline" }, { label: "数据集管理", path: "/datastore" }, { label: "趋势预测", path: "/forecast" }, { label: "预警通知", path: "/alert" }, { label: "查询缓存", path: "/cache" }, { label: "数据标签", path: "/tag" }, { label: "数据导出", path: "/export" }, { label: "数据分享", path: "/share" }, { label: "定时任务", path: "/schedule" }]
</script>
