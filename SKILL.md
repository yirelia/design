---
name: pencil-elplus-design
description: 统一使用 Element Plus UI 框架，采用统一的主题色，业务组件母版支持用户自定义扩展。
license: Complete terms in LICENSE.txt
---

# Element Plus 设计规范 (Skill 文档)

本文档定义了基于 Element Plus 组件库的设计规范，包含统一主题色、业务组件母版以及原型图设计指南。

---

## 1. 设计理念

### 1.1 核心原则

- **一致性**: 所有组件遵循统一的视觉语言和交互模式
- **可扩展性**: 业务组件母版支持用户自定义扩展
- **可访问性**: 符合 WCAG 2.1 AA 标准
- **响应式**: 适配桌面端和移动端

### 1.2 设计 DNA

- **简洁现代**: 扁平化设计，减少视觉噪音
- **专业可靠**: 企业级应用的稳重感
- **高效友好**: 清晰的信息层级，流畅的操作体验

---

## 2. 统一主题色方案

### 2.1 品牌主色

```css
/* 主色 - Element Plus 默认蓝色系 */
--el-color-primary: #409EFF;
--el-color-primary-light-3: #79BBFF;
--el-color-primary-light-5: #A0CFFF;
--el-color-primary-light-7: #C6E2FF;
--el-color-primary-light-8: #D9ECFF;
--el-color-primary-light-9: #ECF5FF;
--el-color-primary-dark-2: #337ECC;
```

### 2.2 功能色

```css
/* 成功色 */
--el-color-success: #67C23A;
--el-color-success-light-3: #95D475;
--el-color-success-light-5: #B3E19D;
--el-color-success-light-7: #D1EDC4;
--el-color-success-light-8: #E1F3D8;
--el-color-success-light-9: #F0F9EB;
--el-color-success-dark-2: #529B2E;

/* 警告色 */
--el-color-warning: #E6A23C;
--el-color-warning-light-3: #EEBE77;
--el-color-warning-light-5: #F3D19E;
--el-color-warning-light-7: #F8E3C5;
--el-color-warning-light-8: #FAECD8;
--el-color-warning-light-9: #FDF6EC;
--el-color-warning-dark-2: #B88230;

/* 危险色 */
--el-color-danger: #F56C6C;
--el-color-danger-light-3: #F89898;
--el-color-danger-light-5: #FAB6B6;
--el-color-danger-light-7: #FCD3D3;
--el-color-danger-light-8: #FDE2E2;
--el-color-danger-light-9: #FEF0F0;
--el-color-danger-dark-2: #C45656;

/* 信息色 */
--el-color-info: #909399;
--el-color-info-light-3: #B1B3B8;
--el-color-info-light-5: #C8C9CC;
--el-color-info-light-7: #DEDFE0;
--el-color-info-light-8: #E9E9EB;
--el-color-info-light-9: #F4F4F5;
--el-color-info-dark-2: #73767A;
```

### 2.3 中性色

```css
/* 文本颜色 */
--el-text-color-primary: #303133;
--el-text-color-regular: #606266;
--el-text-color-secondary: #909399;
--el-text-color-placeholder: #A8ABB2;
--el-text-color-disabled: #C0C4CC;

/* 边框颜色 */
--el-border-color: #DCDFE6;
--el-border-color-light: #E4E7ED;
--el-border-color-lighter: #EBEEF5;
--el-border-color-extra-light: #F2F6FC;
--el-border-color-dark: #D4D7DE;
--el-border-color-darker: #CDD0D6;

/* 填充颜色 */
--el-fill-color: #F0F2F5;
--el-fill-color-light: #F5F7FA;
--el-fill-color-lighter: #FAFAFA;
--el-fill-color-extra-light: #FAFCFF;
--el-fill-color-dark: #EBEDF0;
--el-fill-color-darker: #E6E8EB;
--el-fill-color-blank: #FFFFFF;

/* 背景颜色 */
--el-bg-color: #FFFFFF;
--el-bg-color-page: #F2F3F5;
--el-bg-color-overlay: #FFFFFF;
```

