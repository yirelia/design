# Pencil 文件归类与业务组件命名规范

本文档定义了 Pencil 原型文件的组织结构和业务组件的命名规范。

---

## 1. 文件目录结构

```
pencil-prototypes/
├── 00-公共组件/                    # 通用业务组件
│   ├── layout/                     # 布局组件
│   │   ├── Layout-Header.ep        # 顶部导航
│   │   ├── Layout-Sidebar.ep       # 侧边栏
│   │   └── Layout-Footer.ep        # 页脚
│   ├── form/                       # 表单组件
│   │   ├── Form-Search.ep          # 搜索表单
│   │   ├── Form-Filter.ep          # 筛选表单
│   │   └── Form-Dialog.ep          # 弹窗表单
│   ├── table/                      # 表格组件
│   │   ├── Table-Basic.ep          # 基础表格
│   │   ├── Table-Tree.ep           # 树形表格
│   │   └── Table-Editable.ep       # 可编辑表格
│   └── business/                   # 业务通用组件
│       ├── Biz-UserSelector.ep     # 用户选择器
│       ├── Biz-FileUpload.ep       # 文件上传
│       ├── Biz-ApprovalFlow.ep     # 审批流程
│       └── Biz-TreeSelector.ep     # 树形选择器
│
├── 01-系统管理/                    # 系统管理模块
│   ├── User-List.ep                # 用户列表
│   ├── User-Detail.ep              # 用户详情
│   ├── Role-List.ep                # 角色列表
│   ├── Role-Permission.ep          # 角色权限
│   ├── Menu-List.ep                # 菜单管理
│   └── Dict-List.ep                # 字典管理
│
├── 02-架构模型/                    # 架构模型模块（示例）
│   ├── Model-Tree.ep               # 架构树
│   ├── Model-Component.ep          # 组件管理
│   ├── Model-Port.ep               # 端口管理
│   ├── Model-Param.ep              # 参数定义
│   └── Model-Variable.ep           # 变量定义
│
├── 03-监控中心/                    # 监控模块
│   ├── Monitor-Dashboard.ep        # 监控大屏
│   ├── Monitor-Alert.ep            # 告警管理
│   └── Monitor-Log.ep              # 日志查看
│
└── 99-模板/                        # 页面模板
    ├── Template-CRUD.ep            # 增删改查模板
    ├── Template-Detail.ep          # 详情页模板
    ├── Template-Dashboard.ep       # 仪表盘模板
    └── Template-Wizard.ep          # 向导页模板
```

---

## 2. 文件命名规范

### 2.1 命名格式

```
[模块前缀]-[功能描述].ep
```

### 2.2 命名规则

| 类型 | 前缀 | 示例 |
|------|------|------|
| 布局组件 | `Layout-` | Layout-Header.ep |
| 表单组件 | `Form-` | Form-Search.ep |
| 表格组件 | `Table-` | Table-Basic.ep |
| 业务组件 | `Biz-` | Biz-UserSelector.ep |
| 页面模板 | `Template-` | Template-CRUD.ep |
| 用户管理 | `User-` | User-List.ep |
| 角色管理 | `Role-` | Role-List.ep |
| 菜单管理 | `Menu-` | Menu-List.ep |
| 架构模型 | `Model-` | Model-Tree.ep |
| 监控中心 | `Monitor-` | Monitor-Dashboard.ep |

### 2.3 命名约定

- 使用 **PascalCase** 命名（首字母大写）
- 前缀与功能之间用 `-` 连接
- 功能描述简洁明了，不超过 3 个单词
- 避免使用拼音，统一使用英文

---

## 3. 业务组件命名规范

### 3.1 组件 ID 命名

在 Pencil 中，每个组件应设置唯一的 ID，便于后期代码生成。

```
[组件类型]__[业务模块]__[功能描述]
```

**示例：**

| 组件 | ID 命名 |
|------|---------|
| 端口名称输入框 | `input__model__portName` |
| 流向下拉框 | `select__model__flowDirection` |
| 查询按钮 | `btn__model__search` |
| 重置按钮 | `btn__model__reset` |
| 端口列表表格 | `table__model__portList` |
| 新增端口弹窗 | `dialog__model__addPort` |

### 3.2 表单字段命名

```
[字段类型]__[表名/模块]__[字段名]
```

| 字段类型 | 前缀 | 示例 |
|----------|------|------|
| 输入框 | `input__` | input__port__name |
| 下拉框 | `select__` | select__port__direction |
| 日期选择 | `date__` | date__port__createTime |
| 单选框 | `radio__` | radio__port__type |
| 复选框 | `checkbox__` | checkbox__port__status |
| 开关 | `switch__` | switch__port__enabled |
| 文本域 | `textarea__` | textarea__port__remark |

