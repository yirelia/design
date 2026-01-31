# Element Plus 业务组件模板

本文档提供可扩展的业务组件母版，用户可以基于母版进行自定义扩展。

---

## 1. 母版设计原则

- **可扩展性**: 通过插槽支持用户自定义扩展
- **一致性**: 遵循统一的视觉语言和交互模式
- **复用性**: 提供通用的业务场景解决方案

---

## 2. 页面布局母版

### 2.1 标准管理页面布局

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

### 2.2 表单页面布局

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

---

## 3. 基础组件母版

### 3.1 搜索表单母版

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

### 3.2 数据表格母版

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

### 3.3 详情卡片母版

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

### 3.4 弹窗表单母版

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

---

## 4. 业务组件母版

### 4.1 用户选择器母版

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

### 4.2 文件上传母版

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

### 4.3 审批流程母版

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

## 5. 扩展业务组件指南

1. 继承母版组件
2. 通过插槽扩展功能
3. 通过 props 配置行为
4. 保持与设计规范一致

---

*本文档版本: 1.0.0*
