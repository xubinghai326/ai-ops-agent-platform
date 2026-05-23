# AI Ops Agent Platform MVP

一个用于展示 `Manager Agent + Worker Node` 架构思路的静态前端原型。

## 项目目标

这个 MVP 重点验证一条最小可用闭环：

- 输入运营事件或玩家反馈
- `Manager` 识别问题类型、优先级和路由策略
- `Worker` 执行分类、摘要、相似案例检索和公告草稿生成
- 输出结构化结果
- 进入人工确认闸门

当前版本是纯静态网页，适合直接部署到 `GitHub Pages`。

## 页面说明

- `index.html`
  - 项目首页
- `platform.html`
  - 主演示页，包含输入层、Manager、Worker、执行时间线、结果输出、人工确认闸门
- `README.html`
  - 汇报式项目说明页
- `prototype-assets/ui.css`
  - 共享样式文件

## 本地预览

在项目目录启动一个静态服务即可：

```bash
cd ai-ops-agent-platform
python3 -m http.server 4173
```

然后访问：

```text
http://127.0.0.1:4173
```

## GitHub Pages 部署方式

适合这个项目，因为它没有后端依赖，只需要静态托管。

### 方式一：整个仓库直接发布

1. 新建一个 GitHub 仓库
2. 把当前文件夹内的全部内容上传到仓库根目录
3. 打开 GitHub 仓库的 `Settings`
4. 进入 `Pages`
5. 在 `Build and deployment` 中选择：
   - `Source`: `Deploy from a branch`
   - `Branch`: `main`
   - `Folder`: `/ (root)`
6. 保存后等待 GitHub 自动发布

发布成功后，访问地址通常为：

```text
https://你的用户名.github.io/仓库名/
```

### 方式二：放到已有展示仓库的子目录

如果你已经有一个静态展示仓库，也可以把本项目作为一个子目录放进去，再通过对应路径访问。

## 适合汇报时的演示方式

建议从 `platform.html` 开始演示：

1. 选择一个场景
2. 点击“运行本次 Agent 流程”
3. 讲解 Manager 的识别与路由
4. 展示 Worker 执行过程
5. 展示结构化输出
6. 强调“人工确认闸门”不允许 AI 直接执行高风险动作

## 当前版本边界

- 不接真实数据库
- 不调用真实大模型接口
- 不执行真实发奖、封禁、公告发布等高风险操作
- 重点是展示平台结构、交互思路和 MVP 落地路径
