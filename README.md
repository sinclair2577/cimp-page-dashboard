# 滨海城市工程群预警平台监测大屏

# 技术栈

1. React 18
2. Zustand (建议删掉，本项目里不存在全局变量使用)
3. Nextjs (本项目按 page 路由模式)
4. NextUI
5. TailwindCSS
6. Styled-component (建议全部用 tailwindcss 替换，存在不兼容问题)
7. Echarts
8. Axios
9. DataV-react (建议全部用 echart 替换，该仓库很久没有维护，存在版本不兼容问题)
10. Openapi-generator (默认路径为 api/generated，不要在其他位置生成 api)
11. Cesium (建议从 npm 安装，不要从本地引入)
12. Bimface SDK (本地引入)

# 项目结构

本项目是从 nextui 官方的模板项目构建，如有不属于以下位置的文件，均为默认生成的，非必要不改动：

```
- api               api接口服务
    - generated      自动生成的api
    - bimface        bimface api
- components 组件
    - config        配置
    - ***Components 页面***组件
    - layout        UI组件
    - common        通用组件
- mock       mock数据生成服务
- pages      路由页面
    - /path/to/page_name.tsx    路径名为 root/path/to/page_name的页面
    - index.tsx                 根目录“/”，默认跳转至home或登录页面
    - _app.tsx                  页面入口，这里可以处理一些全局逻辑
    - _document.tsx             页面入口，这里可以处理一些全局样式
    - _not_found.tsx            404页面
    - _error.tsx                错误页面
- model      数据模型
- store      状态管理
- config     配置，目前为模板默认生成
- constants  配置常量，建议删掉
- utils      工具函数
- public     公共资源，非必要不改动
- styles     样式，非必要不改动
- types      类型
```

# 部署方式

1. 环境配置见 [.env.development](.env.development), [.env.production](.env.production), 建议所有的配置都放在.env 文件中
2. 本项目采用 docker 部署，详见: [dockerfile](./dockerfile), [docker-compose.yaml](./docker-compose.yaml)
3. jenkins 集成脚本详见服务器示例

# Releases

- preview 0.1.1
  主要特性：

1. 项目群主页，项目预览，BIM 加载，数据图表加载

# 发布计划:

- preview 0.1.2

1. - [ ] 增加登录页面
2. - [x] 增加面包屑导航
3. - [x] 移除临时项目页面路径：eastStation，fengShouLakeMetroStation，mountainTunnel, 用一个接口对接所有的跳转
4. - [ ] 增加数据监测二级可视化页面
5. - [ ] 对接测点数据查询: 按 table 筛选查询
6. - [ ] 对接风险事件: 基于 nextui modal 操作
7. - [ ] 接入新的 GIS-BIM 可视化组件
8. - [x] 接入新的天气组件，删除导航栏上的日期
9. - [ ] 项目底部 6 个按键功能实现
10. - [ ] 常量和全局属性分离
11. - [ ] 使用 tailwindcss 替代 styled-component, 使用 echart 替代 datav-react, 删除所有非必要的 zustand