### 2.4 阴影系统

```css
--el-box-shadow: 0px 12px 32px 4px rgba(0, 0, 0, 0.04),
                 0px 8px 20px rgba(0, 0, 0, 0.08);
--el-box-shadow-light: 0px 0px 12px rgba(0, 0, 0, 0.12);
--el-box-shadow-lighter: 0px 0px 6px rgba(0, 0, 0, 0.12);
--el-box-shadow-dark: 0px 16px 48px 16px rgba(0, 0, 0, 0.08),
                      0px 12px 32px rgba(0, 0, 0, 0.12),
                      0px 8px 16px -8px rgba(0, 0, 0, 0.16);
```

---

## 3. 字体规范

### 3.1 字体家族

```css
--el-font-family: 'Helvetica Neue', Helvetica, 'PingFang SC',
                  'Hiragino Sans GB', 'Microsoft YaHei', '微软雅黑',
                  Arial, sans-serif;
```

### 3.2 字号规范

| 用途 | 字号 | 行高 | 字重 |
|------|------|------|------|
| 大标题 | 20px | 28px | 600 |
| 标题 | 18px | 26px | 600 |
| 小标题 | 16px | 24px | 600 |
| 正文(大) | 16px | 24px | 400 |
| 正文 | 14px | 22px | 400 |
| 正文(小) | 13px | 20px | 400 |
| 辅助文字 | 12px | 18px | 400 |
| 提示文字 | 12px | 18px | 400 |

---

## 4. 间距规范

### 4.1 基础间距

```css
--el-spacing-xs: 4px;
--el-spacing-sm: 8px;
--el-spacing-md: 12px;
--el-spacing-base: 16px;
--el-spacing-lg: 20px;
--el-spacing-xl: 24px;
--el-spacing-xxl: 32px;
```

### 4.2 组件间距

| 场景 | 间距值 |
|------|--------|
| 表单项间距 | 16px |
| 卡片内边距 | 20px |
| 页面边距 | 24px |
| 模块间距 | 24px |
| 区块间距 | 32px |

---

## 5. 圆角规范

```css
--el-border-radius-base: 4px;
--el-border-radius-small: 2px;
--el-border-radius-round: 20px;
--el-border-radius-circle: 100%;
```

---

## 6. 业务组件母版

### 6.1 母版设计原则

业务组件母版提供可扩展的基础结构，用户可以基于母版进行自定义扩展。

### 6.2 页面布局母版

#### 6.2.1 标准管理页面布局

```
┌─────────────────────────────────────────────────────────┐
│                      Header (64px)                       │
├──────────┬──────────────────────────────────────────────┤
│          │              Breadcrumb                       │
│          ├──────────────────────────────────────────────┤
│  Sidebar │              Page Header                      │
│  (200px) │              (标题 + 操作按钮)                 │
│          ├──────────────────────────────────────────────┤
│          │              Content Area                     │
│          │              (主要内容区域)                    │
│          ├──────────────────────────────────────────────┤
│          │              Footer (可选)                    │
└──────────┴──────────────────────────────────────────────┘
```

#### 6.2.2 表单页面布局

```
┌─────────────────────────────────────────────────────────┐
│                      Header                              │
├──────────┬──────────────────────────────────────────────┤
│          │              Page Title                       │
│  Sidebar ├──────────────────────────────────────────────┤
│          │  ┌─────────────────────────────────────────┐ │
│          │  │           Form Card                      │ │
│          │  │  ┌─────────────────────────────────┐    │ │
│          │  │  │      Form Fields                │    │ │
│          │  │  └─────────────────────────────────┘    │ │
│          │  │  ┌─────────────────────────────────┐    │ │
│          │  │  │      Form Actions               │    │ │
│          │  │  └─────────────────────────────────┘    │ │
│          │  └─────────────────────────────────────────┘ │
└──────────┴──────────────────────────────────────────────┘
```

### 6.3 基础组件母版

#### 6.3.1 搜索表单母版

