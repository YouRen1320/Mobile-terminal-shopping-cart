# Vue3 移动端购物车项目

> [!IMPORTANT]
> **历史学习项目，已停止维护。** 本仓库只包含前端，不包含后端；接口指向 `http://localhost:3001/api/` 占位地址，仓库中也没有可用的服务端实现。因此首页商品列表、商品详情、购物车增删改查、登录注册、头像上传等依赖接口的功能在当前状态下均无法真实使用。较新的配套练习请查看 [商城前端](https://github.com/YouRen1320/shopping_cart_frontEnd) 与 [商城后端](https://github.com/YouRen1320/shopping_cart_afterEnd)。代码和提交历史继续保留，供学习参考。

## 项目介绍

基于 Vite 与 Vue 3 创建的移动端网页购物车应用练习，包含电商常见页面的前端实现：首页商品列表、商品详情、购物车、个人中心、设置、登录与注册。

## 已实现 / 未实现

**已实现（前端代码层面）：**

- 页面结构与路由：底部标签导航（首页 / 购物车 / 我的）、二级页面与登录守卫标记
- 请求封装：axios 实例与请求 / 响应拦截器，错误统一走 Vant 通知
- 各页面的界面代码与交互逻辑（商品列表加载、购物车操作、登录 / 注册表单、头像上传界面）
- 登录态标记：`localStorage` 中记录 `utoken` 与 `userid` 并随请求携带

**未实现 / 不可用：**

- 后端服务：仓库不含任何服务端代码，`localhost:3001` 仅为开发时的占位地址
- 因此所有数据功能（商品列表、详情、购物车数据、登录注册、头像上传）在无后端时都无法真实工作，页面表现为接口报错
- 自动化测试：本项目没有测试代码

## 技术栈

- Vue 3（选项式 API，JavaScript）
- Vite 5（构建工具）
- Vant 4（移动端组件库，通过 unplugin-vue-components 按需自动导入）
- Vue Router 4（Hash 模式）
- Axios（请求封装）
- Sass（样式）
- pnpm（依赖管理）、ESLint / Prettier（代码规范）

## 快速开始

环境要求：Node.js ≥ 18，包管理器 pnpm（或 npm）。

```bash
# 1. 克隆项目
git clone https://github.com/YouRen1320/Mobile-terminal-shopping-cart.git
cd Mobile-terminal-shopping-cart

# 2. 安装依赖
pnpm install

# 3. 启动开发服务器（默认 http://localhost:5173）
pnpm dev

# 4. 生产构建（产物在 dist/）
pnpm build
```

> [!NOTE]
> 仓库内置了 `pnpm-workspace.yaml`，已将 `esbuild` 声明为允许执行安装脚本的依赖。pnpm ≥ 10 默认拦截依赖的构建脚本，若你在自己的环境里遇到 `ERR_PNPM_IGNORED_BUILDS`，可运行 `pnpm approve-builds --all` 或参照该文件配置。

## 目录结构

```
├── public/               # 静态资源（favicon）
├── src/
│   ├── assets/           # 全局样式与静态资源
│   ├── router/           # 路由配置（Hash 模式，含登录守卫标记）
│   ├── utils/
│   │   └── http.js       # axios 封装：baseURL 指向本地占位接口，含拦截器
│   └── views/            # 页面：首页、购物车、我的、设置、朋友、详情、
│                         #   编辑资料、登录、注册
├── vite.config.js        # Vite 配置（@ 别名、Vant 按需导入、自动导入）
└── pnpm-workspace.yaml   # pnpm 构建脚本白名单（esbuild）
```

## 与新商城练习的关系

本项目是最早的移动端购物车练习，缺少后端与状态管理。之后重写的 [shopping_cart_frontEnd](https://github.com/YouRen1320/shopping_cart_frontEnd)（Vue 3 + TypeScript）与 [shopping_cart_afterEnd](https://github.com/YouRen1320/shopping_cart_afterEnd)（配套后端）是更完整的版本，适合作为学习参考的主入口。

## 许可证

[MIT](./LICENSE)
