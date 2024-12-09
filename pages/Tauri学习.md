- 前端学习
	- **CSS**
	- **HTML**
	- **JavaScript/TypeScript**
	- **Vue** [https://cn.vuejs.org/](https://cn.vuejs.org/)
		- 路由（[Vue Router](https://router.vuejs.org/zh/)）
			- 安装路由
				- `pnpm add vue-router@4`
			- 获取当前路由路径 {{cloze {{ $route.fullPath }}}}
			- 创建路由链接 {{cloze `RouterLink`}}
			- 渲染路由 {{cloze `RouterView`}}
			- 创建路由实例
			  collapsed:: true
				- `createRouter`
				  ```javascript
				  import { createMemoryHistory, createRouter } from 'vue-router'
				  
				  import HomeView from './HomeView.vue'
				  import AboutView from './AboutView.vue'
				  
				  const routes = [
				    { path: '/', component: HomeView },
				    { path: '/about', component: AboutView },
				  ]
				  
				  const router = createRouter({
				    history: createMemoryHistory(),
				    routes,
				  })
				  ```
			- 命名路由
			  collapsed:: true
				- 使用命名路由的好处
				  collapsed:: true
					- 没有硬编码的 URL
					- `params` 的自动编码/解码
					- 防止你在 URL 中出现打字错误
					-
				- 使用 `name` 属性创建命名路由
				- ```typescript
				  const routes: Array<RouteRecordRaw> = [
				    {
				      path: '/',
				      component: HomeView,
				      name: 'home' // 使用 name 属性创建命名路由
				    },
				    {
				      path: '/about',
				      component: AboutView,
				      name: 'about'
				    }
				  ]
				  ```
				- 使用命名路由
					- ```vue
					  <RouterLink :to="{ name: 'about' }">
					  	<span class="xtp-icon iconfont icon-l-about"></span>
					  </RouterLink>
					  
					  <RouterLink :to="{ name: 'user', params: { id: 12 } }">
					  	<span class="xtp-icon iconfont icon-setting"></span> User
					  </RouterLink>
					  ```
			- 动态路由
				- ```typescript
				  const routes: Array<RouteRecordRaw> = [
				  	{
				        path: '/users/:id',
				        component: UserView,
				        name: 'user',
				  	}
				  ]
				  ```
				- ```vue
				  <RouterLink :to="{ name: 'user', params: { id: 12 } }">
				  	<span class="xtp-icon iconfont icon-setting"></span> User
				  </RouterLink>
				  ```
				- ```vue
				  <template>
				    <h1>User</h1>
				    <p>UserId: {{ $route.params.id }}</p>
				  </template>
				  ```
			- 编程式导航
			-
			-
		- 状态管理（[Pinia](https://pinia.vuejs.org/zh/)）
		- 基础语法
		-
- 后端学习
	- Rust
-
-