```vue
<template>
  <el-form :model="searchForm" inline>
    <!-- 搜索字段插槽 -->
    <slot name="search-fields"></slot>

    <!-- 操作按钮 -->
    <el-form-item>
      <el-button type="primary" @click="handleSearch">
        <el-icon><Search /></el-icon>
        搜索
      </el-button>
      <el-button @click="handleReset">
        <el-icon><Refresh /></el-icon>
        重置
      </el-button>
      <!-- 扩展按钮插槽 -->
      <slot name="extra-actions"></slot>
    </el-form-item>
  </el-form>
</template>
```

#### 6.3.2 数据表格母版

```vue
<template>
  <div class="table-container">
    <!-- 表格工具栏 -->
    <div class="table-toolbar">
      <slot name="toolbar-left"></slot>
      <div class="toolbar-right">
        <slot name="toolbar-right"></slot>
      </div>
    </div>

    <!-- 数据表格 -->
    <el-table :data="tableData" v-loading="loading">
      <slot name="columns"></slot>

      <!-- 操作列插槽 -->
      <el-table-column label="操作" fixed="right" width="180">
        <template #default="scope">
          <slot name="actions" :row="scope.row"></slot>
        </template>
      </el-table-column>
    </el-table>

    <!-- 分页 -->
    <div class="pagination-container">
      <el-pagination
        v-model:current-page="currentPage"
        v-model:page-size="pageSize"
        :total="total"
        layout="total, sizes, prev, pager, next, jumper"
      />
    </div>
  </div>
</template>
```

#### 6.3.3 详情卡片母版

```vue
<template>
  <el-card class="detail-card">
    <template #header>
      <div class="card-header">
        <span class="title">{{ title }}</span>
        <slot name="header-actions"></slot>
      </div>
    </template>

    <el-descriptions :column="column" border>
      <slot name="descriptions"></slot>
    </el-descriptions>

    <!-- 扩展内容插槽 -->
    <slot name="extra-content"></slot>
  </el-card>
</template>
```

#### 6.3.4 弹窗表单母版

```vue
<template>
  <el-dialog
    v-model="visible"
    :title="title"
    :width="width"
    destroy-on-close
  >
    <el-form
      ref="formRef"
      :model="formData"
      :rules="rules"
      label-width="100px"
    >
      <slot name="form-fields"></slot>
    </el-form>

    <template #footer>
      <el-button @click="handleCancel">取消</el-button>
      <el-button type="primary" @click="handleSubmit" :loading="loading">
        确定
      </el-button>
      <slot name="extra-footer"></slot>
    </template>
  </el-dialog>
</template>
```

### 6.4 业务组件母版

#### 6.4.1 用户选择器母版

```vue
<template>
  <div class="user-selector">
    <el-select
      v-model="selectedUsers"
      multiple
      filterable
      remote
      :remote-method="searchUsers"
      placeholder="请选择用户"
    >
      <el-option
        v-for="user in userList"
        :key="user.id"
        :label="user.name"
        :value="user.id"
      >
        <div class="user-option">
          <el-avatar :size="24" :src="user.avatar" />
          <span class="user-name">{{ user.name }}</span>
          <span class="user-dept">{{ user.department }}</span>
        </div>
      </el-option>
    </el-select>

    <!-- 扩展插槽：已选用户展示 -->
    <slot name="selected-display" :users="selectedUserDetails"></slot>
  </div>
</template>
```

#### 6.4.2 文件上传母版

```vue
<template>
  <div class="file-uploader">
    <el-upload
      :action="uploadUrl"
      :headers="headers"
      :before-upload="beforeUpload"
      :on-success="handleSuccess"
      :on-error="handleError"
      :file-list="fileList"
      :limit="limit"
    >
      <slot name="trigger">
        <el-button type="primary">
          <el-icon><Upload /></el-icon>
          点击上传
        </el-button>
      </slot>

      <template #tip>
        <slot name="tip">
          <div class="el-upload__tip">
            支持 {{ acceptTypes }} 格式，单个文件不超过 {{ maxSize }}MB
          </div>
        </slot>
      </template>
    </el-upload>

    <!-- 文件列表扩展插槽 -->
    <slot name="file-list" :files="fileList"></slot>
  </div>
</template>
```