### 3.3 按钮命名

```
btn__[模块]__[操作]
```

| 操作类型 | 命名 | 示例 |
|----------|------|------|
| 查询 | `search` | btn__port__search |
| 重置 | `reset` | btn__port__reset |
| 新增 | `add` | btn__port__add |
| 编辑 | `edit` | btn__port__edit |
| 删除 | `delete` | btn__port__delete |
| 导出 | `export` | btn__port__export |
| 导入 | `import` | btn__port__import |
| 保存 | `save` | btn__port__save |
| 取消 | `cancel` | btn__port__cancel |
| 提交 | `submit` | btn__port__submit |

---

## 4. 页面元素标注规范

### 4.1 标注内容

在原型图中，应对以下内容进行标注：

| 标注项 | 说明 | 示例 |
|--------|------|------|
| 组件类型 | Element Plus 组件名 | `el-input` |
| 组件 ID | 唯一标识符 | `input__port__name` |
| 数据绑定 | v-model 绑定字段 | `formData.portName` |
| 校验规则 | 表单验证规则 | `required, max:50` |
| 交互说明 | 特殊交互行为 | `输入时触发远程搜索` |

### 4.2 标注颜色规范

| 标注类型 | 颜色 | 用途 |
|----------|------|------|
| 组件标注 | `#409EFF` (蓝色) | 组件类型和 ID |
| 交互说明 | `#E6A23C` (橙色) | 交互行为描述 |
| 数据说明 | `#67C23A` (绿色) | 数据绑定和接口 |
| 注意事项 | `#F56C6C` (红色) | 重要提示和待定项 |

---

## 5. 架构模型模块示例

基于您提供的原型图，以下是架构模型模块的组件规范：

### 5.1 端口管理页面组件

```
页面：Model-Port.ep

┌─────────────────────────────────────────────────────────────┐
│  作动系统控制系统(作动系统控制系统)                    [×]   │
├─────────────────────────────────────────────────────────────┤
│  [组件]    [端口]    [参数定义]    [输出端口变量定义]        │
│                                                             │
│  端口名称 [input__port__name    ]  流向 [select__port__dir] │
│                                        [重置] [查询]        │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ 名称          │ 流向    │ 物理属性                   │   │
│  │ table__port__list                                   │   │
│  ├───────────────┼─────────┼───────────────────────────┤   │
│  │ 端口12        │ 输入    │ 机械/电气等               │   │
│  │ 端口1         │ 输出    │                           │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
│  备注：                                                     │
│  1、目前只考虑增加属性                                      │
│  2、后续产品里根据需求再决定是否对不同物理属性的接口        │
│     增加可连接的校验                                        │
└─────────────────────────────────────────────────────────────┘
```

### 5.2 组件 ID 清单

| 组件 | ID | 类型 | 说明 |
|------|-----|------|------|
| 端口名称输入框 | `input__port__name` | el-input | 支持模糊搜索 |
| 流向下拉框 | `select__port__direction` | el-select | 选项：输入/输出 |
| 重置按钮 | `btn__port__reset` | el-button | 清空搜索条件 |
| 查询按钮 | `btn__port__search` | el-button | type="primary" |
| 端口列表表格 | `table__port__list` | el-table | 支持排序 |
| 物理属性列 | `col__port__physicalAttr` | el-table-column | 机械/电气等 |

### 5.3 数据结构

```typescript
// 端口表单数据
interface PortSearchForm {
  portName: string;      // 端口名称
  direction: string;     // 流向：input | output
}

// 端口列表项
interface PortItem {
  id: string;
  name: string;          // 名称
  direction: string;     // 流向
  physicalAttr: string;  // 物理属性
}
```

---

## 6. 版本管理

### 6.1 文件版本命名

```
[文件名]-v[主版本].[次版本].ep
```

**示例：**
- `Model-Port-v1.0.ep` - 初始版本
- `Model-Port-v1.1.ep` - 小改动
- `Model-Port-v2.0.ep` - 大改版

### 6.2 变更记录

每个原型文件应在备注区域记录变更历史：

```
变更记录：
- v1.0 (2026-01-30): 初始版本，包含基础端口管理功能
- v1.1 (2026-01-31): 新增物理属性列
- v2.0 (2026-02-01): 重构表格布局，支持树形结构
```

---

*本文档版本: 1.0.0*
