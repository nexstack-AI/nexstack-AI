# nexstack-AI

> 空与栈的交汇处。void where stacks align.
>
> AI 全栈开发者 | 构建务实、高效的工程体系

---

## 近期动态

> 像写日志一样更新这里——每完成一件事，加一条在最上面。

### 2026-05-14

- **GitHub 体系上线** — 个人主页 + vitedome 全栈框架 + nexstack-miniapp 小程序框架，三仓就绪
- **小程序框架搭建** — Taro 4.x + React 18 + TypeScript，移植 useRequest / useInViewRequest 核心 hooks
- **vitedome 完整版推送** — React 19 + Vite + Express + SQLite + Drizzle ORM，71 文件全量上线

---

## 项目

| 项目 | 说明 | 技术栈 |
|---|---|---|
| [**vitedome**](https://github.com/nexstack-AI/vitedome) | React 19 + Vite 全栈基础框架 | React / Express / SQLite / Drizzle |
| [**nexstack-miniapp**](https://github.com/nexstack-AI/nexstack-miniapp) | 小程序快速开发框架 | Taro / React / TypeScript |

---

## 技术笔记

> 随手记录，没有形式要求。

### useRequest Hook —— 通用异步请求管理

封装了 loading / error / data 三态，支持防抖节流、手动触发、依赖刷新。核心思路是把"请求"变成一个可观测的状态机。

```typescript
const { data, loading, error, run, refresh } = useRequest(fetchUser)
```

### useInViewRequest —— 视口懒加载请求

在 useRequest 基础上加了 IntersectionObserver。元素进入视口才发请求，减少首屏并发。适配了浏览器版（原生 IntersectionObserver）和 Taro 版（Taro.createIntersectionObserver）。

### 环境策略：Mock / 代理 / 生产 三模切换

通过一个环境变量 `VITE_USE_MOCK` 控制：
- `true` → 本地 Mock 插件拦截
- `proxy` → Vite 代理到 Express 后端
- 生产环境 → 直连正式 API

---

## 联系

- Email: xudongdong502@gmail.com
- GitHub: [@nexstack-AI](https://github.com/nexstack-AI)

---

*规则更新日：2026-05-14 | 星*