#### 6.4.3 审批流程母版

```vue
<template>
  <div class="approval-flow">
    <el-steps :active="currentStep" finish-status="success">
      <el-step
        v-for="(step, index) in steps"
        :key="index"
        :title="step.title"
        :description="step.description"
      >
        <template #icon>
          <slot :name="`step-icon-${index}`" :step="step">
            <el-icon><User /></el-icon>
          </slot>
        </template>
      </el-step>
    </el-steps>

    <!-- 当前步骤详情插槽 -->
    <div class="step-content">
      <slot name="step-content" :step="currentStepData"></slot>
    </div>

    <!-- 审批操作插槽 -->
    <div class="approval-actions">
      <slot name="approval-actions"></slot>
    </div>
  </div>
</template>
```

---

## 7. 消息提醒规范

### 7.1 消息类型

| 类型 | 使用场景 | 图标 | 颜色 |
|------|----------|------|------|
| success | 操作成功 | SuccessFilled | #67C23A |
| warning | 警告提示 | WarningFilled | #E6A23C |
| error | 错误提示 | CircleCloseFilled | #F56C6C |
| info | 信息提示 | InfoFilled | #909399 |

### 7.2 消息组件选择

| 组件 | 使用场景 |
|------|----------|
| ElMessage | 轻量级全局提示，自动消失 |
| ElMessageBox | 需要用户确认的操作 |
| ElNotification | 系统通知，较长内容 |
| ElAlert | 页面内静态提示 |

### 7.3 消息文案规范

- **成功**: "XXX成功" (如：保存成功、提交成功)
- **失败**: "XXX失败，请重试" (如：保存失败，请重试)
- **确认**: "确定要XXX吗？" (如：确定要删除吗？)
- **警告**: "XXX，请注意" (如：数据未保存，请注意)

---

## 8. 交互规范

### 8.1 按钮规范

| 类型 | 使用场景 | 样式 |
|------|----------|------|
| Primary | 主要操作 | type="primary" |
| Default | 次要操作 | 默认 |
| Text | 文字链接操作 | type="text" |
| Danger | 危险操作 | type="danger" |

### 8.2 按钮位置

- **表单**: 右对齐，主按钮在右
- **弹窗**: 右对齐，取消在左，确定在右
- **表格操作列**: 左对齐
- **页面顶部**: 右对齐

### 8.3 加载状态

- 按钮操作时显示 loading 状态
- 表格加载时使用 v-loading 指令
- 页面加载时使用骨架屏或 loading 遮罩

---

## 9. 原型图设计指南

### 9.1 使用 Pencil 绘制原型

原型图应包含以下要素：

1. **页面结构**: 清晰的布局层级
2. **组件标注**: 使用的 Element Plus 组件
3. **交互说明**: 关键交互行为描述
4. **状态展示**: 不同状态的界面表现

### 9.2 原型校验清单

- [ ] 布局是否符合规范
- [ ] 颜色是否使用主题色
- [ ] 间距是否符合规范
- [ ] 组件使用是否正确
- [ ] 交互是否完整
- [ ] 响应式是否考虑

---

## 10. 扩展指南

### 10.1 自定义主题

```scss
// 覆盖 Element Plus 变量
@forward 'element-plus/theme-chalk/src/common/var.scss' with (
  $colors: (
    'primary': (
      'base': #your-primary-color,
    ),
  ),
);
```

### 10.2 扩展业务组件

1. 继承母版组件
2. 通过插槽扩展功能
3. 通过 props 配置行为
4. 保持与设计规范一致

---

## 附录

### A. 图标使用

推荐使用 `@element-plus/icons-vue` 图标库。

### B. 参考资源

- [Element Plus 官方文档](https://element-plus.org/)
- [Element Plus 设计资源](https://element-plus.org/zh-CN/resource/index.html)

---

*本文档版本: 1.0.0*
*最后更新: 2026-01-30*
