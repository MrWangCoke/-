# -
简单的课设，只做了部分功能
让ai写的README

#🎓 大创项目管理平台 (Innovation Project Management System)

基于 **Vue 3** + **Spring Boot** 的前后端分离项目管理系统。
该系统主要用于高校大学生创新创业训练项目的**申报、审核、管理**流程。

> **当前版本特性**：
> * 🚀 **极速启动**：后端采用内存模拟数据库模式，无需安装 MySQL 即可直接运行演示。
> * ✨ **前后端分离**：标准的企业级开发架构。
> 
> 

## 🛠️ 技术栈 (Tech Stack)

### 前端 (Frontend) - `manage` 文件夹

* **框架**：Vue 3 (Composition API)
* **构建工具**：Vite
* **UI 组件库**：Element Plus
* **路由**：Vue Router
* **网络请求**：Axios

### 后端 (Backend) - `managejava` 文件夹

* **核心框架**：Spring Boot 3.x / 4.x
* **语言**：Java (JDK 17+)
* **工具库**：Lombok, EasyExcel (用于导出数据)
* **数据存储**：Memory Mode (当前版本数据存储在内存 List 中，重启后重置)

---

## 📂 项目结构 (Structure)

```text
Project_Root/
├── manage/                 # 🟢 前端项目
│   ├── src/
│   │   ├── views/          # 页面 (Login, Student, Admin)
│   │   ├── components/     # 公共组件
│   │   ├── router/         # 路由配置
│   │   └── ...
│   ├── package.json
│   └── vite.config.js
│
└── managejava/             # 🔵 后端项目
    ├── src/main/java/org/example/managejava/
    │   ├── controller/     # 接口层 (Web API)
    │   ├── service/        # 业务逻辑层 (模拟数据在这里)
    │   ├── entity/         # 实体类 (User, Project)
    │   ├── dto/            # 数据传输对象
    │   └── config/         # 配置类 (跨域配置)
    └── pom.xml             # Maven依赖配置

```

---

## ⚡️ 快速开始 (Quick Start)

由于是前后端分离项目，需要**同时启动**前端和后端。

### 1. 启动后端 (Backend)

1. 使用 **IntelliJ IDEA** 打开 `managejava` 文件夹。
2. 等待 Maven 加载依赖（如果没有自动加载，点击右上角的刷新按钮）。
3. 找到 `ManagejavaApplication.java`，点击绿色运行按钮。
4. 看到控制台输出 `Tomcat started on port 8080` 即表示启动成功。

### 2. 启动前端 (Frontend)

1. 使用 **VS Code** 或 **WebStorm** (或 IDEA) 打开 `manage` 文件夹。
2. 打开终端 (Terminal)，运行以下命令安装依赖：
```bash
npm install

```


3. 启动项目：
```bash
npm run dev

```


4. 看到输出 `Local: http://localhost:5173/` 即表示启动成功。

---

## 🖥️ 功能与使用 (Features & Usage)

访问浏览器地址：`http://localhost:5173/`

### 1. 登录 (Login)

系统根据账号自动判断身份。

* **管理员账号 (二级管理员)**：
* 账号：`admin`
* 密码：`123456`
* *注意：登录页身份必须选择“二级管理员”*


* **学生账号**：
* 账号：任意（例如 `2021001` 或 `student`）
* 密码：`123456`
* *注意：登录页身份必须选择“学生”*



### 2. 学生端功能

* **项目申请**：填写项目名称、级别、类别、指导老师等信息并提交。
* **我的项目**：查看已提交项目的状态（审核中/已通过/已驳回）。

### 3. 管理员端功能

* **项目列表**：查看所有学生提交的项目。
* **在线编辑**：直接在表格中修改“项目级别”和“排名”。
* **批量操作**：
* **提交修改**：保存对级别的修改。
* **确认审核**：选中项目批量通过审核（状态变为“已通过”）。
* **批量导出**：将项目列表导出为 Excel 文件。
* **批量下载**：(模拟) 下载项目附件。



---

## ⚠️ 注意事项 (Notes)

1. **数据重置**：当前后端未使用 MySQL 数据库，所有数据保存在 Java 内存中。**重启后端项目后，之前提交的数据和修改会消失，恢复为默认的演示数据。**
2. **附件上传**：当前文件上传功能仅为演示，文件不会真实保存到服务器磁盘，下载功能也是模拟响应。

---

## 📅 待开发计划 (To-Do)

* [ ] 接入 MySQL 数据库，实现数据持久化。
* [ ] 接入 MinIO 或本地磁盘存储，实现真实文件上传下载。
* [ ] 增加“超级管理员”角色，管理二级管理员。
* [ ] 完善修改密码和个人信息功能。
